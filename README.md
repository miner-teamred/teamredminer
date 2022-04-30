# teamredminer v0.9.4.2
This is an optimized miner for AMD GPUs and Xilinx FPGAs created by todxx and kerney666.

Below is a list of mining operating systems and management software that have built-in support for teamredminer:
 - [MMPOS](https://mmpos.eu/)
 - [SimpleMining OS](https://simplemining.net/)
 - [Hive OS](https://hiveos.farm/)
 - [Minerstat](https://minerstat.com/)
 - [Awesome Miner](https://www.awesomeminer.com/)
 - [PiMP OS](https://getpimp.org/)
 - [RaveOS](https://raveos.com/)

This miner supports a range of algorithms.  Please see the list below for details.
The miner is configured via command line only, please run with the --help option to print a short help message for how to use the command line options.

## GPU Support

GPUs supported and tested:
- Navi - RX 5700(XT)/5600(XT)/5500(XT) for supported algos in the table below.
- Big Navi - RX 6900XT, RX 6800(XT), RX 6700(XT), RX6600XT - same support as for Navi.
- Vega - RX Vega 64/56, Vega FE, Radeon VII (Vega 2)
- Polaris - RX 580/480/570/470/560/460/550
- Fiji - R9 Fury/Fury X/Nano, MI8 (supported but with very limited testing).
- Tonga/Antigua - R9 285/285X/380/380X, W7100, S7150 (beta support from 0.8.2. Only ethash+kawpow available.)

Supported GPU algorithms and their respective dev fees:

|      GPU Algorithm        |  Fee |
| ------------------------- | ---- |
| Ethash on Polaris GPUs    | 0.75%|
| Ethash on all other GPUs  | 1.0% |
| Kawpow                    | 2.0% |
| Verthash                  | 2.0% |
| Autolykos2                | 2.0% |
| Ton                       | 1.0% |
| Nimiq                     | 2.5% |
| Cryptonight R             | 2.5% |
| Cryptonight v8 upx2       | 2.5% |
| Cryptonight v8 turtle     | 2.5% |
| Cryptonight v8 half       | 2.5% |
| Cryptonight v8 double     | 2.5% |
| Cryptonight v8 rwz        | 2.5% |
| Cryptonight v8            | 2.5% |
| Cryptonight heavy         | 2.5% |
| Cryptonight haven         | 2.5% |
| Cryptonight saber         | 2.5% |
| Cryptonight conceal       | 2.5% |
| Chukwa-512 (Turtlecoin)   | 2.5% |
| Chukwa-1024 (Turtlecoin)  | 2.5% |
| x16r                      | 2.5% |
| x16rv2                    | 2.5% |
| x16s                      | 2.5% |
| x16rt                     | 2.5% |
| MTP                       | 2.5% |
| Cuckatoo31                | 2.5% |
| Cuckarood29               | 2.5% |
| Lyra2rev3                 | 2.5% |
| Lyra2z                    | 3.0% |
| Phi2                      | 3.0% |

Some algorithms are not supported on some GPU architectures and/or drivers.  Below is the compatiblity table:

|                          | Navi | Vega | Polaris | Fiji | Tonga |
| ------------------------ |:----:|:----:|:-------:|:----:|:-----:|
| Ethash                   |  Y   |  Y   |   Y     |   Y  |   Y   |
| Kawpow                   |  Y   |  Y   |   Y     |   Y  |   Y   |
| Verthash                 |  Y   |  Y   |   Y     |   Y  |   N   |
| Autolykos2               |  Y   |  Y   |   Y     |   Y  |   Y   |
| Firopow                  |  Y   |  Y   |   Y     |   Y  |   Y   |
| Ton                      |  Y   |  Y   |   Y     |   Y  |   Y   |
| Nimiq                    |  Y   |  Y   |   Y     |   Y  |   N   |
| Cryptonight R            |  N   |  L   |   L     |   L  |   N   |
| Cryptonight v8 upx2      |  N   |  L   |   L     |   L  |   N   |
| Cryptonight v8 turtle    |  N   |  L   |   L     |   L  |   N   |
| Cryptonight v8 half      |  N   |  L   |   L     |   L  |   N   |
| Cryptonight v8 double    |  N   |  L   |   L     |   L  |   N   |
| Cryptonight v8 rwz       |  N   |  L   |   L     |   L  |   N   |
| Cryptonight v8           |  N   |  L   |   L     |   L  |   N   |
| Cryptonight heavy        |  N   |  L   |   L     |   L  |   N   |
| Cryptonight haven        |  N   |  L   |   L     |   L  |   N   |
| Cryptonight saber        |  N   |  L   |   L     |   L  |   N   |
| Cryptonight conceal      |  N   |  L   |   L     |   L  |   N   |
| Chukwa-512               |  N   |  L   |   L     |   L  |   N   |
| Chukwa-1024              |  N   |  L   |   L     |   L  |   N   |
| x16r                     |  N   |  Y   |   Y     |   Y  |   N   |
| x16rv2                   |  N   |  Y   |   Y     |   Y  |   N   |
| x16s                     |  N   |  Y   |   Y     |   Y  |   N   |
| x16rt                    |  N   |  Y   |   Y     |   Y  |   N   |
| MTP                      |  Y   |  Y   |   Y     |   Y  |   N   |
| Cuckatoo31               |  N   |  Y   |   Y     |   Y  |   N   |
| Cuckarood29              |  N   |  Y   |   Y     |   Y  |   N   |
| Lyra2rev3                |  N   |  L   |   L     |   L  |   N   |
| Lyra2z                   |  N   |  L   |   L     |   L  |   N   |
| Phi2                     |  N   |  L   |   L     |   L  |   N   |

Support legend:
 - Y = Supported
 - N = Not supported
 - L = Limited support: algos are supported on windows and linux with amdgpu-pro drivers, not supported on ROCm drivers.

## FPGA Support

FPGA Devices supported and tested in Linux (Windows is not currently supported):
- Xilinx Varium C1100
- SQRL Forest Kitten 33 - performance limited by product design, see guide for details
- Xilinx/TUL/Osprey U50C/ECU50

Supported FPGA algorithms and their respective dev fees:

|      FPGA Algorithm       |  Fee |
| ------------------------- | ---- |
| Ethash                    | 4.0% |

-----------

The miner reports GPU hash rates every 30 seconds.  These are the full GPU hash rates before dev fee deduction (your pool hashrate will be slightly lower). 

The miner includes a read-only api based on the sgminer-5.5 API.  Both the json and text formats are supported.  For more details, we refer to the sgminer api documentation.
The miner also includes a Claymore miner compatible API with support for a subset of the API.

For reporting bugs and/or for features requests, please open an issue on this project's github [issue tracker](https://github.com/todxx/teamredminer/issues).

For example command lines please see the batch/shell scripts in the miner download packages.
For command line options see the [USAGE.txt](USAGE.txt) file that comes with the miner.
