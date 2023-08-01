# Server-side VMA off
Server command: `sudo sockperf sr -i 172.18.200.22`
## Client VMA off
### PingPong:
command: `sudo bash -c  sockperf pp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=957581; ReceivedMessages=957580
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=946153; ReceivedMessages=946153
sockperf: [2;35m====> avg-latency=15.562 (std-dev=10.236, mean-ad=2.187, median-ad=1.878, siqr=1.317, cv=0.658, std-error=0.011, 99.0% ci=[15.535, 15.589])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 15.562 usec
sockperf: [2;35mTotal 946153 observations[0m; each percentile contains 9461.53 observations
sockperf: ---> <MAX> observation = 3955.398
sockperf: ---> percentile 99.999 = 1182.275
sockperf: ---> percentile 99.990 =  315.676
sockperf: ---> percentile 99.900 =   68.989
sockperf: ---> percentile 99.000 =   33.092
sockperf: ---> percentile 90.000 =   17.993
sockperf: ---> percentile 75.000 =   16.170
sockperf: ---> percentile 50.000 =   14.692
sockperf: ---> percentile 25.000 =   13.535
sockperf: ---> <MIN> observation =   11.666
```
### Throughput:
command: `sudo bash -c  sockperf tp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 9750678 messages sent in 30.000 sec

sockperf: [2;35mNOTE: test was performed, using msg-size=14. For getting maximum throughput consider using --msg-size=1472[0m
sockperf: Summary: Message Rate is 325020 [msg/sec]
sockperf: Summary: BandWidth is 4.339 MBps (34.716 Mbps)
```
## Client VMA on
### PingPong:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf pp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=2053760; ReceivedMessages=2053759
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=2027103; ReceivedMessages=2027103
sockperf: [2;35m====> avg-latency=7.272 (std-dev=9.990, mean-ad=0.783, median-ad=0.616, siqr=0.470, cv=1.374, std-error=0.007, 99.0% ci=[7.254, 7.290])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 7.272 usec
sockperf: [2;35mTotal 2027103 observations[0m; each percentile contains 20271.03 observations
sockperf: ---> <MAX> observation = 4291.384
sockperf: ---> percentile 99.999 = 2014.543
sockperf: ---> percentile 99.990 =   64.005
sockperf: ---> percentile 99.900 =   23.644
sockperf: ---> percentile 99.000 =   17.643
sockperf: ---> percentile 90.000 =    7.844
sockperf: ---> percentile 75.000 =    7.494
sockperf: ---> percentile 50.000 =    6.852
sockperf: ---> percentile 25.000 =    6.552
sockperf: ---> <MIN> observation =    5.830
```
### Throughput:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf tp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 92900474 messages sent in 30.000 sec

sockperf: [2;35mNOTE: test was performed, using msg-size=14. For getting maximum throughput consider using --msg-size=1472[0m
sockperf: Summary: Message Rate is 3096660 [msg/sec]
sockperf: Summary: BandWidth is 41.345 MBps (330.759 Mbps)
```
# Server-side VMA on
Server command: `sudo VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib/libvma.so VMA_SPEC=LATENCY sockperf sr -i 172.18.200.22`
## Client VMA off
### PingPong:
command: `sudo bash -c  sockperf pp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=1533808; ReceivedMessages=1533807
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=1511834; ReceivedMessages=1511834
sockperf: [2;35m====> avg-latency=9.741 (std-dev=4.139, mean-ad=0.824, median-ad=0.831, siqr=0.581, cv=0.425, std-error=0.003, 99.0% ci=[9.732, 9.750])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 9.741 usec
sockperf: [2;35mTotal 1511834 observations[0m; each percentile contains 15118.34 observations
sockperf: ---> <MAX> observation = 1515.452
sockperf: ---> percentile 99.999 =  602.929
sockperf: ---> percentile 99.990 =  140.133
sockperf: ---> percentile 99.900 =   34.429
sockperf: ---> percentile 99.000 =   13.775
sockperf: ---> percentile 90.000 =   10.619
sockperf: ---> percentile 75.000 =   10.078
sockperf: ---> percentile 50.000 =    9.447
sockperf: ---> percentile 25.000 =    8.916
sockperf: ---> <MIN> observation =    6.998
```
### Throughput:
command: `sudo bash -c  sockperf tp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 9786464 messages sent in 30.000 sec

sockperf: [2;35mNOTE: test was performed, using msg-size=14. For getting maximum throughput consider using --msg-size=1472[0m
sockperf: Summary: Message Rate is 326211 [msg/sec]
sockperf: Summary: BandWidth is 4.355 MBps (34.843 Mbps)
```
## Client VMA on
### PingPong:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf pp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:sockperf: using recvfrom() to block on socket(s)

[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: [Total Run] RunTime=30.000 sec; Warm up time=400 msec; SentMessages=5240402; ReceivedMessages=5240401
sockperf: ========= Printing statistics for Server No: 0
sockperf: [Valid Duration] RunTime=29.550 sec; SentMessages=5170618; ReceivedMessages=5170618
sockperf: [2;35m====> avg-latency=2.840 (std-dev=8.233, mean-ad=0.139, median-ad=0.073, siqr=0.077, cv=2.899, std-error=0.004, 99.0% ci=[2.831, 2.849])[0m
sockperf: # dropped messages = 0; # duplicated messages = 0; # out-of-order messages = 0
sockperf: Summary: Latency is 2.840 usec
sockperf: [2;35mTotal 5170618 observations[0m; each percentile contains 51706.18 observations
sockperf: ---> <MAX> observation = 4225.051
sockperf: ---> percentile 99.999 =  258.110
sockperf: ---> percentile 99.990 =   12.834
sockperf: ---> percentile 99.900 =    5.435
sockperf: ---> percentile 99.000 =    3.266
sockperf: ---> percentile 90.000 =    2.970
sockperf: ---> percentile 75.000 =    2.875
sockperf: ---> percentile 50.000 =    2.755
sockperf: ---> percentile 25.000 =    2.720
sockperf: ---> <MIN> observation =    2.624
```
### Throughput:
command: `sudo bash -c  VMA_MEM_ALLOC_TYPE=0 LD_PRELOAD=/usr/lib64/libvma.so VMA_SPEC=LATENCY  sockperf tp -i 172.18.200.22 -t 30`
```
sockperf: [2;35m== version #3.10-no.git == [0m
sockperf[CLIENT] send on:
[ 0] IP = 172.18.200.22   PORT = 11111 # UDP
sockperf: Warmup stage (sending a few dummy messages)...
sockperf: Starting test...
sockperf: Test end (interrupted by timer)
sockperf: Test ended
sockperf: Total of 79333690 messages sent in 30.000 sec

sockperf: [2;35mNOTE: test was performed, using msg-size=14. For getting maximum throughput consider using --msg-size=1472[0m
sockperf: Summary: Message Rate is 2644421 [msg/sec]
sockperf: Summary: BandWidth is 35.307 MBps (282.455 Mbps)
```
