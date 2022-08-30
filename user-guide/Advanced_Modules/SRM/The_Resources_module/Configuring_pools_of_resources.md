---
uid: Configuring_pools_of_resources
---

# Configuring pools of resources

This section contains the following topics:

- [Adding a pool](#adding-a-pool)

- [Configuring pool properties](#configuring-pool-properties)

- [Adding resource property definitions](#adding-resource-property-definitions)

- [Adding resources to a pool](#adding-resources-to-a-pool)
- 
- [Removing resources from a pool](#removing-resources-from-a-pool)

- [Adding a virtual function as a resource](#adding-a-virtual-function-as-a-resource)

## Adding a pool

To add a resource pool using DataMiner 10.2.0/10.1.5 or higher:

1. Make sure no existing resource pool is selected.

1. At the bottom of the resource pool pane, click the *Add* button.

1. Enter the pool name in the dialog box and click *OK*.

1. To further configure the pool, select it in the resource pool pane, then proceed with the procedures outlined below.

To add a resource pool prior to DataMiner 10.1.5:

1. At the bottom of the leftmost column in the *resources* tab, click the *Add* button.

1. Enter the pool name in the dialog box and click *OK*.

1. To further configure the pool, select it in the column on the left, then proceed with the procedures outlined below.

## Configuring pool properties

In order to add more information to a pool, for example to make it easier to filter through pools and find the pool you are looking for, you can add properties to the pool:

1. While the pool is selected, in the *properties* tab, click the *Add* button in the *Pool properties* section.

1. Fill in the name of the property, and optionally add a property value.

1. Click *OK*.

## Adding resource property definitions

In order to define properties for all resources in a pool, and optionally limit the values of the properties, you can define resource property definitions:

1. While the pool is selected, in the *properties* tab, click the *Add* button in the *Resource property definitions* section.

1. In the dialog box, fill in the name of the resource property you wish to define.

1. If you wish to restrict the possible values for the property, there are two possibilities:

   - Select *Regex pattern* and specify a regular expression that the property in question must match.

   - Select *Value list*, and, for each possible value for the property, click the *Add value* button and specify the value.

## Adding resources to a pool

To add a resource to a pool using DataMiner 10.2.0/10.1.5 or higher:

1. While the pool is selected, in the *resources* tab, click the *Add* *resource* button.

1. In the *general* subtab, configure the following fields as necessary:

   - *Name*: The name of the resource.

   - *Status*: Determines whether the resource is currently available, unavailable or in maintenance. Note that this field is no longer used in recent SRM configurations.

   - *Concurrency*: The maximum number of times the resource can be reserved at the same time.

   - *Capacity*: Add and configure the capacities of the resource. The available capacities are based on profile parameters in the Profiles module.

   - *Capability*: Add and configure the capabilities of the resource. The available capabilities are based on profile parameters in the Profiles module.

     > [!NOTE]
     > To support time-dependent capabilities that are filled in by a script when necessary, you can select *Use time-dependent* and not specify a value for the capability.

1. In the *device* subtab, configure the following fields as necessary. These fields can be optional, depending on your SRM configuration.

   - *Function*: Links the resource to an existing virtual function. The drop-down list allows you to select virtual functions based on *functions.xml* files or virtual functions with a generated protocol.

   - *Element* or *Link element*: Links the resource to an existing DataMiner element. If a link to an element has been configured already, you can clear the link by selecting *\<None>*.

   - *Instance*: If a virtual function is selected in the *Function* field, here you can select one of the available entrypoint table instances. For example, if the linked element is a provisioning element, the instance can indicate which of its provisioned elements the resource should be linked to. In case the selected virtual function does not define an entrypoint table, the drop-down box will only show the option \<none>.

   - *Function instance name*: Available from DataMiner 10.2.0 \[CU3]/10.2.6 onwards. Allows you to modify the name of the DVE linked to a function resource.

   > [!NOTE]
   >
   > - When a resource linked to a virtual function is saved, a corresponding (virtual) element is created, and its name and ID will be displayed.
   > - We highly recommend that updating the name of a function instance is done via the resource. Strictly speaking, this is also possible via the DVE parent, but if you change the name there, the resource will not be updated.

   > [!WARNING]
   > Virtual functions with generated protocol are currently still in soft launch, with the *Function* soft-launch option. For more information, see [Soft-launch options](https://community.dataminer.services/documentation/soft-launch-options/).

1. In the *properties* subtab, configure any properties if necessary. With the buttons in the lower right corner, you can add, edit and delete resource properties.

1. Click *Save* in the lower right corner.

To add a resource to a pool prior to DataMiner 10.1.5:

1. While the pool is selected, in the *resources* tab, click the *Add* button.

1. In the dialog box, fill in the resource name.

1. Optionally, the following fields can also be filled in:

   - *Status*: Determines whether the resource is currently available, unavailable or in maintenance.

   - *Element*: Links the resource to an existing DataMiner element.

   - *Concurrency*: The maximum number of times the resource can be reserved at the same time.

   - *Capacity* and the corresponding *Capacity units* (up to DataMiner 9.6.6): Limits the number of bookings possible for a resource.

   - *Capacity* (available from DataMiner 9.6.7 onwards): Allows you to select and configure a profile parameter defining the capacity of the resource.

   - *Capability* (available from DataMiner 9.6.7 onwards): Allows you to select and configure a profile parameter defining the capability of the resource.

     > [!NOTE]
     > To support time-dependent capabilities that are filled in by a script when necessary, from DataMiner 10.0.6 onwards, you can select *Use time-dependent* and not specify a value for the capability. In addition, string capabilities are supported from this version onwards.

1. If any resource property definitions have been defined, fill in the values required for the additional properties.

   > [!NOTE]
   > If you select an existing resource in the *resources* tab, you can view information on its configuration if you expand the *Properties* section at the bottom of the tab. This includes a button that allows you to quickly navigate to the element linked to the resource. Buttons are also available that allow you to add, edit or delete properties of a resource.

1. Click *OK*.

## Removing resources from a pool

Besides deleting a resource from the system, it is also possible to remove a resource from an existing resource pool using DataMiner 10.2.0/10.2.10 or higher:

1. Make sure the existing resource that you want to remove, is selected in the resource pool that you want to remove from.

1. Right-click on the selected resource and press *Remove from pool*.

   > [!NOTE]
   > The following conditions must be met in order to see the item *Remove from pool* enabled:
   > - The selected pool is not the (uncategorized) pool
   > - The user has the permission to edit resources
   > - The resource is valid, is unmodified and is existing.


## Adding a virtual function as a resource

To make it possible to schedule a virtual function as a resource, prior to DataMiner 10.2.0/10.1.5 you must add it as a resource in the *Resources* module using the procedure below. From DataMiner 10.2.0/10.1.5 onwards, you can do so as detailed in [Adding resources to a pool](#adding-resources-to-a-pool).

1. In the *Resources* tab, click the *Add function* button.

   A window will open where you can add the virtual function.

1. Select the virtual function definition and provider in the columns on the left.

   > [!NOTE]
   > Only virtual function definitions that have been set active will be listed.

1. In the *Instances* list, in the *Resource* column, click *Create*. One of the available resource instances will be selected.

   > [!NOTE]
   > If the *Create* option is not available, no more resource instances can be added for this particular function and provider.

1. Click *OK* to close the window.

1. Optionally, to customize the name of the virtual functions that will be created for this resource:

   1. Select the resource and click the *Edit* button.

   1. In the *Edit Resource* window, fill a new name in the *Name* box.

   1. Click *OK* to close the window.
