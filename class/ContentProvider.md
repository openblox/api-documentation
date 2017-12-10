---
title: "ContentProvider"
superclass: "Instance"
---

The ContentProvider class allows developers to preload, get, and overwrite content that will be loaded later on. This can be a very powerful class, if used correctly.

## Methods

{{% method string GetContent "string url" %}}

This method loads content from the location given as {{%var%}}url{{%/var%}}. The {{%var%}}url{{%/var%}} argument can be any string, but if you haven't mapped content with [PutContent](#PutContent), only protocols supported by cURL will be loaded, with the exception of the `file://` protocol or OpenBlox's own `res://` protocol, which reads from the project's "res" directory.

{{% method void Load "string url" %}}

This method loads content and doesn't return until the content has either been loaded or an error has occurred. The {{%var%}}url{{%/var%}} argument can be any string accepted by [GetContent](#GetContent).

{{% method void Preload "string url" %}}

This method preloads content so that it can be quickly used at a later time. The URL can be any string accepted by [GetContent](#GetContent).
