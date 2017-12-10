---
title: Viewport
---

The Viewport type is used to represent the two-dimensional area that a [Camera]({{< relref "class/Camera.md" >}}) renders to.

## Properties

{{% property Color3 BackgroundColor %}}

The value of this property determines the color of negative space when rendering. It defaults to a value equal to `Color3.new(0, 0, 0)`.

{{% property OrientationMode OrientationMode %}}

The value of this property determines the orientation (rotation factor) of the screen.

{{% property bool ShadowsEnabled %}}

The value of this property determines whether shadows will be rendered in this viewport.

{{% property bool SkiesEnabled %}}

The value of this property determines whether the skybox, if any, is rendered in this viewport.

## Methods

{{% method int GetActualHeight %}}

This method returns the width of this viewport, in pixels.

{{% method int GetActualLeft %}}

This method returns the left position of this viewport, in pixels.

{{% method int GetActualTop %}}

This method returns the top position of this viewport, in pixels.

{{% method int GetActualWidth %}}

This method returns the width of this viewport, in pixels.

{{% method double GetHeight %}}

This method returns the relative height of this viewport to the render target.

{{% method double GetLeft %}}

This method returns the left position of this viewport, relative to the render target.

{{% method double GetTop %}}

This method returns the top position of this viewport, relative to the render target.

{{% method double GetWidth %}}

This method returns the relative width of this viewport to the render target.
