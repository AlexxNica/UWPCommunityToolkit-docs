---
permalink: /en-US/controls/dropshadowpanel.htm
title: DropShadowPanel XAML Control
description: The DropShadowPanel Control allows the creation of a drop shadow effect for any Xaml FrameworkElement in the markup.
keywords: windows, app, toolkit, DropShadowPanel, drop shadow, UWP, XAML
layout: api
search.product: eADQiWindows 10XVcnh
lang: en-us
---

# DropShadowPanel XAML Control

The **DropShadowPanel Control** allows the creation of a drop shadow effect for any Xaml FrameworkElement in the markup.
You can control the following property of the drop shadow effect : Offset, Color, Opactity and Blur Radius.

Windows Anniversary Update (10.0.14393.0) is needed to support correctly this effect.

## Syntax

{% highlight xml %}

<controls:DropShadowPanel BlurRadius="4.0"
                          ShadowOpacity="0.70"
                          OffsetX="5.0"
                          OffsetY="5.0"
                          Color="Black">
	<Image Width="200" Source="Unicorn.png" Stretch="Uniform"/>
</controls:DropShadowPanel>       

{% endhighlight %}

## Example Image

![DropShadowPanel animation]({{site.baseurl}}/resources/images/Controls-DropShadowPanel.png "DropShadowPanel")

## Example Code

[DropShadowPanel Sample Page](https://github.com/Microsoft/UWPCommunityToolkit/tree/master/Microsoft.Toolkit.Uwp.SampleApp/SamplePages/DropShadowPanel)

## Default Template 

[DropShadowPanel XAML File](https://github.com/Microsoft/UWPCommunityToolkit/blob/master/Microsoft.Toolkit.Uwp.UI.Controls/DropShadowPanel/DropShadowPanel.xaml) is the XAML template used in the toolkit for the default styling.

## Requirements (Windows 10 Device Family)

| [Device family](http://go.microsoft.com/fwlink/p/?LinkID=526370) | Universal, 10.0.14393.0 or higher |
| Namespace | Microsoft.Toolkit.Uwp.UI.Controls |

## API

* [DropShadowPanel source code](https://github.com/Microsoft/UWPCommunityToolkit/tree/master/Microsoft.Toolkit.Uwp.UI.Controls/DropShadowPanel)
* [DropShadowPanel API documentation]({{site.baseurl}}/{{page.lang}}/api/Microsoft_Toolkit_Uwp_UI_Controls_DropShadowPanel.htm)
