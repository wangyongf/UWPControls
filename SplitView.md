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

