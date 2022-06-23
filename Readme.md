<!-- default badges list -->
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T326805)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
# WPF Dock Layout Manager - Build a Layout Similar to Visual Studio

Let's see how to build a layout similar to Visual Studio using the DXDocking Suite. Below is the screenshot of the **Dock Windows -> VS2010 Docking** demo.

![](https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/6c967983-a7bd-11e5-80bf-00155d62480c.png)

The window layout contains the following elements:

## The Solution Explorer Panel

<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/7bdba3b4-a7bd-11e5-80bf-00155d62480c.png">

To display such a panel, use a single [Layout Panel](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.LayoutPanel) item.

```xaml
<dxdo:LayoutPanel Caption="Solution Explorer"/>
```

Several panels are displayed as tabs at the bottom.

<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/a426f3e0-a7bd-11e5-80bf-00155d62480c.png">

There are several ways to display tabs in DXDocking. Please refer to <a href="https://www.devexpress.com/Support/Center/p/T326792">How to display items in tabs</a> to be aware of all available options. In this scenario, use a <a href="https://documentation.devexpress.com/#WPF/CustomDocument6825">Tabbed Group</a>, as it supports reordering panels, removing and adding new panels.

```xaml
<dxdo:TabbedGroup>
    <dxdo:LayoutPanel Caption="Error List"/>
    <dxdo:LayoutPanel Caption="Output"/>
    <dxdo:LayoutPanel Caption="Breakpoints"/>
</dxdo:TabbedGroup>
```

## The Document Area
<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/ebc469da-a7bd-11e5-80bf-00155d62480c.png">
<p>While the Tabbed Group is intended to display static panels like toolbars, background information, etc., <a href="https://documentation.devexpress.com/#WPF/CustomDocument6830">Document Group</a>s can be used to display dynamic content (like opened documents) and provides the functionality similar to Visual Studio’s document area.</p>


```xaml
<dxdo:DocumentGroup>
    <dxdo:DocumentPanel Caption="MainWindow.xaml"/>
    <dxdo:DocumentPanel Caption="MainWindow.xaml.cs"/>
</dxdo:DocumentGroup>
```

To arrange these elements, use a combination of vertical and horizontal <a href="https://documentation.devexpress.com/#WPF/CustomDocument6824">Layout Group</a>s.

```xaml
<dxdo:LayoutGroup Orientation="Horizontal">
    <dxdo:LayoutGroup Orientation="Vertical">
        <dxdo:DocumentGroup>
            <dxdo:DocumentPanel Caption="MainWindow.xaml"/>
            <dxdo:DocumentPanel Caption="MainWindow.xaml.cs"/>
        </dxdo:DocumentGroup>
        <dxdo:TabbedGroup>
            <dxdo:LayoutPanel Caption="Error List"/>
            <dxdo:LayoutPanel Caption="Output"/>
            <dxdo:LayoutPanel Caption="Breakpoints"/>
        </dxdo:TabbedGroup>
    </dxdo:LayoutGroup>
    <dxdo:LayoutPanel Caption="Solution Explorer"/>
</dxdo:LayoutGroup>
```

## Auto-Hide Panels

<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/373fd0bd-a7be-11e5-80bf-00155d62480c.png">

To create such panels, define an <a href="https://documentation.devexpress.com/#WPF/CustomDocument6827">Auto-Hide Group</a> with several panels.

```xaml
<dxdo:DockLayoutManager.AutoHideGroups>
    <dxdo:AutoHideGroup DockType="Left">
        <dxdo:LayoutPanel Caption="Toolbox"/>
        <dxdo:LayoutPanel Caption="Server Explorer"/>
    </dxdo:AutoHideGroup>
</dxdo:DockLayoutManager.AutoHideGroups>
```

<!-- default file list -->
## Files to Look At

* [MainWindow.xaml](./CS/MainWindow.xaml) (VB: [MainWindow.xaml](./VB/MainWindow.xaml))
<!-- default file list end -->

## Documentation

## More Examples

- [WPF Dock Layout Manager - Populate Tabs with Items](https://github.com/DevExpress-Examples/wpf-dock-layout-manager-populate-tabs-with-items)
