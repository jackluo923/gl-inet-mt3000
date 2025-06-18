# Converting CN -> US model on firmware 4.7+
Inspiration: https://forum.openwrt.org/t/converting-gl-inet-mt3000-beryl-ax-from-cn-to-global/165159/28

## Step 1
In `/dev/mtdblock3` binary file, there exist the keyword `CN` at the beginning of the file. The UI parses this and restrict the functionality. Changing this value to `US` remove the artificial restriction. In previous firmware version, this value is in `/dev/mtdblock2` file.

```
echo -n "US" | dd of=/dev/mtdblock3 conv=notrunc bs=1 seek=136
sync
reboot
```

## Step 2
Change the language in the GL-iNet UI to English, otherwise the VPN feature will not be available. 