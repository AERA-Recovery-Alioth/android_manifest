# AERA Recovery for Alioth

Android 16 AERA recovery sources for POCO F3 / Redmi K40 and Mi 11X.
The manifest includes the Alioth device tree and compatible Qualcomm graphics
and boot-control dependencies. Maintained sources follow named branches;
unchanged shared sources use their original repositories.

```sh
mkdir -p ~/aera-alioth
cd ~/aera-alioth
repo init -u https://github.com/AERA-Recovery-Alioth/android_manifest.git -b aera-16.0
repo sync -c --no-clone-bundle --no-tags -j8
source build/envsetup.sh
export AERA_BUILD_TYPE=Alpha AERA_USE_BUSYBOX_BINARY=1
lunch twrp_alioth-bp2a-user
m -j8 adbd bootimage sepolicy_neverallows sepolicy_test sepolicy_dev_type_test
```

Raw recovery-as-boot output is `out/target/product/alioth/boot.img`.
Temporary testing uses `fastboot boot`; only native AERA image/installer
packaging is distributed. Device compatibility is documented in the device
repository. Release attachments record exact tested source revisions and
validation results without adding snapshot-update commits to this manifest.

Original project authorship and license notices remain intact.
