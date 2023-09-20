# Portworx
# OUTPUT
Exporting Sharedv4 volumes externally outside kubernetes cluster nodes
[root@master-node ~]# ./nfs-mounter.sh 
NAME                 PROVISIONER                     RECLAIMPOLICY   VOLUMEBINDINGMODE   ALLOWVOLUMEEXPANSION   AGE
export-sharedv4-sc   kubernetes.io/portworx-volume   Delete          Immediate           false                  21m

NAME                  STATUS   VOLUME                                     CAPACITY   ACCESS MODES   STORAGECLASS         AGE
export-sharedv4-pvc   Bound    pvc-78c391f0-46a6-439e-9533-37d3746e8b6a   10Gi       RWX            export-sharedv4-sc   7m8s

 The export-sharedv4-pvc is now in Bound State ... 
pod/export-sharedv4-pod configured

 TARGET NFS END-POINT: 70.0.71.13
 TARGET NFS DEVICE PATH: /var/lib/osd/pxns/780959580385042137

Use the following information and commands to mount the sharedv4 Portworx volume:- 

  1. Create a mount point directory for example, mkdir /mnt/Portworx_NFS_Mount
  2. mount -t nfs 70.0.71.13:/var/lib/osd/pxns/780959580385042137 /mnt/Portworx_NFS_Mount
  3. Verify mount df -hP /mnt/Portworx_NFS_Mount
