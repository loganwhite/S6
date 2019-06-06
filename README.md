# S6: Elastic Scaling of Stateful Network Functions

# Contains
- S6 runtime library (`/core`) and souce-to-source compiler (`/gen_source`)
- A sample NF controller (`/s6ctl`)
- Sample applications (`/sample`)

# Running environment
- We have tested S6 in Ubuntu Server 16.04 LTS
- An NF instance can run as a process or a container
- We used Amazon EC2 for elastic scaling experiments (c4.xlarge)

# Compiling S6 library

## Prerequisites: basic utilities (**Using Ubuntu 16.04 LTS and the mentioned version of tools will not generate errors**)
- gcc, g++, make
- python 2.7
- python-clang-3.6 (s2s compiler) sudo apt-get install python-clang-3.6
- libclang-3.6-dev (s2s compiler) sudo apt-get install libclang-3.6-dev
- linux-headers (DPDK) sudo apt-get install linux-headers-$(uname -r)
- unzip (Rapidjson) sudo apt-get install unzip
- libssl-dev (sample applications) sudo apt-get install libssl-dev
- libpcre3-dev (DPI) sudo apt-get install libpcre3-dev
- libpcap-dev (PRAD) sudo apt-get install libpcap-dev

## Prerequisites: 3rd-party libraries
- C++ BOOST
- Rapidjson
- DPDK
- BESS (for the sample NF controller)

### Building dependent libraries (DPDK, C++ BOOST, Rapidjson)
$ ./build.py build deps

### Building BESS
https://github.com/NetSys/bess

## Building main library and apps
$ ./build.py              # build all (generating source, building core and apps)

# Running S6

## Running S6 controller
$ ./s6ctl/controller.py   # No such a file found in the directory, simply don't use it.

$ ./s6ctl                 # Use the public key method ssh login to simplify the process.
