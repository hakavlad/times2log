
# times2log

[![Total alerts](https://img.shields.io/lgtm/alerts/g/hakavlad/times2log.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/hakavlad/times2log/alerts/)

Monitor and log user and system CPU times of the selected process.

`times2log` reads `/proc/[PID]/stat` to check `utime` and `stime` of the selected process.

## Options

```
$ times2log -h
usage: times2log [-h] [-p PID] [-i INTERVAL] [-l LOG]

optional arguments:
  -h, --help            show this help message and exit
  -p PID, --pid PID     PID of the process
  -i INTERVAL, --interval INTERVAL
                        output interval in seconds
  -l LOG, --log LOG     path to the log file
```

## Example

```
$ times2log -p `pidof kswapd0`
Process memory locked with MCL_CURRENT | MCL_FUTURE | MCL_ONFAULT
PID: 93, Name: kswapd0, interval: 2s, SC_CLK_TCK: 100
============================================================
       user    |      system    |        total    | interval
-------------- | -------------- | --------------- | --------
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |  161 t,  80.4% |   161 t,  80.4% | 2.0s
   0 t,   0.0% |  199 t,  99.4% |   199 t,  99.4% | 2.0s
   0 t,   0.0% |  197 t,  98.4% |   197 t,  98.4% | 2.0s
   0 t,   0.0% |  198 t,  98.9% |   198 t,  98.9% | 2.0s
   0 t,   0.0% |  150 t,  74.9% |   150 t,  74.9% | 2.0s
   0 t,   0.0% |  157 t,  78.4% |   157 t,  78.4% | 2.0s
   0 t,   0.0% |  197 t,  98.4% |   197 t,  98.4% | 2.0s
   0 t,   0.0% |   29 t,  14.5% |    29 t,  14.5% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
   0 t,   0.0% |    0 t,   0.0% |     0 t,   0.0% | 2.0s
^C--
Times for the last 32.2s:
  user:   0 ticks (0.0s), avg: 0.0%
  system: 1288 ticks (12.9s), avg: 40.0%
  total:  1288 ticks (12.9s), avg: 40.0%
```

## Requirements

- Python 3.3+

## Installation

Install
```sh
$ git clone https://github.com/hakavlad/times2log.git && cd times2log
$ sudo make install
```

Uninstall
```sh
$ sudo make uninstall
```

