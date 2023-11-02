# Armbian - ZC-328
Armbian patches for zc-328 board (third party &amp; hobby project, not offical)

# How to use
1. Clone this repo to your local machine (or download zip file)
2. Clone (armbian repo)[https://github.com/armbian/build] to your local machine
3. Copy all files in this repo to armbian directory (e.g. /home/username/armbian/build)
4. Run armian build script to build your own image:
```
./compile.sh build BOARD=zc-328 NO_HOST_RELEASE_CHECK=yes BRANCH=current
```
5. After build process is done, you can find your image in output/images directory (e.g. /home/username/armbian/build/output/images)
6. Flash your image to SD card and enjoy it!

# Flashing to EMMC
For flashing to EMMC, you can use rkdeveloptool.   
rkdeveloptool is already included in armbian build script, so you can use it directly:  
```
# 0. Put your board into maskrom mode
#    - Connect your board to PC via USB OTG port
#    - Press and hold the "uboot" button near the EMCC chip (This is very important!)
#    - Then connect the 12V power supply

# 1. Download bootloader
/home/username/armbian/build/cache/sources/rkbin-tools/tools/rkdeveloptool db /home/username/armbian/build/cache/sources/rkbin-tools/rk32/rk3288_ubootloader_v1.01.06.bin

# 2. Flash image to EMMC
/home/username/armbian/build/cache/sources/rkbin-tools/tools/rkdeveloptool wl 0 /home/username/armbian/build/output/images/YOUR_IMAGE_FILE.img

# 3. Reboot your board.
/home/username/armbian/build/cache/sources/rkbin-tools/tools/rkdeveloptool rd

# 4. That's all. Enjoy it!
```

# License
This project is licensed under the GPLv2 License - with ABSOLUTELY NO WARRANTY. See the [LICENSE](LICENSE) file for details. 

This project is a hobby project and has nothing to do with the original manufacturer of the zc-328 board.  
Please do not contact the original manufacturer for technical support.

------------

# Armbian - ZC-328
zc-328主板的armbian补丁（这是一个第三方爱好者项目，非官方作品）

# 使用说明
1. 将本项目克隆到本地（或者下载zip文件）
2. 将armbian项目克隆到本地
3. 将本项目中的所有文件复制粘贴到armbian目录下（例如/home/username/armbian/build）
4. 运行armbian的编译脚本来编译你自己的镜像：
```
./compile.sh build BOARD=zc-328 NO_HOST_RELEASE_CHECK=yes BRANCH=current
```
5. 编译完成后，你可以在output/images目录下找到你的镜像（例如/home/username/armbian/build/output/images）
6. 将镜像烧录到SD卡，大功告成！

# 烧录到EMMC
你可以使用rkdeveloptool来烧录镜像到EMMC。  
rkdeveloptool已经包含在armbian的编译脚本中，所以你可以直接使用：  
```
# 0. 将主板进入maskrom模式
#    - 通过USB OTG口将主板连接到电脑
#    - 然后按住EMMC芯片旁边的"uboot"按钮（这一步非常重要！）
#    - 最后连接12V电源

# 1. 下载uboot
/home/username/armbian/build/cache/sources/rkbin-tools/tools/rkdeveloptool db /home/username/armbian/build/cache/sources/rkbin-tools/rk32/rk3288_ubootloader_v1.01.06.bin

# 2. 烧录镜像到EMMC
/home/username/armbian/build/cache/sources/rkbin-tools/tools/rkdeveloptool wl 0 /home/username/armbian/build/output/images/你的镜像文件.img

# 3. 重启主板
/home/username/armbian/build/cache/sources/rkbin-tools/tools/rkdeveloptool rd

# 4. 搞定，大功告成！
```

# 软件许可
本项目基于GPLv2协议发布，没有任何担保。更多详情请参阅[LICENSE](LICENSE)文件。  

本项目是一个爱好者项目，与zc-328主板的原始制造商无关。  
请不要联系原始制造商寻求技术支持。
