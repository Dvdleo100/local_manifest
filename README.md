# Lineage buildscripts
========================

Please note, I use ~/android/lineage-18.1 in this README but you can use whatever folder name you want.

First I recommend checking the official LineageOS wiki instructions for building for jd20 here to see what are the dependencies and how to install them
https://wiki.lineageos.org/devices/jd20/build

Also please note that repopick.sh isn't always updated. Please check LineageOS Gerrit in case there is changes to repopick topics.

Starting from zero:
---------
    mkdir -p ~/android/lineage-18.1
    cd ~/android/lineage-18.1
    repo init -u git://github.com/LineageOS/android.git -b lineage-18.1
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/lineage-jd20/local_manifests/lineage-18.1/lenovo.xml > .repo/local_manifests/lenovo.xml
    repo sync
    # OPTIONAL to use repopick unless you want to test WIP commits
    curl https://raw.githubusercontent.com/lineage-jd20/local_manifests/lineage-18.1/repopick.sh > repopick.sh
    ./repopick.sh

If you've already synced Lineage-Sources:
----------
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/lineage-jd20/local_manifests/lineage-18.1/lenovo.xml > .repo/local_manifests/lenovo.xml
    repo sync
    # OPTIONAL to use repopick unless you want to test WIP commits
    curl https://raw.githubusercontent.com/lineage-jd20/local_manifests/lineage-18.1/repopick.sh > repopick.sh
    ./repopick.sh

Building
----------
    cd ~/android/lineage-18.1
    curl https://raw.githubusercontent.com/lineage-jd20/local_manifests/lineage-18.1/jd20_eng_clean_build.sh > jd20_eng_clean_build.sh
    curl https://raw.githubusercontent.com/lineage-jd20/local_manifests/lineage-18.1/jd20_eng_dirty_build.sh > jd20_eng_dirty_build.sh
    ./jd20_eng_clean_build.sh // for jd20 clean builds
    ./jd20_eng_dirty_build.sh // for jd20 dirty builds

I made these modified scripts for convenience plus logs terminal output to files for easy scrolling later in your favorite text editor.
