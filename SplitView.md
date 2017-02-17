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