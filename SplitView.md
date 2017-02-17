# SplitView

SplitView是一个存放两个视图的容器，一个视图存放的是主要内容，而另外一个一般用作导航。

## 语法

### 声明

```C#
public class SplitView
```

```xaml
<SplitView>
  <SplitView.Content>
    singleObject
  </SplitView.Content>
  <SplitView.Pane>
    singleObject
  </SplitView.Pane>
</SplitView>
```

### 继承层次结构

[DependencyObject](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.dependencyobject)  
　　[UIElement](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.uielement)  
　　　　[FrameworkElement](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.frameworkelement)  
　　　　　　[Control](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.control)  
　　　　　　　　SplitView

### 继承的成员

[点击这里查看](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#syntax)

## 注意事项

[SplitView](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview)控件的内容由两部分区域构成：窗格Pane区域，以及主要内容区域。通常来讲，你可以根据[导航栏设计规范](http://msdn.microsoft.com/library/8fb52f5e-8e72-4604-9222-0b0ec6a97541)用[SplitView](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview)创建一个适应不同屏幕尺寸的顶级导航，但实际上，它不只是可以用于导航栏。  
  
下面是[SplitView](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview)的一个示例。  
![示例](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls/images/controls/splitviewbasic.png)  
  
[内容区域](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_Content)始终是可见的，它可以只包含一个子元素，该子元素一般都是包含附加子元素的内容面板。尽管内容区域是始终可见的，不过它也可以被Pane窗格区域完全覆盖。  

你可以设置SplitView的一些属性来定制[Pane窗格](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_Pane)的外观和行为。设置[IsPaneOpen](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_IsPaneOpen)属性来打开或是关闭[Pane窗格](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_Pane)。[SplitView](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview)不提供用来切换[Pane窗格](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_Pane)状态的菜单或者汉堡按钮，切换[IsPaneOpen属性](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_IsPaneOpen)必须由你自己手动编码实现。  

要指定[Pane窗格](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_IsPaneOpen)打开时的宽度，设置[OpenPaneLength属性](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_OpenPaneLength)。你也可以设置[PanePlacement属性](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_PanePlacement)来设置[Pane窗格](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_Pane)是出现内容区域的左边还是右边。  

尽管SplitView控件的外观主要由Pane窗格和内容区域的子元素所决定，不过你还是可以设置PaneBackground属性来改变默认的背景色。  

通过设置DisplayMode属性，你可以配置Pane窗格和内容区域之间的交互方式。在默认状态下，Pane窗格在打开时会覆盖内容区域，在关闭时Pane窗格会消失。设置DisplayMode为"inline"内联模式，Pane窗格就会与内容区域并排显示。设置DisplayMode为"compact"紧凑模式，这样即便Pane窗格处于关闭状态，它仍然是可见的。欲知更多有关受支持模式的信息，请访问[SplitViewDisplayMode](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitviewdisplaymode)。  

有关设计指南的部分，请参见[SplitView控件设计指南](http://msdn.microsoft.com/library/e9e4537f-1160-4183-9a83-26602fcfdc9a)。  

有关建立顶级导航体验的更多信息和示例，请查看[导航窗格指南](http://msdn.microsoft.com/library/8fb52f5e-8e72-4604-9222-0b0ec6a97541)和[XAML导航菜单示例](http://go.microsoft.com/fwlink/p/?LinkId=619902&amp;clcid=0x409)。  

### 代码示例

下面这个示例展示了一个Pane窗格和内容区域内联的SplitView控件。  

```xaml
<SplitView IsPaneOpen="True"
           DisplayMode="Inline"
           OpenPaneLength="296">
    <SplitView.Pane>
        <TextBlock Text="Pane"
                   FontSize="24"
                   VerticalAlignment="Center"
                   HorizontalAlignment="Center"/>
    </SplitView.Pane>

    <Grid>
        <TextBlock Text="Content"
                   FontSize="24"
                   VerticalAlignment="Center"
                   HorizontalAlignment="Center"/>
    </Grid>
</SplitView>
```

## 构造函数一览

[SplitView()](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView__ctor)  
初始化SplitView类的一个实例  

## 属性一览

[CompactPaneLength](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_CompactPaneLength)  
获取或设置SplitView的Pane窗格在紧凑显示模式下的宽度  

[CompactPaneLengthProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_CompactPaneLengthProperty)  
标识CompactPaneLength依赖属性  

[Content](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_Content)  
获取或设置SplitView主面板的内容  

[ContentProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_ContentProperty)  
标识Content依赖属性  

[DisplayMode](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_DisplayMode)  
获取或设置一个值，指定Pane窗格和SplitView的内容区域的显示方式  

[DisplayModeProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_DisplayModeProperty)  
标识DisplayMode依赖属性  

[IsPaneOpen](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_IsPaneOpen)  
获取或设置一个值，指定SplitView的Pane窗格是否扩展到最大宽度  

[IsPaneOpenProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_IsPaneOpenProperty)  
标识IsPaneOpen依赖属性  

[LightDismissOverlayMode](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_LightDismissOverlayMode)  
获取或设置一个值，指定light-dismiss UI之外的区域是否变暗  

[LightDismissOverlayModeProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_LightDismissOverlayModeProperty)  
标识LightDismissOverlayMode依赖属性  

[OpenPaneLength](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_OpenPaneLength)  
获取或设置SplitView的Pane窗格完全展开时的宽度  

[OpenPaneLengthProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_OpenPaneLengthProperty)  
标识OpenPaneLength依赖属性  

[Pane](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_Pane)  
获取或设置SplitView的Pane窗格的内容  

[PaneBackground](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_PaneBackground)  
获取或设置要应用于控件窗格区域的背景的画笔  

[PaneBackgroundProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_PaneBackgroundProperty)  
标识PaneBackground依赖属性  

[PanePlacement](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_PanePlacement)  
获取或设置一个值，指定Pane窗格是显示在SplitView的右边还是左边  

[PanePlacementProperty](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_PanePlacementProperty)  
标识PanePlacement依赖属性  

[TemplateSettings](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_TemplateSettings)  
获取一个对象，在为SplitView控件定义模板时，提供能够被引用为TemplateBinding资源的计算值  

## 事件一览

[PaneClosed](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_PaneClosed)  
当SplitView的Pane窗格关闭时触发  

[PaneClosing](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Xaml.Controls.SplitView#Windows_UI_Xaml_Controls_SplitView_PaneClosing)  
当SplitView的Pane窗格正在关闭时触发  

## 构造函数

### SplitView()  

初始化SplitView类的一个新实例  

```C#
public SplitView()
```

## 属性

### CompactPaneLength

获取或设置SplitView的Pane窗格在紧凑显示模式下的宽度。  

```C#
public double CompactPaneLength { get; set; }
```

```XAML
<SplitView CompactPaneLength="double" .../>
```

#### 属性值

double  
在紧凑显示模式下Pane窗格的宽度。默认是48 device-independent-pixel(DIP)（由SplitViewCompactPaneThemeLength资源定义）  

#### 注意事项

当显示模式是`SplitViewDisplayMode`并且IsPaneOpen为`false`时，这个属性指定了Pane窗格的宽度。  

### CompactPaneLengthProperty

标识CompactPaneLength依赖属性  

```C#
public static DependencyProperty CompactPaneLengthProperty { get; }
```

#### 属性值

[DependencyProperty](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.dependencyproperty)  
标识CompactPaneLength依赖属性  

### Content

获取或设置SplitView主面板的内容

```C#
public UIElement Content { get; set; }
```

```XAML
<SplitView>
  singleObject
</SplitView>
```

#### 属性值

[UIElement](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.uielement)  
SplitView主面板的内容。默认为空null。

### ContentProperty

标识`Content`依赖属性  

```C#
public static DependencyProperty ContentProperty { get; }
```

#### 属性值

[DependencyProperty](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.dependencyproperty)  
标识`Content`依赖属性

### DisplayMode

获取或设置一个值，指定Pane窗格和SplitView的内容区域的显示方式  

```C#
public SplitViewDisplayMode DisplayMode { get; set; }
```

```XAML
<SplitView DisplayMode="splitViewDisplayModeMemberName" />
```

#### 属性值

[SplitViewDisplayMode](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitviewdisplaymode)  
一系列枚举值，指定Pane窗格和SplitView的内容区域的显示方式。默认值是`Overlay`。

### DisplayModeProperty

标识`DisplayMode`依赖属性

```C#
public static DependencyProperty DisplayModeProperty { get; }
```

#### 属性值

[DependencyProperty](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.dependencyproperty)  
标识`DisplayMode`依赖属性

### IsPaneOpen

获取或设置一个值，指定SplitView的Pane窗格是否扩展到最大宽度

```C#
public bool IsPaneOpen { get; set; }
```

```XAML
<SplitView IsPaneOpen="bool" .../>
```

#### 属性值

`bool`  
`true`-如果Pane窗格扩展到了最大宽度；否则，`false`。默认值是`true`。

#### 注意事项

此属性的实际效果受到`DisplayMode`属性值的影响。  

| DisplayMode        | Effect    |
| :--------:   | :-----:   |
| Inline内联        | `IsPaneOpen`始终为`true`      |
| Overlay覆盖        | 当`IsPaneOpen`为false时，Pane窗格被隐藏      |  
| Compact紧凑        | 当`IsPaneOpen`为false时，Pane窗格显示为紧凑的尺寸（参见[CompactPaneLength](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_CompactPaneLength)）      |

### IsPaneOpenProperty

标识`IsPaneOpen`依赖属性

```C#
public static DependencyProperty IsPaneOpenProperty { get; }
```

#### 属性值

[DependencyProperty](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.dependencyproperty)  
标识`IsPaneOpen`依赖属性

### LightDismissOverlayMode

获取或设置一个值，指定light-dismiss UI之外的区域是否变暗

```C#
public LightDismissOverlayMode LightDismissOverlayMode { get; set; }
```

#### 属性值

[LightDismissOverlayMode](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.lightdismissoverlaymode)  
一系列枚举值，指定light-dismiss UI之外的区域是否变暗。默认值是`Auto`。

#### 注意事项

Transient UI，比如打开着的`SplitView`，当你点击Pane窗格外部的时候，Pane窗格会关闭。这就称之为light-dismiss。`Overlay`指的是light-dismiss UI之外的区域。默认情况下，Xbox中的`Overlay`区域会变暗，而在其他设备族中则不会。你可以设置[LightDismissOverlayMode](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_LightDismissOverlayMode)为on开启状态，这样你的应用会将所有设备族中的`Overlay`区域变暗；相反，你也可以将其设置为off关闭状态。   

### 版本兼容性

[LightDismissOverlayMode](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.splitview#Windows_UI_Xaml_Controls_SplitView_LightDismissOverlayMode)属性在Windows10 version 1607之前的版本中不可用。如果你在Viusal Studio中设置的应用程序的最低平台版本低于本页后面要求的引进版本，你就必须设计并测试你的应用程序以免出现问题