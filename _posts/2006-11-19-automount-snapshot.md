---
categories:
- linux
title: Automount Snapshot
slug: snapshot 
created: 1163944500
---
<p>
Summary: I present a method for transparently auto-creating lvm snapshots on use. 
</p>

<p>
1) The problem 
</p>

<p>
I'm using rsync to transfer a backup area to another computer. The problem is that if the backup area changes during rsync then rsync complains bitterly and returns nasty error codes making me thing it has failed. 
</p>

<p>
2) The normal solution 
</p>

<p>
The "normal" solution (for those who run Linux Logical Volume Manager, that is) is to create a <a href='http://www.tldp.org/HOWTO/LVM-HOWTO/snapshotintro.html'>"snapshot"
volume </a>. 
</p>

<p>
The problem with the "normal" solution is that someone has to manage the snapshots -- and I don't like coupling the thing which performs the backup with the rest of the system. That increases system complexity. 

</p>

<p>
3) My "hack" 
</p>

<p>
So, I realized that I could use the automounter (autofs) to do what I needed. If the map for an automounter mount point is executable it is called as a script and can return what to link. Eureka! 
</p>

<p>
So my solution was to create an automounter executable map that <strong>creates </strong>the snapshot and returns it based on the request. In other words, you add the following to your automount master file: 
</p>

<p>

/mnt/path /etc/autofs/auto.snapshot-storage 
</p>

<p>
now when you execute 
</p>

<p>
ls /mnt/path/something 
</p>

<p>
Then the text "something" is passed to <code class='inline-backtick'>/etc/autofs/auto.snapshot-storage </code>, and that script creates a snapshot partition <code class='inline-backtick'>/dev/storage/something-snap </code>based on the partition <code class='inline-backtick'>/dev/storage/something </code>and returns it to be mounted. 

</p>

<p>
If one previously existed that previous one gets removed. 
</p>

<p>
This mount will exist as long as some process keeps <code class='inline-backtick'>/mnt/path/something </code>open. After nothing touches it for a while (how long is controled by the regular automounter timeout) then it will automatically be unmounted. When it's next mounted it will be generated again. 
</p>


