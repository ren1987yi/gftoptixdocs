

* Variable of type NodeId : is a pointer to any element of the project, the Value property of this variable contains the NodeId of the target element,this is the simplest type of pointer(and the most similar to the pointer concept of programming languages)


* Alias : Alias is a pointer which exposes a Kind property,this Kind only exists at DesignTime and it is intended as a type hinting for the user when creating a DynamicLink to the alias content, this is the most used one as this is the only way to pass additional arguments to some elements such as Screens of a NavigationPanel or to a DialogBox.


* NodePointer : Very similar to an alias,in addition to the Kind property it exposes the NodeClass property, this is still a design time hint for the user,this allows to filter the content of the DropDown based on the Kind you specified and the face that you choose to link only Types or Instances

Once again,Aliass are the way to go in 99% of cases,both the Kind and the NodeClass property only exists at DesignTime to provide guidance to user.

