# Install OpenClash
## Step 1
Append additional soruces to the feed distribution in `/etc/opkg/distfeeds.conf
```
src/gz openwrt_base https://downloads.openwrt.org/releases/21.02.3/packages/aarch64_cortex-a53/base
src/gz openwrt_luci https://downloads.openwrt.org/releases/21.02.3/packages/aarch64_cortex-a53/luci
src/gz openwrt_packages https://downloads.openwrt.org/releases/21.02.3/packages/aarch64_cortex-a53/packages
src/gz openwrt_routing https://downloads.openwrt.org/releases/21.02.3/packages/aarch64_cortex-a53/routing
src/gz openwrt_telephony https://downloads.openwrt.org/releases/21.02.3/packages/aarch64_cortex-a53/telephony
```

## Step 2
Update the distribution feeds
```
opkg update
```

## Step 3
Download latest openclash release from https://github.com/vernesong/OpenClash/releases and upload it to the router

## Step 4
Install the package
```
opkg install luci-app-openclash_0.46.086_all.ipk
```

## Step 5 
Openclash also expects a `core` to be available under `/etc/openclash/core/clash_meta`

### Option 1
Downlaod it from https://github.com/MetaCubeX/mihomo/releases (mihomo-android-arm64-v8-v1.19.10.gz)
```
gunzip mihomo-android-arm64-v8-v1.19.10.gz
mv mihomo-android-arm64-v8-v1.19.10 /etc/openclash/core/clash_meta
```

### Option 2
In LuCi's service pannel's OpenClash page, click `Plugin Settings` tab, `Version Update`, click `Download lLatgest Core`. This will auto-install it. 