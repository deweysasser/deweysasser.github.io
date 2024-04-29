---
excerpt: Announcing availability of a simple program to backup the output of commands
  to Amazon S3 storage.
categories:
- software
- amazon
- aws
- s3
title: Simple S3 Backup script
slug: simple s3 backup script 
created: 1437971029
---
I had a need in several different contexts for a very simple script to backup a small amount of server state to Amazon S3.  There are a number of scripts that do the basic task of "copy some files to S3", but I wanted to handle automatic rotation so I could set it up and forget about it (until something goes wrong).  There are also scripts of "backup these files to S3 with rotation".  What I actually needed was a way to do:

    ssh <some target> docker exec <some container> tar -C /var/lib/my-interesting-data -cpz .

and have that file end up in S3.

Thus, [the SimpleS3Backup](https://github.com/deweysasser/SimpleS3Backup) program came into existence by asking the question "what is the simplest thing that could possibly work?"  It's a simple python script, perhaps even too simple (I'm looking at the rotation pattern).  Anyway, grab, use and enjoy. 

It's also available by "pip install SimpleS3Backup"

You can use it like

    s3backup -bucket my-backup-bucket -path /some/place -filename backupseries.tgz ssh <IP> docker exec <CONTAINER> tar -C /app -cpz .

You'll now grow "/some/place/backupseries.tgz.1", "...2", "...0" in your S3 bucket.  (By default it rotates daily and saves the last 3 days).

