AOSP OREO MSM8916 Manifest 
====================

Create AOSP folder
----------------------

    mkdir ~/aosp
    cd ~/aosp
    

GIT config (nickname, e-mail)
-----------------------------

    git config --global user.email "mail@domain.com"
    git config --global user.name "login"
    

To initialize your local repository use
---------------------------------------

    repo init -u https://github.com/AOSP-Oreo-MSM8916/manifest.git -b 8.1
    

Then to sync up:
----------------

    repo sync --current-branch --no-tags --no-clone-bundle --optimized-fetch --force-broken --force-sync -j16

Build command is
----------------
    export JACK_SERVER_VM_ARGUMENTS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4000m"
    . build/envsetup.sh
    lunch aosp_$device-userdebug
    make -jx otapackage
