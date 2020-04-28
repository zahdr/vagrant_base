# vagrant_base
Vagrantfile to create a variable amount of ssh ready machines

## Usage
1. change "NODE_COUNT" in "Vagrantfile" to desired vm count
2. change "BOX_IMAGE" in "Vagrantfile" to desired vagrant box
3. vagrant up

## Info
- Using 256mb ram or less is crashing the vm kernel
