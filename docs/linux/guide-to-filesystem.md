# 如何拓展lvm（逻辑卷），并应用更新到filesystem(文件系统)

查看当前逻辑卷容量
```
lvdisplay


  LV Path                /dev/ubuntu-vg/ubuntu-lv
    LV Name                ubuntu-lv
    VG Name                ubuntu-vg
    LV UUID                1etXme-8GZu-3dUd-8i8P-xbCJ-ODz1-og491d
    LV Write Access        read/write
    LV Creation host, time ubuntu-server, 2019-04-27 04:04:04 +0000
    LV Status              available
    # open                 1
    LV Size                4.00 GiB
    Current LE             2048
    Segments               1
    Allocation             inherit
    Read ahead sectors     auto
    - currently set to     256
    Block device           253:0
```

拓展容量

```
lvextend -L+4G /dev/ubuntu-vg/ubuntu-lv
```


> 如果提示Insufficient free space: 1280 extents needed, but only 1279 available。原因在于逻辑卷容量的最大值取决于其录属的partion分区大小。
你需要重新对你的分区进行容量分配了。

确认是否增加成功


```
lvdisplay

--- Logical volume ---
  LV Path                /dev/ubuntu-vg/ubuntu-lv
  LV Name                ubuntu-lv
  VG Name                ubuntu-vg
  LV UUID                1etXme-8GZu-3dUd-8i8P-xbCJ-ODz1-og491d
  LV Write Access        read/write
  LV Creation host, time ubuntu-server, 2019-04-27 04:04:04 +0000
  LV Status              available
  # open                 1
  LV Size                8.00 GiB
  Current LE             2048
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           253:0
```

将调整应用到文件系统

```
resize2fs /dev/ubuntu-vg/ubuntu-lv
```

完成。
