Mounting EBS from snapshot to an EC2 instance

1. Get the information of the physical volume
   sudo pvs   
    PV         VG    Fmt  Attr PSize   PFree   
  /dev/sdb   BtcVG lvm2 a--  100.00g 1020.00m

2. List the physical volume of the volume group
   sudo lvdisplay /dev/BtcVG
     --- Logical volume ---
      LV Path                /dev/BtcVG/BtcLV
      LV Name                BtcLV
      VG Name                BtcVG
      LV UUID                dKdldP-ntOT-CUaq-gf5f-xMN3-spTF-UunAp1
      LV Write Access        read/write
      LV Creation host, time ip-172-31-25-168, 2016-1-20 01:23:38 +0000
      LV Status              available
      # open                 0
      LV Size                99.00 GiB
      Current LE             25344
      Segments               1
      Allocation             inherit
      Read ahead sectors     auto
      - currently set to     256
      Block device           253:0
      
 3. Mount using the logical volume
      sudo mount /dev/mxtVG/mxVG /data
