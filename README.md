# MetaSym

For uploading of various metadata with Plex into GDrive/Teamdrives.

"I am not a coder. I have barely know what I am doing. Use at your own risk!"


## What is it?
This script was create for the purposes of creating .bif files, otherwise known as Video Preview Thumbnails in Plex. I enjoy having them but did not want to have to use terabytes of storage to do so.

Enter my script!

# Requirements
 1. fd: https://github.com/sharkdp/fd
   - The script has a built-in check to download this.
 2. Cloudplow: https://github.com/l3uddz/cloudplow
   - The script will do a check to see if this is installed but youw ill need to install this yourself as there are a myriad of config settings.
   - I chose cloudplow because it's already a complete rclone wrapper and I am lazy. Thanks l3uddz!!
 3. Rclone: ```curl https://rclone.org/install.sh | sudo bash```
 4. yq: https://github.com/mikefarah/yq
   - If you have Cloudbox installed then you will already have this installed.
   - If you do not have Cloudbox you must follow the below steps to install it.
   A. Install Instructions:
     - Get current version of yq: `wget -qO- https://api.github.com/repos/mikefarah/yq/releases/latest | jq -r ".assets[] | select(.name | test(\"yq_linux_amd64\")) | .browser_download_url"`
     - `sudo wget -o /usr/local/bin/ <insert above command result here>`
     - `sudo mv /usr/local/bin/yq_linux_amd64 /usr/local/bin/yyq`
     - `sudo chmod 775 /usr/local/bin/yyq`
     - `sudo chown root:root /usr/local/bin/yyq`
     - `yyq --version`
   B. We rename this due to the fact that there is 2 other versions of yq out there that are named the same.

---

## Installation
1. `cd /opt`

2. `git clone https://github.com/Visorask/SymMeta.git`

3. `nano config.yml` Edit these settings as needed. 

4. `cd /opt/SymMeta && chmod +x symmeta`

5. Enjoy!

---

## I will add more instructions soon. This is initial release.

---


## Troubleshooting
Will add more as people run into any issues.