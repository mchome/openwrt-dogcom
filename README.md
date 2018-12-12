# openwrt-dogcom
[dogcom](https://github.com/mchome/dogcom.git) is [drcom-generic](https://github.com/drcoms/drcom-generic) implementation in C.

### To build:

```bash
# download toolchain (ar71xx as an example)
  wget https://mirrors.tuna.tsinghua.edu.cn/lede/releases/18.06.1/targets/ar71xx/generic/openwrt-sdk-18.06.1-ar71xx-generic_gcc-7.3.0_musl.Linux-x86_64.tar.xz
  xz -d *.tar.xz && tar -xvf *.tar
# remove the tarball archive as you wish
  rm -f *Linux-x86_64.tar
# preconf
  cd openwrt-sdk-18.06*
  git clone https://github.com/Mirr0ch1/openwrt-dogcom.git package/openwrt-dogcom
# mark dogcom as 'modular' under 'Network' section of menuconfig
  make menuconfig
# then compile, the ipk will be generated
  make package/openwrt-dogcom/compile
```

### To start:

put this under `/etc/rc.local`

```bash
dogcom -m dhcp -c /etc/drcom.conf -d
```

### License:

![AGPL V3](https://cloud.githubusercontent.com/assets/7392658/20011165/a0caabdc-a2e5-11e6-974c-8d4961c7d6d3.png)
