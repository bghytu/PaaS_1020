在PaaS上部署Xray,带伪装页面

[镜像](https://hub.docker.com/r/dfgdgrty/ghjktyui6789fghderty)：`dfgdgrty/ghjktyui6789fghderty`

# 配置

vless + vmess + trojan + shadowsocks2022

- 地址：**x.x.x.x**（由服务平台提供）
- 端口：**443**（通常自带TLS）
- 用户ID/密码：**a6e568d2-8d3a-4199-913b-995cc428e926**（默认）
- 传输协议：**ws**
- 传输层安全：**tls**
- 加密
  - shadowsocks：**2022-blake3-aes-128-gcm**
- 路径（默认）
  - vless：**/vless/a6e568d2-8d3a-4199-913b-995cc428e926**
  - vmess：**/vmess/a6e568d2-8d3a-4199-913b-995cc428e926**
  - trojan：**/trojan/a6e568d2-8d3a-4199-913b-995cc428e926**
  - shadowsocks：**/shadowsocks/1eb6e917774b4a84aff6b058577c60a5**

> 其他参数默认

****



# 环境变量

| 变量名           | 默认值                           | 描述            |
| ---------------- | -------------------------------- | --------------- |
| PORT             | 8080                             | 端口            |
| UUID             | a6e568d2-8d3a-4199-913b-995cc428e926 | 用户ID/密码     |
| PATH_vless       | /vless/$UUID                     | vless路径       |
| PATH_vmess       | /vmess/$UUID                     | vmess路径       |
| PATH_trojan      | /trojan/$UUID                    | trojan路径      |
| PATH_shadowsocks | /shadowsocks/$UUID               | shadowsocks路径 |

为兼容**shadowsocks2022**，生成的UUID需去除所有`-`

> 例：*1eb6e917-774b-4a84-aff6-b058577c60a5* => *1eb6e917774b4a84aff6b058577c60a5*
> 
> 虽然配置的*UUID*里去除了`-`，但是<u>**vmess/vless**</u>可以使用带`-`的<u>1eb6e917-774b-4a84-aff6-b058577c60a5</u>作为*用户ID*（针对SagerNet连不上的情况）

默认路径：**/协议名称/设置的UUID**

1. 假设UUID为：0123456789
2. 则vless默认的路径为：/vless/0123456789

> 如果设置vless路径为<u>/vless1</u>，则配置路径就为<u>/vless1</u>

****



[Xray v1.6.0](https://github.com/XTLS/Xray-core)	·	[Caddy v2.6.1](https://github.com/caddyserver/caddy)	·	[2048小游戏](https://github.com/gabrielecirulli/2048)
