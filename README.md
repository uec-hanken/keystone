# Keystone: An Open-Source Secure Enclave Framework for RISC-V Processors

![Documentation Status](https://readthedocs.org/projects/keystone-enclave/badge/)
[![Build Status](https://travis-ci.org/keystone-enclave/keystone.svg?branch=master)](https://travis-ci.org/keystone-enclave/keystone/)

Visit [Project Website](https://keystone-enclave.org) for more information.

`master` branch is for public releases.
`dev` branch is for development use (up-to-date but may not fully documented until merged into `master`).

# Documentation

See [docs](http://docs.keystone-enclave.org) for getting started.

# Fast compilation instructions

Install dependencies

```shell
sudo apt update
sudo apt install autoconf automake autotools-dev bc \
bison build-essential curl expat libexpat1-dev flex gawk gcc git \
gperf libgmp-dev libmpc-dev libmpfr-dev libtool texinfo tmux \
patchutils zlib1g-dev wget bzip2 patch vim-common lbzip2 python \
pkg-config libglib2.0-dev libpixman-1-dev libssl-dev screen \
device-tree-compiler expect makeself unzip cpio rsync cmake p7zip-full
```

Get the repository

```shell
git submodule update --init --recursive
```

Compile the Keystone SDK for 32-bits

```shell
cd sdk
mkdir install
export KEYSTONE_SDK_DIR=$(pwd)/install
mkdir build
cd build
cmake .. -DRISCV32=y
make
make install
```

Compile the Keystone SDK for 64-bits

```shell
cd sdk
mkdir install
export KEYSTONE_SDK_DIR=$(pwd)/install
mkdir build
cd build
cmake ..
make
make install
```

Compile for 32-bits

```shell
export KEYSTONE_SDK_DIR=$(pwd)/sdk/install
mkdir build
cd build
cmake .. -DRISCV32=y
make
make image
```

Compile for 64-bits

```shell
export KEYSTONE_SDK_DIR=$(pwd)/sdk/install
mkdir build
cd build
cmake ..
make
make image
```


# Contributing

See CONTRIBUTING.md

# Citation

If you want to cite the project, please use the following bibtex:

```
@inproceedings{lee2019keystone,
    title={Keystone: An Open Framework for Architecting Trusted Execution Environments},
    author={Dayeol Lee and David Kohlbrenner and Shweta Shinde and Krste Asanovic and Dawn Song},
    year={2020},
    booktitle = {Proceedings of the Fifteenth European Conference on Computer Systems},
    series = {EuroSys’20}
}
```
