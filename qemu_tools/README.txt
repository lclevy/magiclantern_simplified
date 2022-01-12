Uses Docker to build Qemu, so you must have Docker
working first.

Expects you to have these repos downloaded:
https://github.com/reticulatedpines/magiclantern_simplified
https://github.com/reticulatedpines/qemu-eos

Example install instructions.  These assume you have git >= 2.23.
If you're on older git you'll need to use git checkout instead of git switch:

mkdir magiclantern
cd magiclantern
git clone https://github.com/reticulatedpines/qemu-eos.git
cd qemu-eos
git switch qemu-eos-v4.2.1
cd ..
git clone https://github.com/reticulatedpines/magiclantern_simplified.git
cd magiclantern_simplified/qemu_tools
./build_qemu.py
unzip qemu_4.zip
QEMU_EOS_WORKDIR=/home/username/magiclantern/roms ./qemu-eos/arm-softmmu/qemu-system-arm -drive if=ide,format=raw,file=/dev/zero -M 50D,firmware=boot=0

You will want to provide better disk images!  This will be improved soon.

