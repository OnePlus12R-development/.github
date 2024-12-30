# Build LineageOS for OnePlus12R

## Prerequisites
- refer to [AOSP](https://source.android.com/docs/setup/start/requirements)

## Build
1. Initialise repo with [LineageOS](https://github.com/LineageOS/android) source code.
    ```
    repo init -u https://github.com/LineageOS/android.git -b lineage-22.1 --git-lfs --depth=1
    ```

2. Clone [local_manifests](https://github.com/OnePlus12R-development/local_manifests)
    ```
    git clone https://github.com/OnePlus12R-development/local_manifests -b lineage-22.1 .repo/local_manifests
    ```

3. Sync
    ```
    repo sync -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
    ```

4. Build
    ```
    . build/envsetup.sh
    lunch lineage_aston-ap2a-userdebug
    mka bacon
    ```
    Compiling source can take anywhere from 30 mins - 4hrs depending on how powerful your hardware is,
    After successful build, you can find your flashable rom zip at ```out/target/product/aston/```
