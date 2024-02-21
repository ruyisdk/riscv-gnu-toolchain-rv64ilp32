RUYISDK RV64ILP32 GNU工具链说明
=============================

欢迎使用RV64ILP32工具链，你可以从 直接下载[release工具](https://github.com/ruyisdk/riscv-gnu-toolchain-rv64ilp32/releases/tag/2024.02.21)或自行构建

### 本地构建

使用git工具下载本仓库

    $ git clone https://github.com/ruyisdk/riscv-gnu-toolchain-rv64ilp32.git

**整个仓库大小约占7G空间**

### 构建准备

Ubuntu环境中需准备以下依赖软件包:

    $ sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev expect tcl

Fedora/CentOS/RHEL环境中需准备以下依赖软件包:

    $ sudo yum install autoconf automake python3 libmpc-devel mpfr-devel gmp-devel gawk  bison flex texinfo patchutils gcc gcc-c++ zlib-devel expat-devel expect tcl
    
Arch Linux环境中需准备以下依赖软件包:

    $ sudo pacman -Syyu autoconf automake curl python3 libmpc mpfr gmp gawk base-devel bison flex texinfo gperf libtool patchutils bc zlib expat expect tcl

OS X环境中需准备以下依赖软件包:

    $ brew install python3 gawk gnu-sed gmp mpfr libmpc isl zlib expat texinfo flock expect tcl

### 构建

首先配置configure参数，其中--prefix选项指定构建后工具链所在目录(make时使用-j选项可以加快构建速度):

    ./configure --prefix=/opt/riscv --with-arch=rv64gc --with-abi=ilp32d
    make -j $(nproc)

### 使用

构建完成后查看--prefix选项指定目录中的bin子目录下是否生成gcc/qemu等工具，其默认参数已开启rv64ilp32

示例:

     /opt/riscv/bin/riscv64-unknown-elf-gcc -v


### 问题解答

如果在构建或使用工具链过程中发现任何问题，请在[issue](https://github.com/ruyisdk/riscv-gnu-toolchain-rv64ilp32/issues)中提出，我们会予以及时的修复解答
