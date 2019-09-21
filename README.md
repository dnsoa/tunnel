Tunnel is a simple proxy tool.

# Binary/config file 
both server/client are compiled in one binary file and share same config file.

config file sample is [here](/conf/tunnel.yaml)

# Client(local)
* proxy rule:
    - geoip: based on country
    - whitelist/blacklist: based on regular expression matching
     
* protocols supported
    * socks5
    * http
    * https
    
    support all three protocols on same port.

# Transport

* implemention

    client(local) < --- DataMask + Compression + Transport + Compression + DataMask --- > server(remote) 

* data mask byte/dict and tls key/cert area all generated by user key dynamically.

* protocols supported
    
    transport protocol support quic+tls(UDP), kcp+aes(UDP), tcp+tls(TCP).

* compression
    - disable: disable compression
    - zlib
    - gzip
    - s2
    - snappy

    see [https://github.com/klauspost/compress](https://github.com/klauspost/compress) for more details

# License
MIT.