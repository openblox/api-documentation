---
title: "ContentProvider"
superclass: "Instance"
---

The ContentProvider class provides scripts access to internal information about assets loaded and grants the ability to load assets from scripts.

## Properties

{{% property int RequestQueueSize %}}

The value of this property is equivalent to the number of asset requests enqueued. It cannot be changed.

## Methods

{{% method string GetAsset "string url" %}}

This method loads content from the location given as {{%var%}}url{{%/var%}}. The {{%var%}}url{{%/var%}} argument can be any string, but if you haven't mapped content with [PutContent](#PutContent), only protocols supported by cURL will be loaded, with the exception of the `file://` protocol or OpenBlox's own `res://` protocol, which reads from the project's "res" directory.

The `file://` protocol is disabled, and we suggest the use of the OpenBlox provided protocol instead.

{{% method void Load "string url" %}}

This method loads content and doesn't return until the content has either been loaded or an error has occurred. The {{%var%}}url{{%/var%}} argument can be any string accepted by [GetAsset](#GetAsset).

{{% method void Preload "string url" %}}

This method preloads content so that it can be quickly used at a later time. The URL can be any string accepted by [GetAsset](#GetAsset).

{{% event AssetLoaded "string url" "string reason" %}}

This event is fired when an asset loads successfully.

{{% event AssetLoadFailed %}}