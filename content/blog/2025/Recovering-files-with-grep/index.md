+++
title =  "Recovering files with grep"
date =  2025-06-21
[taxonomies]
tags = ["Linux"]
[extra]
+++

Whilst I was tidying up my docker compose file, I somehow managed to delete a portion of it without noticing. I only realised this when I tried to run the docker compose command and it failed due to a syntax error about volumes. I thought that was strange as I hadn't been editing anything about volumes. I opened it up and discovered it started part way through a image's config. Oh Dear.

I started searching for ways to recover files on linux, and came across this stackexchange [thread](https://unix.stackexchange.com/questions/149342/can-overwritten-files-be-recovered/405948#405948), and thought I'd give it a go.

The line of interest is:

```bash
grep -i -a -B100 -A100 'a string unique to your file' /dev/sda1 | strings > /tmp/my-recovered-file
```

I then searched that recovered file for a unique part of my docker-compose.yml file.

This grep command is searching the raw data from the partition and adding 100 lines before and after it into the text file. The resultant file is big and messy, but it did contain the text I was looking for. I then copied the relevant sections back into my docker-compose.yml file and it worked!

I did benefit from an old backup of my docker-compose file on a github repo as a reference, but it was 5 years out of date. Needless to say I've updated mu bacup to the latest file.

Linux is amazing. 🤓
