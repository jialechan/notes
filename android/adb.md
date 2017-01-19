adb devices
adb kill-server

ls /data/data

输入以下命令，为了在/system目录写入文件
mount -o remount,rw -t yaffs2 /dev/block/mtdblock3 /system

cat 代替cp
cat /sdcard/test.mp3 >/system/media/audio/test.mp3
