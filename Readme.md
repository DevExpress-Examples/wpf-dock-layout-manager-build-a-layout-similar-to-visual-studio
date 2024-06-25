<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128643021/21.1.5%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T326805)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
# WPF Dock Layout Manager - Build a Layout Similar to Visual Studio

This example uses the [DockLayoutManager](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.DockLayoutManager) control to build a layout similar to Visual Studio. 

<img src="https://user-images.githubusercontent.com/12169834/175337035-49bc2b7d-b28b-485f-b4a4-09f5951b4d51.png" width=700px/>

The window layout contains the following elements:

## The Solution Explorer Panel

<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/7bdba3b4-a7bd-11e5-80bf-00155d62480c.png">

Use a [Layout Panel](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.LayoutPanel) item to display the panel.

```xaml
<dxdo:LayoutPanel Caption="Solution Explorer"/>
```

Several panels are displayed as tabs at the bottom.

<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/a426f3e0-a7bd-11e5-80bf-00155d62480c.png">

This example uses a [Tabbed Group](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.TabbedGroup), as it allows you to reorder, remove, and add new panels.

```xaml
<dxdo:TabbedGroup>
    <dxdo:LayoutPanel Caption="Error List"/>
    <dxdo:LayoutPanel Caption="Output"/>
    <dxdo:LayoutPanel Caption="Breakpoints"/>
</dxdo:TabbedGroup>
```

## The Document Area

<img src="https://raw.githubusercontent.com/DevExpress-Examples/how-to-build-a-layout-similar-to-visual-studio-t326805/15.1.3+/media/ebc469da-a7bd-11e5-80bf-00155d62480c.png">

Use [Document Groups](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.DocumentGroup) to display dynamic content (like opened documents).


```xaml
<dxdo:DocumentGroup>
    <dxdo:DocumentPanel Caption="MainWindow.xaml"/>
    <dxdo:DocumentPanel Caption="MainWindow.xaml.cs"/>
</dxdo:DocumentGroup>
```

To arrange these elements, use a combination of vertical and horizontal [LayoutGroups](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.LayoutGroup).

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

To create these panels, define an [AutoHideGroup](https://docs.devexpress.com/WPF/DevExpress.Xpf.Docking.AutoHideGroup) that includes panels.

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

- [WPF Dock Layout Manager - Dock Items](https://docs.devexpress.com/WPF/6191/controls-and-libraries/layout-management/dock-windows)
- [WPF Dock Layout Manager - Create a Simple Layout of Dock Panes](https://docs.devexpress.com/WPF/6654/controls-and-libraries/layout-management/dock-windows/getting-started/how-to-create-a-simple-layout-of-dock-panes)

## More Examples

- [WPF Dock Layout Manager - Populate Tabs with Items](https://github.com/DevExpress-Examples/wpf-dock-layout-manager-populate-tabs-with-items)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=wpf-dock-layout-manager-build-a-layout-similar-to-visual-studio&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=wpf-dock-layout-manager-build-a-layout-similar-to-visual-studio&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
