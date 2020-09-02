---
date: 2006-04-03 05:38:10
layout: post
title: High Availability NFS
---

I've tried out the [high availability NFS solution detailed here](http://www.howtoforge.com/high_availability_nfs_drbd_heartbeat) and run into a few issues. It does provide a great way to get a higher degree of availability for one of the most problematic bits of infrastructure, so I don't mean to crap on the idea as a whole. But here are two issues to make sure you either check out or understand before you deploy something like this:





  * We saw write throughput cut in half when DRBD was up and running. If you've got plenty of capacity and can segment as you grow you might be more concerned with the availability than the throughput. And it's certainly possible that we could have performed some tuning to get DRBD to perform better. I'm just saying perform some benchmarks beforehand and afterward to make sure you're not impacting the system too negatively without knowing it.


  * This is a block level replication technique, so there's no guarantee that a filesystem level error that causes corruption isn't just replicated over to the failover box as it happens. True, it's much more common that the failure mode be bad blocks at the hardware level than an error at the OS level.... but once again this is block level replication. A bad block on the master side that goes undetected for even a single read/write cycle will have that incorrect information replicated to the slave. As far as I know (and I admit I haven't researched this in a while) there isn't a Linux filesystem that does end to end checksumming to prevent this kind of issue.



Just two things to keep in mind. There's some great info in that article in general, like moving the NFS runtime files out to the replicated block device and how to configure heartbeat.
