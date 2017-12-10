---
title: "Instance"
---

The Instance class is the base class of the object system. All other classes inherit, either directly or undirectly, from this class. The members that are common to all the OpenBlox objects belong to the Instance class. This is why many of the most important and most used members belong to this class.

## Properties

{{% property bool Archivable %}}

The value of this property determines whether the object can be serialized. The object will only be cloned or saved when this property is true. By default, this is true.

{{% property string ClassName %}}

The value of this property is the name of the class (e.g. "Camera") the object belongs to. It cannot be changed.

{{% property string Name %}}

The value of this property is the name of the instance. This property is used to determine which instance, if any, will be returned when indexing an instance. By default, instances are given the name of their class.

{{% property Instance Parent %}}

The value of this property is the hierarchical parent of the instance, in the scene graph. This property's default value is void.

{{% property int UseCount %}}

## Methods

{{% method void ClearAllChildren %}}

This method sets the parent of all the descendants of the object to void.

{{% method Instance Clone %}}

This method creates a new instance of the class and sets all properties to the same value as this one. All children will be cloned as well, and their [Parent](#Parent) property will be set to this instance. The parent of the new instance will be void.

If the [Archivable](#Archivable) property is false or the class is abstract or uncreatable, this method will return void. Otherwise, it will return the new instance.

{{% method void Destroy %}}

This method is used to parent the object to void and remove all references. All connections to events of this instance will be disconnected. The instance's [Parent](#Parent) property cannot be changed after this method is called.

{{% method void Remove %}}

This method sets the [Parent](#Parent) property to void and recursively calls itself on children of the instance.

{{% method Instance FindFirstChild "string name" "bool recursive = false" %}}

This method is used to find the first child of the instance with the given name. If {{%var%}}recursive{{%/var%}} is specified and true, this method will search all descendants of the instance.

{{% method "Instance[]" GetChildren %}}

This method returns all children of the instance in an array.

{{% method string GetFullName %}}

This method returns the full name of the instance. This is usually in the form "game.Service.Thing" but can return weird things when one of the ancestors of the instance is parented to void.

{{% method int GetNetworkId %}}

This method returns an integer used to represent the instance in network transactions. This can be 0 if the instance isn't assigned a network ID.

{{% method bool IsA "string className" %}}

This method returns true if this class inherits from the class of the given name. If there is no such class, this method will always return false.

{{% method bool IsAncestorOf "Instance otherInstance" %}}

This method returns true if {{%var%}}otherInstance{{%/var%}} is not void and this instance is an ancestor of {{%var%}}otherInstance{{%/var%}}.

{{% method bool IsDescendantOf "Instance otherInstance" %}}

This method returns true if {{%var%}}otherInstance{{%/var%}} is void or this instance is a descendant of {{%var%}}otherInstance{{%/var%}}.

## Events

{{% event AncestryChanged "Instance child" "Instance parent" %}}

This event is fired when the [Parent](#Parent) property of the instance or one of its ancestors is changed. The {{%var%}}child{{%/var%}} argument is the instance whose parent changed and the {{%var%}}parent{{%/var%}} argument is the new parent of {{%var%}}child{{%/var%}}.

{{% event Changed "string property" %}}

This event is fired when a property of the instance is changed. The {{%var%}}property{{%/var%}} argument is the name of the property that was changed.

{{% event ChildAdded "Instance kid" %}}

This event is fired when a child is added to the instance. The {{%var%}}kid{{%/var%}} argument is the new child.

{{% event ChildRemoved "Instance kid" %}}

This event is fired when a child is removed from the instance. The {{%var%}}kid{{%/var%}} argument is the instance whose ancestry has been changed.

{{% event DescendantAdded "Instance descendant" %}}

This event is fired when a descendant is added to the instance. The {{%var%}}descendant{{%/var%}} argument is the descendant that has been added to the instance's hierarchy.

{{% event DescendantRemoving "Instance descendant" %}}

This event is fired when a descendant of the instance is removed. The {{%var%}}descendant{{%/var%}} argument is the descendant that is being removed from the instance.
