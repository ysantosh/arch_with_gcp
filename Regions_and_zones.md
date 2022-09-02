# Designing resilient systems
A resilient system is a system that can withstand a certain amount of failures or disruptions without interrupting your service or affecting your users' experience using your service. While Compute Engine makes every effort to prevent such disruptions, certain events are unpredictable, and it's best to be prepared for these events.

Types of failures
-----------------

At some point, one or more of your VMs might be lost due to system or hardware failures. The following list contains some types of failure scenarios that you can mitigate:

-   Unexpected single VM failure

    Unexpected single VM failures can be due to hardware or system failure. You can mitigate these events by using [persistent disks](https://cloud.google.com/compute/docs/disks/add-persistent-disk) and [startup scripts](https://cloud.google.com/compute/docs/tutorials/robustsystems#startup) to save your data and re-enable software after you restart the VM.

-   Unexpected single VM reboot

    At some point in time, you might experience an unexpected single VM failure and reboot. Unlike an unexpected single VM failure, Compute Engine automatically reboots your VM after it fails. To help mitigate these events, [back up your data](https://cloud.google.com/compute/docs/tutorials/robustsystems#backup), use [persistent disks](https://cloud.google.com/compute/docs/disks/add-persistent-disk), and use [startup scripts](https://cloud.google.com/compute/docs/tutorials/robustsystems#startup) to quickly re-configure software.

-   Zone or region failures

    Zone and region failures are rare failures that can cause all of your VMs in a given zone or region to be inaccessible or fail. To mitigate these failures, create [diversity across regions and zones](https://cloud.google.com/compute/docs/tutorials/robustsystems#distribute) and implement [load balancing](https://cloud.google.com/compute/docs/tutorials/robustsystems#loadbalancing). You should also [back up your data](https://cloud.google.com/compute/docs/tutorials/robustsystems#backup) or [replicate your persistent disks](https://cloud.google.com/compute/docs/disks#repds) across multiple zones.


To help mitigate VM failures, design your application to be resilient against failures and here are some guidelines.

# Distribute your VMs

Create VMs across more than one region and zone so that you have alternative VMs to point to if a zone or region containing one of your VMs is disrupted. If you host all your VMs in the same zone or region, you won't be able to access any of those VMs if that zone or region becomes unreachable.


## Regions
Compute Engine resources are hosted in multiple locations worldwide. These locations are composed of regions and zones. A region is a specific geographical location where you can host your resources. Regions have three or more zones. For example, the `us-west1` region denotes a region on the west coast of the United States

### Regional Resources
Resources like [static external IP addresses](https://cloud.google.com/compute/docs/ip-addresses#reservedaddress), are regional.


## Zones
The `us-west1` region denotes a region on the west coast of the United States that has three zones: `us-west1-a`, `us-west1-b`, and `us-west1-c`
[More about region and zones](https://cloud.google.com/compute/docs/regions-zones)

### Zonal Resources
Resources that live in a zone, such as [virtual machine instances](https://cloud.google.com/compute/docs/instances) or zonal [persistent disks](https://cloud.google.com/compute/docs/disks), are referred to as zonal resources.

Regional resources can be used by any resource in that region, regardless of zone, while zonal resources can only be used by other resources in the same zone.
[More information on global regional and zonal resources](https://cloud.google.com/compute/docs/regions-zones/global-regional-zonal-resources)


## Clusters
Compute Engine implements a layer of abstraction between zones and the physical clusters where the zones are hosted. A cluster represents a distinct physical infrastructure that is housed in a data center. Each zone is hosted in one or more clusters.


## Relation between Region, zones and Clusters.



Reference - 

https://cloud.google.com/compute/docs/tutorials/robustsystems

https://cloud.google.com/compute/docs/regions-zones

https://cloud.google.com/compute/docs/regions-zones/zone-virtualization
