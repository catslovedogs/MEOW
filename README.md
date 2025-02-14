
![SevenSeas Logo](https://github.com/catslovedogs/SevenSeas/blob/master/SevenSeas%20BANNER-1.png "SevenSeas Logo")


## SevenSeas

This is the official SevenSeas sourcecode repository based on https://github.com/jl777/komodo.

## Development Resources

- SevenSeas Chain Website: [https://SevenSeas.cc](https://pirate.black/)
- Komodo Platform: [https://komodoplatform.com](https://komodoplatform.com/)
- SevenSeas Blockexplorer: [https://explorer.SevenSeas.cc](https://pirate.black/)
- SevenSeas Discord: [https://SevenSeas.cc/discord](https://pirate.black/discord)
- BTT ANN: [https://bitcointalk.org/
- Mail: [marketing@SevenSeas.cc](mailto:marketing@SevenSeas.cc)
- Support: [https://SevenSeas.cc/discord](https://SevenSeas.cc/discord)
- API references & Dev Documentation: [https://docs.komodoplatform.com](https://docs.komodoplatform.com/)
- Blog: [https://SevenSeas.cc/blog](https://SevenSeas.cc/blog/)
- Whitepaper: [SevenSeas Whitepaper](https://SevenSeas.cc/whitepaper)

## Komodo Platform Technologies Integrated In SevenSeas

- Delayed Proof of Work (dPoW) - Additional security layer and Komodos own consensus algorithm  
- zk-SNARKs - Komodo Platform's privacy technology for shielded transactions  


## Tech Specification
- Max Supply: 200 million SevenSeas
- Block Time: 60s
- Block Reward: 256 SevenSeas
- Mining Algorithm: Equihash 200,9

## About this Project
SevenSeas Chain (SevenSeas) is a 100% private send cryptocurrency. It uses a privacy protocol that cannot be compromised by other users activity on the network. Most privacy coins are riddled with holes created by optional privacy. SevenSeas Chain uses zk-SNARKs to shield 100% of the peer to peer transactions on the blockchain making for highly anonymous and private transactions.

## Getting started

### Dependencies

```shell
#The following packages are needed:
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool libncurses-dev unzip git python zlib1g-dev wget bsdmainutils automake libboost-all-dev libssl-dev libprotobuf-dev protobuf-compiler libqrencode-dev libdb++-dev ntp ntpdate nano software-properties-common curl libevent-dev libcurl4-gnutls-dev cmake clang libsodium-dev -y
```

### Build SevenSeas

This software is based on zcash and considered experimental and is continuously undergoing heavy development.

The dev branch is considered the bleeding edge codebase while the master-branch is considered tested (unit tests, runtime tests, functionality). At no point of time do the Pirate developers take any responsibility for any damage out of the usage of this software.
Pirate builds for all operating systems out of the same codebase. Follow the OS specific instructions from below.

#### Linux
```shell
git clone https://github.com/SevenSeasNetwork/SevenSeas --branch master
cd SevenSeas
# This step is not required for when using the Qt GUI
./zcutil/fetch-params.sh

# -j8 = using 8 threads for the compilation - replace 8 with number of threads you want to use; -j$(nproc) for all threads available

#For CLI binaries
./zcutil/build.sh -j8

#For qt GUI binaries
./zcutil/build-qt-linux.sh -j8.
```

#### OSX
Ensure you have [brew](https://brew.sh) and the command line tools installed (comes automatically with XCode) and run:
```shell
brew update
brew upgrade
brew tap discoteq/discoteq; brew install flock
brew install autoconf autogen automake gcc@8 binutilsprotobuf coreutils wget python3
git clone https://github.com/PirateNetwork/pirate --branch master
cd pirate
# This step is not required for when using the Qt GUI
./zcutil/fetch-params.sh

# -j8 = using 8 threads for the compilation - replace 8 with number of threads you want to use; -j$(nproc) for all threads available

#For CLI binaries
./zcutil/build-mac.sh -j8

#For qt GUI binaries
./zcutil/build-qt-mac.sh -j8
```

#### Windows
Use a debian cross-compilation setup with mingw for windows and run:
```shell
sudo apt-get install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python python-zmq zlib1g-dev wget libcurl4-gnutls-dev bsdmainutils automake curl cmake mingw-w64
curl https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
rustup target add x86_64-pc-windows-gnu

sudo update-alternatives --config x86_64-w64-mingw32-gcc
# (configure to use POSIX variant)
sudo update-alternatives --config x86_64-w64-mingw32-g++
# (configure to use POSIX variant)

git clone https://github.com/SevenSeasNetwork/SevenSeas --branch master
cd SevenSeas
# This step is not required for when using the Qt GUI
./zcutil/fetch-params.sh

# -j8 = using 8 threads for the compilation - replace 8 with number of threads you want to use; -j$(nproc) for all threads available

#For CLI binaries
./zcutil/build-win.sh -j8

#For qt GUI binaries
./zcutil/build-qt-win.sh -j8
```
**SevenSeas is experimental and a work-in-progress.** Use at your own risk.

To run the SevenSeas GUI wallet:

**Linux**
`SevenSeas-qt-linux`

**OSX**
`SevenSeas-qt-mac`

**Windows**
`SevenSeas-qt-win.exe`


To run the daemon for SevenSeas:  
`SevenSeasd`
both SevenSeasd and SevenSeas-cli are located in the src directory after successfully building  

To reset the SevenSeas blockchain change into the *~/.komodo/SevenSeas* data directory and delete the corresponding files by running `rm -rf blocks chainstate debug.log komodostate db.log` and restart daemon

To initiate a bootstrap download on the GUI wallet add bootstrap=1 to the SevenSeas.conf file.


**SevenSeas is based on Komodo which is unfinished and highly experimental.** Use at your own risk.

License
-------
For license information see the file [COPYING](COPYING).


Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
