# Server VMA off
## Client VMA off
### PingPong:
command: `sudo bash -c  sockperf pp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=702616; ReceivedMessages=702615
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=691734; ReceivedMessages=691734
sockperf: [2;35m====> avg-latency=21.323 (std-dev=14.741, mean-ad=3.679, median-ad=3.201, siqr=2.226, cv=0.691, std-error=0.018, 99.0% ci=[21.277, 21.369])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 21.323 usec
sockperf: [2;35mTotal 691734 observations[0m; each percentile contains 6917.34 observations
sockperf: ---> <MAX> observation = 4943.790
sockperf: ---> percentile 99.999 = 1707.535
sockperf: ---> percentile 99.990 =  448.175
sockperf: ---> percentile 99.900 =  110.538
sockperf: ---> percentile 99.000 =   51.281
sockperf: ---> percentile 90.000 =   25.372
sockperf: ---> percentile 75.000 =   22.287
sockperf: ---> percentile 50.000 =   19.867
sockperf: ---> percentile 25.000 =   17.833
sockperf: ---> <MIN> observation =   15.178
```
### Throughput:
command: `sudo bash -c  sockperf tp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 9385544 messages sent in 30.000 sec

sockperf: Summary: Message Rate is 312849 [msg/sec]
sockperf: Summary: BandWidth is 439.180 MBps (3513.441 Mbps)
```
## Client VMA on
### PingPong:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf pp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=1280578; ReceivedMessages=1280577
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=1264027; ReceivedMessages=1264027
sockperf: [2;35m====> avg-latency=11.670 (std-dev=22.738, mean-ad=1.498, median-ad=0.928, siqr=0.646, cv=1.948, std-error=0.020, 99.0% ci=[11.618, 11.722])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 11.670 usec
sockperf: [2;35mTotal 1264027 observations[0m; each percentile contains 12640.27 observations
sockperf: ---> <MAX> observation = 5112.733
sockperf: ---> percentile 99.999 = 4389.974
sockperf: ---> percentile 99.990 =  325.950
sockperf: ---> percentile 99.900 =   43.567
sockperf: ---> percentile 99.000 =   23.870
sockperf: ---> percentile 90.000 =   12.583
sockperf: ---> percentile 75.000 =   11.651
sockperf: ---> percentile 50.000 =   10.940
sockperf: ---> percentile 25.000 =   10.359
sockperf: ---> <MIN> observation =    9.397
```
### Throughput:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf tp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 24056273 messages sent in 30.000 sec

sockperf: Summary: Message Rate is 801866 [msg/sec]
sockperf: Summary: BandWidth is 1125.666 MBps (9005.331 Mbps)
```
# Server VMA on
## Client VMA off
### PingPong:
command: `sudo bash -c  sockperf pp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=1135300; ReceivedMessages=1135299
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=1118768; ReceivedMessages=1118768
sockperf: [2;35m====> avg-latency=13.170 (std-dev=6.744, mean-ad=0.947, median-ad=0.660, siqr=0.536, cv=0.512, std-error=0.006, 99.0% ci=[13.154, 13.186])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 13.170 usec
sockperf: [2;35mTotal 1118768 observations[0m; each percentile contains 11187.68 observations
sockperf: ---> <MAX> observation = 1312.843
sockperf: ---> percentile 99.999 = 1287.084
sockperf: ---> percentile 99.990 =  208.068
sockperf: ---> percentile 99.900 =   42.074
sockperf: ---> percentile 99.000 =   17.863
sockperf: ---> percentile 90.000 =   14.201
sockperf: ---> percentile 75.000 =   13.380
sockperf: ---> percentile 50.000 =   12.633
sockperf: ---> percentile 25.000 =   12.308
sockperf: ---> <MIN> observation =   11.281
```
### Throughput:
command: `sudo bash -c  sockperf tp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 9458117 messages sent in 30.000 sec

sockperf: Summary: Message Rate is 315266 [msg/sec]
sockperf: Summary: BandWidth is 442.573 MBps (3540.585 Mbps)
```
## Client VMA on
### PingPong:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf pp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=2269571; ReceivedMessages=2269570
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=2237935; ReceivedMessages=2237935
sockperf: [2;35m====> avg-latency=6.584 (std-dev=11.775, mean-ad=0.215, median-ad=0.163, siqr=0.117, cv=1.788, std-error=0.008, 99.0% ci=[6.564, 6.604])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 6.584 usec
sockperf: [2;35mTotal 2237935 observations[0m; each percentile contains 22379.35 observations
sockperf: ---> <MAX> observation = 6176.693
sockperf: ---> percentile 99.999 =  262.144
sockperf: ---> percentile 99.990 =   20.117
sockperf: ---> percentile 99.900 =    9.868
sockperf: ---> percentile 99.000 =    7.779
sockperf: ---> percentile 90.000 =    6.777
sockperf: ---> percentile 75.000 =    6.617
sockperf: ---> percentile 50.000 =    6.487
sockperf: ---> percentile 25.000 =    6.382
sockperf: ---> <MIN> observation =    6.216
```
### Throughput:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf tp -i 172.18.200.22 -t 30 --msg-size=1472`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 24018365 messages sent in 30.000 sec

sockperf: Summary: Message Rate is 800606 [msg/sec]
sockperf: Summary: BandWidth is 1123.898 MBps (8991.181 Mbps)
```
