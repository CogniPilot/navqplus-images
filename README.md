# Image Release Details

## 24.04.02-Jazzy
- Force Performance mode on NavQPlus
- `jazzy-241107112629-f5fbb06c28`

## 24.04.01-Jazzy
- Initial release for 24.04 jazzy on NavQPlus
- `jazzy-240925145528-b2c2ee4acb`

# General for NavQPlus 24.04 ROS 2 Jazzy images on 6.6.x kernels
See releases

## Flash image with `uuu` to emmc
### Boot switches
Make sure boot switches are in flash mode:
![image](https://user-images.githubusercontent.com/10233412/235987123-838d5295-149f-4258-b98f-96aa24345b35.png)
| Mode  | Switch 1 | Switch 2 |
| ----- | -------- | -------- |
|  SD   |    ON    |    ON    |
| eMMC  |    OFF   |    ON    |
| Flash |    ON    |    OFF   |
### Uncompress image for flashing faster
```bash
unzstd navqplus-24.04-jazzy-<date>-<commit_hash>.wic.zst
```
### Flash image with `uuu` to emmc
```bash
sudo ./uuu -b emmc_all navqplus-24.04-jazzy-<date>-<commit_hash>.bin-flash_evk navqplus-24.04-jazzy-<date>-<commit_hash>.wic
```
## Build steps for current image release on native 24.04 system host:
#### Run 24.04 Jazzy build script on local system
```bash
sudo apt-get install -y gawk wget diffstat unzip texinfo \
    gcc-multilib build-essential chrpath socat file cpio python3 \
    python3-pip python3-pexpect xz-utils debianutils iputils-ping \
    libsdl1.2-dev xterm tar locales net-tools rsync sudo vim curl zstd \
    liblz4-tool libssl-dev bc lzop libgnutls28-dev efitools

wget -q https://raw.githubusercontent.com/NXPHoverGames/meta-nxp-mr/refs/heads/lf-6.6.23-2.0.0-scarthgap/scripts/build.sh
chmod a+x build.sh
./build.sh
```
