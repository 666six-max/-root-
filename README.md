利用漏洞获取临时root权限，再永久root

仅限于低版本安卓

mtk easy su v2.1.1对应的magisk版本为8.0.7
# KitKat
adb push mtk-su /data/local/tmp/
adb shell
cd /data/local/tmp
chmod 755 mtk-su
./mtk-su
mount -o remount,rw /system
cp /data/local/tmp/mtk-su /system/bin/su
dd if=/dev/block/bootdevice/by-name/boot of=/sdcard/boot.img
dd if=/dev/block/bootdevice/by-name/recovery of=/sdcard/recovery.img
