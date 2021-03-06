# Examples from the .dotfiles

### .aliases
Command examples from `.aliases`.

**Navigation**
Easier navigation: `..`, `...`, `....`, `.....`, `~` and `-`

`..`

```
/tmp/Termux/dir1/dir11/dir111$ ..
/tmp/Termux/dir1/dir11$
```

`...`
```
/tmp/Termux/dir1/dir11/dir111$ ...
/tmp/Termux/dir1$
```

`....`
```
/tmp/Termux/dir1/dir11/dir111$ ....
/tmp/Termux$
```

`~`
```
/tmp/Termux$ ~
~$
```

`-`
```
/tmp/Termux/dir1/dir11/dir111$ ...
/tmp/Termux/dir1$ -
/tmp/Termux/dir1/dir11/dir111
/tmp/Termux/dir1/dir11/dir111$
```


**Shortcuts**
*Termux needs Storage permissions to access `/mnt/sdcard`*

`sd` shortcut to `/mnt/sdcard`
```
/tmp/Termux$ sd
/mnt/sdcard$
```

`dl` shortcut to `/mnt/sdcard/Download`
```
/tmp/Termux$ dl
/mnt/sdcard/Download$
```



`h` history
```
/tmp/Termux/dir1/dir11/dir111$ h
  235  2017-01-04 16:21:41 ~
  236  2017-01-04 16:22:03 --
  237  2017-01-04 16:22:18 -
  238  2017-01-04 16:22:31 cd dir1/dir11/dir111/
  239  2017-01-04 16:22:42 ...
  240  2017-01-04 16:22:44 -
  241  2017-01-04 16:39:13 h
```

`g` git
```
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]
```

`j` jobs
```
/tmp/Termux/dir1/dir11/dir111$ j
[1]+  Stopped                 top
/tmp/Termux/dir1/dir11/dir111$
```

`lessf` alternative to `tail -f`
```
/tmp/Termux/dir1/dir11/dir111$ lessf file1
this
is
a
long
file
that
grows
Waiting for data... (interrupt to abort)
```


**Listings**
Colorized listings of files and/or directories

`l` List all files colorized in long format
```
total 4
-rw-r--r-- 1 root root 31 Jan  4 16:43 file1
```

`ll` or `la` List all files colorized in long format, including dot files
```
total 12K
drwxr-xr-x 2 root root 4.0K Jan  4 16:43 ./
drwxr-xr-x 3 root root 4.0K Jan  4 16:03 ../
-rw-r--r-- 1 root root   31 Jan  4 16:43 file1
```

`lsd` List only directories
```
/tmp/Termux$ lsd
drwxr-xr-x 3 root root 4096 Jan  4 16:03 dir1/
drwxr-xr-x 3 root root 4096 Jan  4 16:03 dir2/
drwxr-xr-x 3 root root 4096 Jan  4 16:03 dir3/
```



`week` Get week number
```
/tmp/Termux$ week
01
```

`times` Stopwatch
```
/tmp/Termux$ timer
Timer started. Stop with Ctrl-D.
Wed Jan  4 16:52:55 GMT+1 2017

real    0m2.743s
user    0m0.000s
sys 0m0.000s
Wed Jan  4 16:52:58 GMT+1 2017
```

`dice` Rolls a 6-sided dice
```
/tmp/Termux$ dice
5
```

`yn` Tes / No
```
/tmp/Termux$ yn
Yes
```



**Networking**


`ips` All your IPs
```
/tmp/Termux$ ips
10.0.2.15
fe80::a00:27ff:fe41:bf82
10.6.6.8
fe80::a00:27ff:fedf:ed97
127.0.0.1
::1
```

`myip` Your public IP
```
/tmp/Termux$ myip
104.83.4.80
```


`localip` Your local IP
```
/tmp/Termux$ localip
10.0.2.15
```



`hexdump` Canonical hex dump
```
/tmp/Termux$ hexdump file1
0000000 6573 7263 7465 000a
0000007
```

`urlencode` URL-encode strings
```
/tmp/Termux$ urlencode "../ /"
..%2F+%2F
```

`badge` Ring the terminal bell
```
*ding*
```

`map`  Intuitive map function, For example, to list all directories that contain a certain file
```
/tmp$ find . -name file1 | map dirname
./Termux
./Termux/dir1/dir11/dir111
```

`reload` Reload the shell (i.e. invoke as a login shell)

`p` See if my connection works (ping google dns)
```
/tmp/Termux$ p
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=63 time=78.3 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=63 time=38.3 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=63 time=38.6 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=63 time=82.7 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=63 time=411 ms
^C
--- 8.8.8.8 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4008ms
rtt min/avg/max/mdev = 38.366/129.845/411.080/141.874 ms
```

`path` Print each PATH entry on a separate line
```
/tmp/Termux$ path
/root/bin
/usr/local/sbin
/usr/local/bin
/usr/sbin
/usr/bin
/sbin
/bin
```

### .functions


`calc` Wrapper for `bc`
```
/tmp/Termux$ calc 5+2
7
```

`mkd` Create a new directory and enter it
```
/tmp/Termux$ mkd dir4
/tmp/Termux/dir4$
```

`targz` Create a .tar.gz archive, using `zopfli`, `pigz` or `gzip` for compression
```
/tmp/Termux$ targz dir1
dir1/
dir1/dir11/
dir1/dir11/dir111/
dir1/dir11/dir111/file1
Compressing .tar (10 kB) using `gzip`…
dir1.tar:    98.1% -- replaced with dir1.tar.gz
dir1.tar.gz (0 kB) created successfully.
```

`fs` Determine size of a file or total size of a directory
```
/tmp/Termux$ fs dir1
13K dir1
```

`dataurl` Create a data URL from a file
```
/tmp/Termux$ dataurl file1
data:text/plain;charset=utf-8;base64,c2VjcmV0Cg==
```

`gz` Compare original and gzipped file size
```
/tmp/Termux$ gz file1
orig: 7 bytes
gzip: 33 bytes (471.43%)
```

`json` Syntax-highlight JSON strings or files

`digga`
```
/tmp/Termux$ digga github.com
github.com.     60 IN A 192.30.253.113
github.com.     1730 IN TXT "docusign=087098e3-3d46-47b7-9b4e-8a23028154cd"
github.com.     1730 IN TXT "v=spf1 ip4:192.30.252.0/22 include:_spf.google.com include:esp.github.com include:_spf.createsend.com include:mail.zendesk.com include:servers.mcsv.net ~all"
github.com.     60 IN A 192.30.253.112
github.com.     354 IN NS ns-1283.awsdns-32.org.
github.com.     269 IN SOA ns-1707.awsdns-21.co.uk. awsdns-hostmaster.amazon.com. (
                1          ; serial
                7200       ; refresh (2 hours)
                900        ; retry (15 minutes)
                1209600    ; expire (2 weeks)
                86400      ; minimum (1 day)
                )
github.com.     354 IN NS ns-421.awsdns-52.com.
github.com.     354 IN NS ns-1707.awsdns-21.co.uk.
github.com.     354 IN NS ns-520.awsdns-01.net.
```


**Unicode**

`escape`  UTF-8-encode a string of Unicode symbols
```
/tmp/Termux$ escape 🍃
\xF0\x9F\x8D\x83
```

`unidecode` Decode \x{ABCD}-style Unicode escape sequences
```
/tmp/Termux$ unidecode "\x{5317}\x{4EB0}"
北亰
```

`codepoint` Get a character’s Unicode code point
```
/tmp/Termux$ codepoint 🍃
U+1F343
```



`getcertnames` Show all the names (CNs and SANs) listed in the SSL certificate for a given domain
```
/tmp/Termux$ getcertnames github.com
Testing github.com…

Common Name:

github.com

Subject Alternative Name(s):

github.com
www.github.com
```

`v` with no arguments opens the current directory in Vim, otherwise opens the given location

`tre` is a shorthand for `tree` with hidden files and color enabled, ignoring the `.git` directory, listing directories first. The output gets piped into `less` with options to preserve color and line numbers, unless the output is small enough for one screen.
```
/tmp/Termux$ tre
      1 .
      2 ├── dir1
      3 │   └── dir11
      4 │       └── dir111
      5 │           └── file1
      6 ├── dir2
      7 │   └── dir22
      8 │       └── dir222
      9 ├── dir3
     10 │   └── dir33
     11 │       └── dir333
     12 ├── dir4
     13 ├── example.json
     14 └── file1
     15
     16 10 directories, 3 files
```

`cp_p` Copy with progress
```
/tmp/Termux$ cp_p file1 file2
sending incremental file list
file1
              7 100%    0.00kB/s    0:00:00 (xfr#1, to-chk=0/1)

sent 98 bytes  received 35 bytes  266.00 bytes/sec
total size is 7  speedup is 0.05
```

**Videos**

`gifify` animated gifs from any video (via `ffmpeg`)

`webmify` turn that video into webm (via `ffmpeg`)

`ffconcat` concat videos  (via `ffmpeg`)



`weather` Weather forecast =]
```
/tmp/Termux$ weather Berlin
Weather for City: Berlin, Germany

  _`/"".-.     Moderate or heavy snow showers
   ,\_(   ).   -2 – 3 °C
    /(___(__)  ↘ 20 km/h
     * * * *   7 km
    * * * *    0.2 mm
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤ Wed 04. Jan ├───────────────────────┬──────────────────────────────┐
│           Morning            │             Noon      └──────┬──────┘    Evening            │            Night             │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│  _`/"".-.     Moderate or he…│  _`/"".-.     Moderate or he…│  _`/"".-.     Moderate or he…│  _`/"".-.     Light snow     │
│   ,\_(   ).   -3 – 3 °C      │   ,\_(   ).   -2 – 4 °C      │   ,\_(   ).   -3 – 1 °C      │   ,\_(   ).   -5 – -1 °C     │
│    /(___(__)  → 35 – 51 km/h │    /(___(__)  → 31 – 47 km/h │    /(___(__)  ↘ 19 – 29 km/h │    /(___(__)  ↘ 17 – 27 km/h │
│     * * * *   6 km           │     * * * *   6 km           │     * * * *   9 km           │      *  *  *  10 km          │
│    * * * *    0.6 mm | 84%   │    * * * *    1.1 mm | 98%   │    * * * *    0.1 mm | 37%   │     *  *  *   0.1 mm | 7%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤ Thu 05. Jan ├───────────────────────┬──────────────────────────────┐
│           Morning            │             Noon      └──────┬──────┘    Evening            │            Night             │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│      .-.      Moderate snow  │               Cloudy         │  _`/"".-.     Patchy light s…│     \   /     Clear          │
│     (   ).    -8 – -2 °C     │      .--.     -8 – -2 °C     │   ,\_(   ).   -10 – -4 °C    │      .-.      -11 – -5 °C    │
│    (___(__)   ↓ 19 – 28 km/h │   .-(    ).   ↓ 21 – 27 km/h │    /(___(__)  ↘ 17 – 25 km/h │   ― (   ) ―   ↘ 16 – 25 km/h │
│    * * * *    8 km           │  (___.__)__)  8 km           │      *  *  *  10 km          │      `-’      10 km          │
│   * * * *     0.1 mm | 21%   │               0.1 mm | 32%   │     *  *  *   0.0 mm | 0%    │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤ Fri 06. Jan ├───────────────────────┬──────────────────────────────┐
│           Morning            │             Noon      └──────┬──────┘    Evening            │            Night             │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│               Overcast       │  _`/"".-.     Light snow     │               Cloudy         │     \   /     Clear          │
│      .--.     -10 – -5 °C    │   ,\_(   ).   -8 – -3 °C     │      .--.     -8 – -6 °C     │      .-.      -8 °C          │
│   .-(    ).   ↘ 13 – 18 km/h │    /(___(__)  ↘ 12 – 16 km/h │   .-(    ).   ↘ 8 – 10 km/h  │   ― (   ) ―   → 7 – 10 km/h  │
│  (___.__)__)  10 km          │      *  *  *  7 km           │  (___.__)__)  10 km          │      `-’      10 km          │
│               0.1 mm | 0%    │     *  *  *   0.1 mm | 42%   │               0.0 mm | 0%    │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘

Check new Feature: wttr.in/Moon or wttr.in/Moon@2016-Mar-23 to see the phase of the Moon
Follow @igor_chubin for wttr.in updates
```
