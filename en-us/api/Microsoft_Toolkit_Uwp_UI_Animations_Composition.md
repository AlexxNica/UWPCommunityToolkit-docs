---
permalink: /en-US/api/Microsoft_Toolkit_Uwp_UI_Animations_Composition.htm
title: Microsoft.Toolkit.Uwp.UI.Animations.Composition API 
description: API page for Microsoft.Toolkit.Uwp.UI.Animations.Composition
keywords: windows, app, toolkit, UWP, API
layout: default
search.product: eADQiWindows 10XVcnh
---


# Composition class

These extension methods use composition to perform animation on visuals.

## Members

The **Composition** class has this types of members

* [methods](#methods)

* [properties](#properties)

### methods

#### Offset(Windows.UI.Xaml.UIElement associatedObject,System.Double duration,System.Double delay,System.Single offsetX,System.Single offsetY,System.Single offsetZ)

Changes the Offset of the specified UI Element.

##### parameters



| name | description | type |


#### Scale(Windows.UI.Xaml.UIElement associatedObject,System.Double duration,System.Double delay,System.Single centerX,System.Single centerY,System.Single centerZ,System.Single scaleX,System.Single scaleY,System.Single scaleZ)

Scales the specified UI Element.

##### parameters



| name | description | type |


#### Rotate(Windows.UI.Xaml.UIElement associatedObject,System.Double duration,System.Double delay,System.Single value,System.Single centerX,System.Single centerY,System.Single centerZ)

Rotates the specified UI Element.

##### parameters



| name | description | type |


#### Rotate(Microsoft.Toolkit.Uwp.UI.Animations.AnimationSet animationSet,System.Double duration,System.Double delay,System.Single value,System.Single centerX,System.Single centerY,System.Single centerZ)

Rotates the specified UI Element.

##### parameters



| name | description | type |


#### Fade(Windows.UI.Xaml.UIElement associatedObject,System.Double duration,System.Double delay,System.Single value)

Changes the Opacity of the specified UI Element.

##### parameters



| name | description | type |


#### Fade(Microsoft.Toolkit.Uwp.UI.Animations.AnimationSet animationSet,System.Double duration,System.Double delay,System.Single value)

Changes the Opacity of the specified UI Element.

##### parameters



| name | description | type |


#### Scale(Microsoft.Toolkit.Uwp.UI.Animations.AnimationSet animationSet,System.Double duration,System.Double delay,System.Single centerX,System.Single centerY,System.Single centerZ,System.Single scaleX,System.Single scaleY,System.Single scaleZ)

Scales the specified UI Element.

##### parameters



| name | description | type |


#### Offset(Microsoft.Toolkit.Uwp.UI.Animations.AnimationSet animationSet,System.Double duration,System.Double delay,System.Single offsetX,System.Single offsetY,System.Single offsetZ)

Changes the Offset of the specified UI Element.

##### parameters



| name | description | type |


#### Blur(Microsoft.Toolkit.Uwp.UI.Animations.AnimationSet animationSet,System.Double duration,System.Double delay,System.Double value)

Blurs the specified framework element.

##### parameters



| name | description | type |


#### Blur(Windows.UI.Xaml.FrameworkElement associatedObject,System.Double duration,System.Double delay,System.Double value)

Blurs the specified framework element.

##### parameters



| name | description | type |


#### Parallax(Windows.UI.Xaml.UIElement element,Windows.UI.Xaml.FrameworkElement scrollerElement,System.Boolean isHorizontalEffect,System.Single multiplier)

Creates a Parallax effect on the specified element based on the supplied scroller element.

##### parameters



| name | description | type |


### properties

#### IsBlurSupported

Gets a value indicating whether the platform supports blur.

