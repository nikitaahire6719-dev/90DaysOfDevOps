# Day 13 – Linux Volume Management (LVM)

## Overview

Today, I learned and implemented **Linux Volume Management (LVM)** through hands-on practice. LVM provides a flexible way to manage disk storage, allowing logical volumes to be created, mounted, and extended without the limitations of traditional disk partitioning.

## Topics Covered

* Introduction to Linux Volume Management (LVM)
* Physical Volume (PV)
* Volume Group (VG)
* Logical Volume (LV)
* LVM Architecture
* Storage Management Workflow

## Hands-on Tasks Completed

* Installed LVM utilities (`lvm2`)
* Inspected the current storage configuration
* Created a virtual disk using a loop device
* Initialized a Physical Volume (PV)
* Created a Volume Group (VG)
* Created a Logical Volume (LV)
* Formatted the logical volume with the ext4 filesystem
* Created a mount point and mounted the logical volume
* Verified the mounted filesystem
* Extended the logical volume
* Resized the filesystem to utilize the additional storage

## Commands Practiced

* `lsblk`
* `pvs`
* `vgs`
* `lvs`
* `pvcreate`
* `vgcreate`
* `lvcreate`
* `mkfs.ext4`
* `mkdir`
* `mount`
* `df -h`
* `lvextend`
* `resize2fs`

## Key Learnings

* Understood the complete LVM workflow: **PV → VG → LV**.
* Learned how LVM provides flexible and scalable storage management.
* Gained practical experience in creating, mounting, and extending logical volumes.

---

**#90DaysOfDevOps #DevOpsKaJosh #TrainWithShubham**
