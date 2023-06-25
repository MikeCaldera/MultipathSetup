# MultipathSetup
Setup Multipathing in Proxmox Linux Debian for Direct Attached Storage (DAS) device
In a typical multipath configuration, you would only include the storage devices that are accessible via multiple paths. The purpose of multipathing is to provide redundancy and load balancing for these devices. If a path to a device fails, the multipath software can automatically switch to a different path, preventing downtime.

The OS disks are directly attached to your servers (Cluster example: node1, node2, and Node3) and are not part of a storage array that supports multiple paths. You would not typically include these disks in your multipath configuration. Instead, you would include the disks in your Direct Attached Storage (DAS) device, which supports multiple paths.

When configuring multipathing, you would add the World Wide Identifiers (WWIDs) of the DAS device's disks to the multipath.conf file. The multipath software would then manage these disks, providing redundancy and load balancing.

If your server node fails and the system clusters over to node2, the DAS device's disks would still be accessible via the remaining path. The multipath software would automatically switch to this path, allowing your system to continue operating without downtime.

In summary, in a typical multipath configuration, you would include the WWIDs of the DAS device's disks in the multipath.conf file, but not the WWIDs of the OS disks on node1 and node2. However, the specifics of your configuration can depend on your exact setup and the specific hardware and software you're using but for most people, this setup works well and hopefully is easy to understand now.
