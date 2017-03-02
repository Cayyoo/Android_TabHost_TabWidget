# TabHost、TabWidget实现Tab页效果

```java

/**
 * TabHost、TabWidget实现Tab页效果
 *
 * 实现TabHost有两种方式：
 * 方式一：直接让一个Activity程序继承TabActivity类（通过getTabHost取得实例）；
 * 方式二：定义XML布局文件利用findViewById()方法取得TagHost组件，通过setup()方法实例化并进行若干配置；
 *
 * 要用到tab组件，布局layout中必须有TabHost文件，它有一个id，比如 android:id="@+id/tabhost" 或者android:id="@android:id/tabhost"
 * 在TabHost中一般必须有TabWidget，这个主要是用来处理tab的位置、属性等。一般还有FrameLayout组件，用于定义显示的在Tab下显示的组件。
 *
 * 1、常用组件
 * TabWidget : 该组件就是TabHost标签页中上部 或者 下部的按钮, 可以点击按钮切换选项卡;
 * TabSpec : 代表了选项卡界面, 添加一个TabSpec即可添加到TabHost中;
 * 创建选项卡 : newTabSpec(String tag), 创建一个选项卡;
 * 添加选项卡 : addTab(tabSpec);

 * 2、使用步骤
 *  a. 定义布局 : 在XML文件中使用TabHost组件, 并在其中定义一个FrameLayout选项卡内容;
 *  b. 继承TabActivity : 显示选项卡组件的Activity继承TabActivity;
 *  c. 获取组件 : 通过调用getTabHost()方法, 获取TabHost对象;
 *  d. 创建添加选项卡 : 通过TabHost创建添加选项卡;

 * 3、将按钮放到下面
 *  布局文件中TabWidget代表的就是选项卡按钮, Fragement组件代表内容;
 *  设置失败情况 : 如果Fragement组件没有设置 android:layout_weight属性, 那么将TabWidget放到下面, 可能不会显示按钮;
 *  设置权重 : 设置了Fragment组件的权重之后, 就可以成功显示该选项卡按钮;
 */



/**
 * TabWidget
 * 选项卡切换 : 该组件是选项卡切换按钮, 通过点击该组件可以切换选项卡;
 * 设置android自带id : 这个组件的id要设置成android的自带id : android:id=@android:id/tabs ;
 * TabHost必备组件 : 该组件与FrameLayout组件是TabHost组件中必备的两个组件;
 * 切换按钮下方显示 : 如果想要将按钮放到下面, 可以将该组件定义在下面, 但是注意,FrameLayout要设置android:layout_widget = 1;
 * 设置TabWidget大小 : 如果想要设置该按钮组件的大小, 可以设置该组件与FrameLayout组件的权重;
 */

/**
 * FrameLayout
 * 组件作用 : 该组件中定义的子组件是TabHost中每个页面显示的选项卡, 可以将TabHost选项卡显示的视图定义在其中;
 * 设置android自带id : 这个组件的id要设置成android的自带的id : android:id=@android:id/tabcontent ;
 */

/**
 * Activity方法
 *
 * 1、获取TabHost
 * 获取方法 : getHost();
 * 前提 : 调用getHost()方法获取TabHost组件的方法的前提是在布局文件中, 设置了android自带的id android:id=@android:id/tabhost 才可以;
 * 2、创建选项卡
 * 创建选项卡 : 调用TabHost组件的newTabHost(tag), 其中的tag是字符串, 即在选项卡的唯一标识;
 * 设置选项卡 :
 *     设置按钮名称 : setIndicator(叫兽);
 *     设置选项卡内容 : setContent(), 可以设置视图组件, 可以设置Activity, 也可以设置Fragement;
 * 添加选项卡 : tabHost.add(tag), 传入的参数是创建选项卡的时候定义的唯一标识;
 */



/**
 * 当 extends FragmentActivity时，可使用<android.support.v4.app.FragmentTabHost/>
 */

/**
 * 当继承自Activity时，
 * TabWidget的id必须定义为：android:id="@android:id/tabs"，
 * FrameLayout的id必须定义为：android:id="@android:id/tabcontent"
 * 其它控件没有限制，否则报错。
 */

```

![img](https://github.com/ykmeory/TabHost_TabWidget/blob/master/img.jpg "screenshot")
