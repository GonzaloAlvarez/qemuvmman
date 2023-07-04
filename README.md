# QEMU VM Manager
## Why
I like testing my devops configuration and ansible stuff with actual VMs. In particular when using my MacBookPro laptop.
Now, using VMs in mac is a pain in general, but doing so on M1 hardware is really horrible.
So, I built this that basically automates pulling a bunch of different images, and creating the right VMs.
And it works.

## How
First, you create a VM based on a template
```shell
$ ./vm.sh create template/debian11
```

Then, you just run it
```shell
$ ./vm.sh run VMXXXXXXX
```
where XXXXXXXX needs to be replaced with the code of the VM you just created.

And finally, you can connect via SSH
```shell
$ ./vm.sh ssh VMXXXXXXX
```

You want to connect to the VM's QEMU monitor port? Sure...
```shell
$ ./vm.sh monitor VMXXXXXXXX
```

Or maybe you just want to know if the VM is running or not
```shell
$ ./vm.sh status VMXXXXXXXX
```

After you stop a VM (right now just by connecting to it and shutting it down from inside), you can simply remove it
```shell
$ rm -Rf VMXXXXXXXX
```

And, if you want to see how many VMs you got around, well...
```shell
$ ls -1 VM*
```

And that's it.

## What's next
Not much. Extend support to custom SSH keys, non ARM images and some other customizations. But this is the basics.
