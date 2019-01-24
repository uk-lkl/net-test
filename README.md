# net-test: LKL on Unikraft sample

This is a LKL on Unikraft sample app.
The original "net-test" is from `tools/lkl/tests/net-test.c`,
in [lkl/linux](https://github.com/lkl/linux).
It currently supports x86/linuxu and x86/kvm.

## Build and Run

```
$ mkdir unikraft
$ cd unikraft
$ git clone git@github.com:uk-lkl/unikraft.git --branch=retrage/lkl-v2
$ mkdir libs && cd libs
$ git clone git@github.com:uk-lkl/newlib.git --branch=retrage/fix
$ git clone --recursive git@github.com:uk-lkl/lkl.git
$ cd ..
$ mkdir apps && cd apps
$ git clone git@github.com:uk-lkl/net-test.git
$ cd net-test
$ make menuconfig
# Select x86
# Select KVM guest or Linux user space
# For Linux user space, default heap size must be larger than 128MB
$ make
# For x86/linuxu,
$ ./build/net-test_linuxu-x86_64
# For x86/kvm,
$ ./run.sh
```
