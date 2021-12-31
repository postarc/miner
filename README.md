# TON-Pool Miner

Miner from [TON-Pool.com](https://ton-pool.com/) and other pools

## Instructions

Download the latest release of our miner at https://github.com/TON-Pool/miner/releases , then run the corresponding command according to your operating system.

```
# Windows
miner-windows.exe run https://next.ton-pool.club <your_wallet>

# Linux
./miner-linux run https://next.ton-pool.club <your_wallet>
```

If you have updated your hardware settings (like overclocking) or if you accidentally run our miner twice, make sure to delete `benchmark_data.txt` before running it again to get optimal hashrate.

### Hive OS Configuration

Installation URL: go to [releases](https://github.com/TON-Pool/miner/releases), copy the link of any `hiveos` file.

Wallet and worker template: `%WAL%`

Pool URL: https://next.ton-pool.club

Note: The hashing algorithm will show up as darkcoin in the panel, although it is not actually.

### Rave OS Configutation

Go to [releases](https://github.com/TON-Pool/miner/releases), download a RaveOS package, and upload it to custom miners.

Create a new wallet, select our mining pool, and the newly uploaded miner, and you're ready to start mining.

### Usage 

```miner.exe [-h] [-p PLATFORM] [-d DEVICE] [-t THREADS] [--stats]
                 [--stats-devices] [--debug] [--silent]
                 POOL WALLET```

positional arguments:

  POOL             Pool URL
  
  WALLET           Your wallet address
  

optional arguments:

  -h, --help       show this help message and exit
  
  -p PLATFORM      Platform ID List, separated by commas (e.g. 0,1).
  
  -d DEVICE        Device ID List, separated by commas (e.g 0-0,1,2-1). You
                   can use A-B where A is platform ID and B is device ID.
                   
  -t THREADS       Number of threads. This is applied for all devices.
  
  --stats          Dump stats to stats.json
  
  --stats-devices  Dump devices information to devices.json
  
  --debug          Show all logs
  
  --silent         Only show warnings and errors

## Run Python code

If you want to debug the miner, you can run the Python code directly.

You need to have Python 3 and packages `pyopencl`, `numpy`, and `requests` installed.

For Linux users, you can run `pip3 install pyopencl numpy requests` to install the packages. If you are running old version of Python, try `pip3 install "pyopencl<2018.3"` and `pip3 install "numpy<1.15"`.

For Windows users, you can run `pip3 install numpy requests` to install the later two packages. You need to go to https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyopencl and download an `pyopencl` binary.

The command is

```
python3 miner.py [pool addr] [wallet address]
```

An optional dependency is `websocket-client`, if you install it you can get more timely job fetching.

## Dev Fee

No fee

## License

GPLv3
