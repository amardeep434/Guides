# Guides
#Guide to build cm-13.0 with my commits :)
==============
#Install your Linux platform 
  Platform used by me (Ubuntu 14.04lts)
  
#  Setup Build Environment

sudo apt-get install bison build-essential curl flex git gnupg gperf libesd0-dev liblz4-tool libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop openjdk-7-jdk openjdk-7-jre pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev g++-multilib gcc-multilib lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache libgl1-mesa-dev libxml2-utils xsltproc unzip && cd && mkdir ~/bin && PATH=~/bin:$PATH && mkdir -p ~/android/cm13 && curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo && cd ~/android/cm13

#Setup CM Branch & get the roomservice.xml

git config --global user.email "your@email.com" && git config --global user.name "YourName" && cd ~/android/cm13 && repo init -u git://github.com/CyanogenMod/android.git -b cm-13.0 && mkdir -p ~/android/cm13/.repo/local_manifests && curl -L -o .repo/local_manifests/roomservice.xml -O -L https://raw.github.com/amardeep434/Guides/master/roomservice.xml && cd ~/android/cm13

#Sync up the Repo

cd ~/android/cm13 && repo sync --force-sync && cd ~/android/cm13

#Setup ccache

nano ~/.bashrc

add to the bottom of the file  (without "") "export USE_CCACHE=1"

cd ~/android/cm13 && prebuilts/misc/linux-x86/ccache/ccache -M 50G

#cm-13.0 commits (these commits are used from unity rom and temasek for bacon)

cd ~/android/cm13 && cd ~/android/cm13/build/ && git fetch https://github.com/amardeep434/android_build cm-13.0 && git cherry-pick 2a99df952a9ed88986e17391dd062fdc674c28bb && cd ~/android/cm13/build/ && git fetch https://github.com/amardeep434/android_build cm-13.0 && git cherry-pick 000904b8137d26360ad4c87ae27a00773801eaa7 && cd ~/android/cm13/build/ && git fetch https://github.com/amardeep434/android_build cm-13.0 && git cherry-pick 62d88fd217043b098462dc8f395721b73e6bd820 && cd ~/android/cm13/build/ && git fetch https://github.com/amardeep434/android_build cm-13.0 && git cherry-pick 2fa75f17a809b8ad481a92fbf76335e128cf15bc && cd ~/android/cm13/packages/apps/Settings && git fetch https://github.com/amardeep434/android_packages_apps_Settings cm-13.0 && git cherry-pick cf01a7e06b82903f2374d56c2daf981f29b1d964 && cd ~/android/cm13/packages/apps/Settings && git fetch https://github.com/amardeep434/android_packages_apps_Settings cm-13.0 && git cherry-pick daee39a9053b847992f128d034a31346a65bf9a7 && cd ~/android/cm13/packages/apps/Settings && git fetch https://github.com/amardeep434/android_packages_apps_Settings cm-13.0 && git cherry-pick 2c00f1ed4e2c9cd52988d2839919d0617ef3bf5c && cd ~/android/cm13/packages/apps/Settings && git fetch https://github.com/amardeep434/android_packages_apps_Settings cm-13.0 && git cherry-pick 7bc3c95f022b081f79ced64ef8fc1ef56b7994ea && cd ~/android/cm13/vendor/cm && git fetch https://github.com/amardeep434/android_vendor_cm cm-13.0 && git cherry-pick 89405f4967b4a6bc863e3c8c9d782353ab110dd3 && cd ~/android/cm13/vendor/cm && git fetch https://github.com/amardeep434/android_vendor_cm cm-13.0 && git cherry-pick ffcf2a6de8f98623648d835809b7d0649f0ff536 && cd ~/android/cm13/frameworks/base && git fetch https://github.com/amardeep434/android_frameworks_base cm-13.0 && git cherry-pick 0cd5c6920df72982bcef60770103f2ecea52bffd && cd ~/android/cm13/frameworks/base && git fetch https://github.com/amardeep434/android_frameworks_base cm-13.0 && git cherry-pick 63cf9c3cf81f39f794c4fd99a3bdc085fa9543b0 && cd ~/android/cm13/frameworks/base && git fetch https://github.com/amardeep434/android_frameworks_base cm-13.0 && git cherry-pick 2381a1ff273be8d58da881788fd2f63cffe423b1 && cd ~/android/cm13/frameworks/base && git fetch https://github.com/sultanxda/android_frameworks_base cm-12.1 && git cherry-pick 0cbd4a88767d78640b7dd391674575f7d5e517e6 && cd ~/android/cm13/kernel/oneplus/msm8974 && git fetch https://github.com/amardeep434/android_kernel_oneplus_msm8974 cm-13.0 && git cherry-pick 8111396b7d29fa4de067a9356ed1d4f60b804fa4 && cd ~/android/cm13/kernel/oneplus/msm8974 && git fetch https://github.com/amardeep434/android_kernel_oneplus_msm8974 cm-13.0 && git cherry-pick ced5b9950de1d6c321b7209019b51cf11630eb56 && cd ~/android/cm13/kernel/oneplus/msm8974 && git fetch https://github.com/amardeep434/android_kernel_oneplus_msm8974 cm-13.0 && git cherry-pick 83d8d1ce7bb2b1548cf10e370d24cbd8867f627b && cd ~/android/cm13/kernel/oneplus/msm8974 && git fetch https://github.com/amardeep434/android_kernel_oneplus_msm8974 cm-13.0 && git cherry-pick 91f14a5e64417c478af706a10fdf782a68d0b008 && cd ~/android/cm13/device/oneplus/bacon && git fetch https://github.com/amardeep434/android_device_oneplus_bacon cm-13.0 && git cherry-pick c013cc57be9d156b480dfcd362ad56cb2fca039c && cd ~/android/cm13/device/oneplus/bacon && git fetch https://github.com/amardeep434/android_device_oneplus_bacon cm-13.0 && git cherry-pick d381133d635057dcb3f263e788fdd4b9f2554327 && cd ~/android/cm13/device/oneplus/bacon && git fetch https://github.com/amardeep434/android_device_oneplus_bacon cm-13.0 && git cherry-pick 33c1ba20bf92547a3e790199b4b8809dc44b100a && cd ~/android/cm13/device/oneplus/bacon && git fetch https://github.com/amardeep434/android_device_oneplus_bacon cm-13.0 && git cherry-pick d40754e1561c78049a0d31e8358548755fc68a86 && cd ~/android/cm13/device/oneplus/bacon && git fetch  https://github.com/amardeep434/android_device_oneplus_bacon cm-13.0 && git cherry-pick a0992674be8b9e5f54bae660e2bd4b32d2616aac && cd ~/android/cm13/device/oneplus/bacon && git fetch https://github.com/amardeep434/android_device_oneplus_bacon cm-13.0 && git cherry-pick 75f43ea247a3b7d5405789cb1afcc738647de027 && cd ~/android/cm13/device/oppo/common && git fetch https://github.com/amardeep434/android_device_oppo_common cm-13.0 && git cherry-pick d756baef9a46d67632353602d1ae41ac9ed8cecf && cd ~/android/cm13/

#Build ROM

cd ~/android/cm13 && make clean && export USE_CCACHE=1 && source build/envsetup.sh && breakfast bacon && croot && brunch bacon
