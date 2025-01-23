# Iscan-go

如发现bug或者有需要改进的地方，请联系我。谢谢，我会尽快修复其中bug、改进。

在做测试的时候，dirsearch总是不如我所愿，每次装的时候总是需要考虑环境问题，并且status-code为200的404页面总是太多，于是写了一个go版的。 并且添加了404判断（status-code为200，但是实际为404页面），并自动将其忽略（有一些可能忽略不了，还请放过，或者提出改进建议，我很乐意倾听，并将其改进），

后续又加入了端口扫描功能，可做简单的探测，以及协议识别，适合在外网使用。

目录扫描：
  iscan dirscan
~~~
NAME:
   infoAIO dirscan - infoAIO dirscan -u url

USAGE:
   infoAIO dirscan [command options] [arguments...]

OPTIONS:
   Dictionary Configuration:

   --dw value, --dir-wordlists value   Customize directory wordlists
   --fw value, --file-wordlists value  Customize file wordlists
   --prefixes value                    Add custom prefixes to all wordlist entries
   --suffixes value                    Add custom suffixes to all wordlist entries
   -e value, --extensions value        Extension list separated (default: "php,jsp,do,action,asp,aspx")

   Request configuration :

   --cookie value
   --delay value             Delay between requests (default: 3)
   --header value            HTTP request header, can use multiple flags
   --level value             level (default: 3)
   --proxy value             Proxy URL (HTTP/HTTPS/SOCKS5), can use multiple flags
   --random-agent value      Choose a random User-Agent for each request
   --timeout value           Connection timeout (default: 5)
   --ua value
   -m value, --method value  HTTP method (default: GET),Not yet completed
   -t value, --thread value  Number of threads (default: 30)

   Sava Configuration:

   --format value             Report format (Available: plain,csv) (default: "csv")
   -i value, --include value  Include status codes (default: "200-403,500-599")
   -l value, --lenght value   Return Length
   -o value, --output value   Output filePath (default: "output")

   Target Input Source:

   -f value, --file value  URL list file
   -s, --stdin             stdin url list (default: false)
   -u value, --url value   URL



~~~

端口扫描：
  iscan ipscan 
~~~
NAME:
   infoAIO ipscan - infoAIO subscan -d url

USAGE:
   infoAIO ipscan [command options] [arguments...]

OPTIONS:
   --proxy value                     Use proxy scan, support http/socks5 protocol [e.g. --proxy socks5://127.0.0.1:1080]
   --timeout value, --TimeOut value  TimmOut (default: 5)
   --type value                      Specify the type [e.g. --type tcp/--type udp/--type all] (default: "tcp")
   -m value, --mode value            h:hostLivscan p:portscan (default: "hp")
   -o value, --output value          output to file (default: "2025-01-22_21-08-34.csv")
   -t value, --thread value          Number of concurrent threads (default: 500)

   Target Input IP Source:

   --ei value, --excludeIp value  exclude Ip
   -f value, --file value         IP list file
   -i value, --ip value           IP
   -s, --stdin                    IP list (default: false)

   Target Input port Source:

   --ep value, --excludePort value  exclude port
   --pa value, --portadd value      port add
   -p value, --port value           Custom scan ports [e.g. -p 80,443 or -p 1-65535] (default: top port)

~~~
