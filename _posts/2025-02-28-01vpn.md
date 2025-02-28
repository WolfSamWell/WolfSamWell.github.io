| VPN协议类型                                        | Base Protocol                                                | VPN Server和VPN Client 是否实现FIDO协议 | Open Source  | github                                                       |
| -------------------------------------------------- | ------------------------------------------------------------ | --------------------------------------- | ------------ | :----------------------------------------------------------- |
| Open VPN                                           | SSL/TLS 协议，支持 TCP/UDP                                   | 否                                      | 是           | https://github.com/OpenVPN/openvpn                           |
| WireGuard                                          | uses state-of-the-art cryptography, like the [Noise protocol framework](http://www.noiseprotocol.org/), [Curve25519](http://cr.yp.to/ecdh.html), [ChaCha20](http://cr.yp.to/chacha.html), [Poly1305](http://cr.yp.to/mac.html), [BLAKE2](https://blake2.net/), [SipHash24](https://131002.net/siphash/), [HKDF](https://eprint.iacr.org/2010/264), and secure trusted constructions. | 否                                      | 是           | https://github.com/WireGuard                                 |
| SSTP (Secure Socket Tunneling Protocol)            | SSL/TLS，主要用于 Windows 平台                               | 否                                      | 否，微软所有 | https://github.com/SoftEtherVPN/SoftEtherVPN                 |
| IPsec，SSL/TLS，                                   | 通常与 L2TP 或 IKEv2 结合使用                                | 否                                      | 是           | https://github.com/hwdsl2/setup-ipsec-vpn/blob/master/README-zh.md |
| PPTP                                               | PPTP (Point-to-Point Tunneling Protocol)，被淘汰             | 否                                      | 是，标准协议 | 实现可以是开源的，也可以是闭源的，被淘汰。实现之一：https://github.com/accel-ppp/accel-ppp |
| L2TP/IPsec (Layer 2 Tunneling Protocol with IPsec) | 结合 L2TP 和 IPsec，较高的安全性。L2TP/IPsec 的实现可以是开源的，也可以是闭源的 | 否                                      | 是，标准协议 | 实现之一：https://github.com/libreswan/libreswan             |
| IKEv2 (Internet Key Exchange version 2)            | 与 IPsec 结合使用，支持快速重连。                            | 否                                      | 是，协议标准 | 实现之一：https://github.com/strongswan/strongswan           |
| AnyConnect (Cisco SSL VPN)                         | SSL/TLS，支持多因素认证。                                    | 否，支持多因素FIDO2硬件密钥             | 否，商业公司 | https://github.com/topics/cisco-anyconnect                   |
| SoftEther VPN                                      | SSL-VPN、L2TP/IPsec、OpenVPN 等                              | 否，通过外部插件                        | 否，商业公司 | https://github.com/SoftEtherVPN/SoftEtherVPN/                |



