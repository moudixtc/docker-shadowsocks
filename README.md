# moudixtc/shadowsocks
Docker image for [shadowsocks server](https://github.com/shadowsocks/shadowsocks/tree/master) based on Ubuntu 18.04 LTS.

# Tags
- [`latest` (*latest/Dockerfile*)](https://github.com/moudixtc/docker-shadowsocks/blob/master/latest/Dockerfile)

# Usage
The default command expects the [config json file](https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File) at `/etc/shadowsocks/shadowsocks.json`.
1. Use docker's bind mount
    ```bash
    docker run -d --mount type=bind,source=<CONFIG_FILE_ON_HOST>,destination=/etc/shadowsocks/shadowsocks.json,readonly moudixtc/shadowsocks
    ```
