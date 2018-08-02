---
title: "ObjectValue"
superclass: "BaseValue"
---

The ObjectValue class provides a way for developers to store references to instances within the DataModel.

## Properties

{{% property Instance Value %}}

This property holds a reference to an Instance which can be accessed or changed by other scripts. The referenced instance doesn't have to be in the DataModel, however it will not be serialized if it is not in the DataModel. The default value is nil.
