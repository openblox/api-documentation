---
title: "ServiceProvider"
superclass: "Instance"
---

This class provides methods for objects (like the [DataModel]({{< relref "DataModel.md" >}}) that provide access to services.

## Methods

{{% method Instance FindService "string className" %}}

This method will search for a service with the given class name in the children of the service provider and will return such a service if it finds it, void otherwise.

{{% method Instance GetService "string className" %}}

This method searches for a service, like [FindService](#FindService), but will create it if it does not exist yet.
