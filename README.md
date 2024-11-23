# Libra C++ implementation

This repo is built on top of [Libra](https://github.com/sunblaze-ucb/Libra.git)

## Prerequisites

On Debian based systems, you can run the following command:
```
./setup.sh
``` 
This script will change your default clang compiler to clang-7.

Or:
```
apt update
apt -y install cmake make git clang++-7 libgmp-dev g++ parallel
```

In other words, you'll need a C++11-compatible compiler (we use clang-7) (g++ 5, 6, or 7 will work).

Add dependant libraries:
```
git submodule init && git submodule update
```

## Building

The top-level Makefile in this directory will build everything below. Just run

    cmake .
    make -j4        # for example

## Testing

### SHA256
    cd tests/SHA256
    python build.py
    python run.py

use `sudo` if necessary.

## Known issue

Due to optimizations to the system, we cannot process small witness(input). We will pad the input to appropriate size. This will slow down on small instances and produce different result compared to the paper. Large instance remains the same.
