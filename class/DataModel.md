---
title: "DataModel"
superclass: "ServiceProvider"
---

All OpenBlox games have a singleton DataModel instance that provides, as a [ServiceProvider]({{< relref "ServiceProvider.md" >}}), access to all the game services. It is designated in scripts by the global variables {{%var%}}Game{{%/var%}} and {{%var%}}game{{%/var%}}.

## Properties

{{% property bool RobloxCompatMode %}}

The value of this property determines whether or not Roblox compatibility mode is enabled. This defaults to false, but could be true on load if the file opened was in Roblox XML format.

## Methods

{{% method void SetTitle "string title" %}}

This method sets the title of the game window to the value provided by {{%var%}}title{{%/var%}}.

{{% method string GetTitle %}}

This method returns the title of the game window.

{{% method bool IsLoaded %}}

This method returns `true` if the DataModel is loaded, otherwise `false`. Currently, this method is a stub.

{{% method string GetMessage %}}

This method returns the status message of the DataModel.

{{% method void SetMessage "string title" %}}

This method sets the status message of the DataModel to {{%var%}}title{{%/var%}}.

{{% method void ClearMessage %}}

This method clears the status message of the DataModel.

{{% method void Shutdown "int statusCode" %}}

This method shuts down the DataModel and causes the game to exit. If a status code is passed, some client implementations return that as an exit code to the operating system. If it is not set, 0 is used.

{{% method double GetFPS %}}

This method returns the last recorded frame rate in frames per second. On the server, this will always return `-1`.

## Events

{{% event Loaded %}}

This event is fired when the DataModel is loaded. This happens any time a file is loaded (with internal engine methods) or all known instances are downloaded from a server.
