# SymMeta

For uploading of various metadata with Plex into GDrive/Teamdrives.

"I am not a coder. I have barely know what I am doing. Use at your own risk!"

## Changelog v1.0
   - [Added] Script will now detect any dependencies it needs and download them.
   - [Added] Script will detect if dependencies need an upgrade and will upgrade them.
   - [Added] Script now uses a logging library that is more efficient and provides better information.
   - [Added] Script is ran through shellcheck to verify it is the most current and updated logic and bash.

### To-Do List
   - Add better logging to a log file.
   - Add apprise notifications.
   - Add error handling when files for some reason to not upload.
   - Other stuff I'm probably forgetting.

## What is it?
This script was create for the purposes of creating .bif files, otherwise known as Video Preview Thumbnails in Plex. I enjoy having them but did not want to have to use terabytes of storage to do so.

Enter my script!

# Requirements
 1. fd: https://github.com/sharkdp/fd
   - The script has a built-in check to download this.
 2. Cloudplow: https://github.com/l3uddz/cloudplow
   - The script will do a check to see if this is installed but you will need to install this yourself as there are a myriad of config settings.
   - I chose cloudplow because it's already a complete rclone wrapper and I am lazy. Thanks l3uddz!!
 3. rclone: ```curl https://rclone.org/install.sh | sudo bash```
 4. yq: https://github.com/mikefarah/yq 
   - This is renamed to yyq as there are a couple variants out there with the same name.
   - The script has a built in check to download this.
   

---

## Installation
1. `cd /opt`

2. `git clone https://github.com/Visorask/SymMeta.git`

3. `nano config.yml` Edit these settings as needed. 

4. `cd /opt/SymMeta && chmod +x symmeta`

5. Enjoy!

---

## How to use

1. First thing is you will probably want to create a specific teamdrive or use gdrive for this.
2. You will then add that rclone remote to the config file. The script will generate this folder automatically for you, as long as it's pointed at the right rclone remote.
3. At this point you should wait a minute for rclone backend to catch up and then do `cd /mnt/unionfs/` (or wherever you have your mergerfs folder) and then do `ls` to see if there is a folder called `bif` there. If there is not you need to try again.
4. Also check under `cd /mnt/local` and `ls` and see if there is a bif folder there as well.
5. Once you have the folder showing up under `/mnt/unionfs` then you can get started.
6. You will then enable `Settings -> Library -> Generate video preview thumbnails` And set it to your preference of `as a scheduled task` or `as a scheduled task and when media is added`.
7. You can then go `Plex Home -> <Target Library> -> Manage Library -> Edit -> Advanced -> Enable video preview thumbnails.`
8. Then `Plex Home -> <Target Library> -> Manage Library -> Analyze` 
  - This sometimes takes a while to start so don't get discouraged or frustrated. Refresh the page a couple of times and when you see the dashboard start spinning and it says Generating video preview thumbnails, you should be good to go.
9. At this point you can give it a while to create some .bif file before activating the script.
10. When you feel enough time has passed then you can `cd /opt/SymMeta` and run the command `./symmeta` and you should be getting output. 
11. At this point this should be everything you need to do. 

---

## I will add crontab instructions soon.


---


## Troubleshooting
Will add more as people run into any issues.