---
title: Skype for Business Online 安全指南
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Skype for Business Online 安全指南 <add description>
ms.openlocfilehash: a47ec19c0469e47644f7c3a7e86a6aa71cf730d6
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240945"
---
# <a name="security-and-skype-for-business-online"></a>安全性和 Skype for Business 联机

Skype for Business Online (SfBO), as part of the Office 365 service, follows all the security best practices and procedures such as service-level security through defense-in-depth, customer controls within the service, security hardening and operational best practices. 有关完整的详细信息，请参阅 Office 365 信任中心 （https://products.office.com/en-us/business/office-365-trust-center-security)。

## <a name="trustworthy-by-design"></a>设计方面的可信赖性
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>默认的可信赖性
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>SfBO 如何处理常见的安全威胁
本节介绍更常见 SfBO 服务和 Microsoft 如何减少每个威胁的安全威胁。

### <a name="compromised-key-attack"></a>破解密钥攻击
密钥是用于加密、解密或验证机密信息的机密代码或数字。 在公钥基础设施 (PKI) 中使用的敏感密钥有两个必须考虑的因素：每个证书持有者拥有的私钥以及在通信伙伴成功识别和会话密钥交换后使用的会话密钥。 破解密钥攻击是指攻击者破解私钥或会话密钥的行为。 攻击者在成功破解密钥之后，可以使用此密钥对已加密的数据进行解密，而数据的发送者对此毫不知情。

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>网络拒绝服务攻击
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- 向受到攻击的网络中正在运行的应用程序和服务发送无效数据，干扰它们的正常工作。
- 发送大量流量以造成系统过载，直到系统停止对合理请求做出响应或对合理请求做出响应的速度变得很慢。
- 隐藏攻击证据。
- 阻止用户访问网络资源。

SfBO 缓解针对这些攻击中，通过运行 Azure DDOS 网络保护，并通过限制来自相同的终结点、 子网和联合的实体的客户端请求。

### <a name="eavesdropping"></a>窃听
Eavesdropping can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called sniffing or snooping. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path. 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

借助从几个项（包括从不以明文格式发送的 TURN 密码）派生的密钥 SfBO 服务可通过检查消息完整性来确保数据有效。 TURN 协议不要求对通信进行加密和其发送的信息由消息完整性保护。 虽然对窃听开放，信息将发送 （即，IP 地址和端口） 可以提取直接通过只查看数据包的源和目标地址。 SfBO 服务可确保的数据通过检查消息完整性使用密钥派生自几项包括打开密码从不以明文形式发送的邮件有效。 SRTP 用于媒体流量并且也被加密。

### <a name="identity-spoofing-ip-address-spoofing"></a>身份欺骗（IP 地址欺骗）
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- 已配置仅支持传输控制协议 (TCP) 的连接（建议不要这样做，因为 TCP 通信未经过加密）。
- 将这些连接的 IP 地址标记为受信任的主机。 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>中间人攻击
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

中间人攻击还可能发生在两个客户端之间的媒体流量中，但在 SfBO 中点对点音频、视频和应用程序共享流使用基于 TLS 的会话启动协议 (SIP) 在对等设备之间协商的加密密钥通过 SRTP 进行加密。 

### <a name="rtp-replay-attack"></a>RTP 重播攻击
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>SPIM
Spim is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.

### <a name="viruses-and-worms"></a>病毒和蠕虫
病毒是一个代码单元，其目的是为了复制更多类似的代码单元。 病毒需要像文件、电子邮件或程序这样的宿主才能发挥作用。 和病毒一样，蠕虫是一种代码单元，它的代码旨在繁殖更多的类似代码单元，但与病毒不同的是，蠕虫不需要宿主。 病毒和蠕虫主要是在客户端之间传送文件期间或从其他用户发送 URL 时出现。 例如，如果你的计算机上存在某种病毒，则该病毒可使用你的身份代表你发送即时消息。 标准的客户端安全最佳实践（例如定期扫描病毒）可以缓解此问题。 

## <a name="personally-identifiable-information"></a>个人身份信息
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***表 1 - 增强状态数据***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **数据**             | **可能的** **设置**                                                                  |   |
| 个人数据        | 姓名、 职务、 公司、 电子邮件地址、 时区                                             |   |
| 电话号码    | 工作电话号码、手机号码、住宅电话号码                                                                         |   |
| 日历信息 | 忙/闲、 出城通知，会议 （到有权访问您的日历） 的详细信息 |   |
| 状态      | 离开、空闲、忙碌、请勿打扰、脱机                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***表2  - 强制性数据***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **类别** | **可能的设置**                                           |   |
| IP 地址   | 计算机的实际地址或经过 NAT 转换的地址                     |   |
| SIP URI      | <u>david.campbell@contoso.com</u>                               |   |
| 名称         | David Campbell（在 Active Directory 域服务中定义） |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>SfBO 的安全框架
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) 为用户帐户提供单个受信任的后端存储库。 
- 公钥基础结构 (PKI) 使用受信任的证书颁发机构 (Ca) 颁发的证书进行身份验证服务器和确保数据完整性。
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- 用于用户身份验证的行业标准协议，如果可能。

本节中的主题介绍每个基本要素如何工作以增强 SfBO 服务的安全性。

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>SfBO 的公钥基础架构
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>CRL 分发点
SfBO 要求所有服务器证书包含一个或多个证书吊销列表 (CRL) 分发点。 可从 CRL 分发点 (CDP) 下载 CRL，以便确认证书自颁发以来未被吊销且仍处于有效期内。 CRL 分发点作为 URL 证书的属性中记下，安全 HTTP。 SfBO 服务使用每个证书身份验证来检查 CRL。

#### <a name="enhanced-key-usage"></a>增强型密钥使用
All components of the SfBO service require all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication. Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers. This EKU is essential for MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>用于 SfBO 的 TLS 和 MTLS
TLS and MTLS protocols provide encrypted communications and endpoint authentication on the Internet. SfBO uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted. All SIP communications between servers occur over MTLS. SIP communications from client to server occur over TLS.

TLS enables users, through their client software, to authenticate the SfBO servers to which they connect. On a TLS connection, the client requests a valid certificate from the server. To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate. If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication. The resulting connection is trusted and from that point is not challenged by other trusted servers or clients. Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.

Server-to-server connections rely on mutual TLS (MTLS) for mutual authentication. On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA. The certificates prove the identity of each server to the other. In the SfBO service, this procedure is followed.

TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks. In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party. TLS and SfBO’s specification of trusted servers mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication. 

### <a name="encryption-for-sfbo"></a>SfBO 的加密
SfBO uses TLS and MTLS to encrypt instant messages. All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.

下表总结了 SfBO 使用的协议。

***表 3  - 流量保护***

<!--start table here with header -->


|||
|:-----|:-----|
|**通信类型**|**保护协议**|
|服务器到服务器|MTLS|
|客户端到服务器|TLS|
|即时消息和状态|TLS（如果已配置 TLS）|
|音频、视频和媒体的桌面共享|SRTP|
|桌面共享（信号）|TLS|
|Web 会议|TLS|
|会议内容下载、通讯簿下载和通讯组扩展|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>媒体加密
Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. SRTP uses a session key generated by using a secure random number generator and exchanged using the signaling TLS channel. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. 

SfBO generates username/passwords for secure access to media relays over TURN. Media relays exchange the username/password over a TLS-secured SIP channel.

#### <a name="fips"></a>FIPS
SfBO 使用符合 FIPS（联邦信息处理标准）的算法进行加密密钥交换。 

### <a name="user-and-client-authentication"></a>用户和客户端身份验证 
受信任的用户是指其凭据已经过身份验证通过 AAD O365 中。 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **现代身份验证**是 Microsoft 为实现客户端到服务器的通信而实施 OAUTH 2.0 的过程。 它支持众多安全功能，如 O365 基于证书的身份验证、O365 多因素身份验证和 O365 条件访问等。 为使用 MA，在线租户和客户端都需要启用 MA。 2017 年 5 月之后创建的 SfBO 租户默认启用 MA。 此时间之前创建的租户，请按照此处的说明予以启用。 以下客户端均支持 MA：Skype for Business 2015 或 2016 客户端、Skype for Business Mac、Lync 2013 客户端、3PIP IP 电话、iOS 和 Android。 
- 时现代身份验证已启用 （或不可用） 而不使用**组织 ID** 。
- **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。

SfBO 身份验证包括以下两个阶段：
1. 在客户端和服务器之间建立安全关联。
2. 客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

客户端证书提供用户进行身份验证 SfBO 另一种的方法。而不是提供用户名和密码，用户拥有证书和对应于要解决加密质询，则需要证书的私钥。 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Windows PowerShell 和 SfBO 管理工具
在 SfBO 中，IT 管理员可以通过 O365 管理门户或使用 Tenant Remote PowerShell（TRPS）管理他们的服务。 租户管理员使用现代身份验证向 TRPS 进行身份验证。

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>在 Internet 边界配置对 SfBO 的访问
为 SfBO 协同工作 （用户能够加入会议等），客户需要配置其 internet 访问以便允许 SfBO 云服务的出站 UDP 和 TCP 通信。 有关详细信息，请参阅此处：https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 和 TCP 443

UDP 3478 3481 和 TCP 443 端口用于客户端请求服务从 A / V 边缘服务。客户端使用这些两个端口分配 UDP 和 TCP 端口分别用于远程用户连接到。若要访问 A / V 边缘服务，客户端首先必须建立经过身份验证的 SIP 信号会话的 SfBO 注册才能获取 A / V 边缘服务身份验证凭据。这些值通过受 TLS 保护的信号通道发送，并由计算机生成以减少字典式攻击。客户端然后可以使用这些凭据的摘要式身份验证与 A / V 边缘服务以分配在媒体会话中使用的端口。从客户端发送初始分配请求并将其位置收到 401 现时/质询消息响应从 A / V 边缘服务。客户端发送第二个分配包含用户名和哈希消息身份验证代码 (HMAC) 的用户名和现时哈希。 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50000 – 59999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>外部用户 A/V 流量遍历
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![在会议加入中的呼叫顺序](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>用户单击电子邮件中的会议 URL，此操作将启动用户计算机上的客户端检测流程，以便让用户加入会议。 如果检测到客户端，则启动该客户端。 否则，用户将重定向到 Web 客户端。<p/>
2. SfBO 客户端发送包含用户证书的 SIP INVITE。 联盟或远程用户加入会议，通过使用企业凭据。 对于联合用户，SIP INVITE 首先会发送到他或她的家庭服务器，后者对用户进行身份验证并将 INVITE 转发给 SfBO。 匿名用户需通过摘要式身份验证。<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. 客户端发送 INFO 请求以将用户添加到 A/V 会议。

    A / V 会议将发送添加用户响应，其中包含要向 A / V 会议边缘服务之间的其他信息。

    [注意] 所有上述 SIP 流量都将流经访问边缘服务。

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. 客户端之间的 A / V 会议服务器的媒体连接进行协商和通过 SRTP 的设置。
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>SfBO 的联盟保障
联盟让你的组织能够与其他组织通信，以共享 IM 和状态。 在 SfBO 中，默认设置为开启联盟。 但是，租户管理员可以通过 O365 管理门户进行控制。 了解更多详情。

## <a name="addressing-threats-to-sfbo-conferences"></a>应对 SfBO 会议的威胁

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- 参与者的角色决定了其会议控制权限。
- 参与者类型可让你限制对特定会议的访问。
- 已定义的会议类型决定了哪类参与者可以参加。
- 会议日程安排仅限拥有 AAD 帐户和 SfBO 许可证的用户。
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>参与者角色
会议参与者分为三组，每组都有自己的权利和限制：
- **组织者**&nbsp;&nbsp;临时还是按计划是否创建会议的用户。 组织者必须经过身份验证的企业用户，并控制会议的所有最终用户方面。
- **演示者**&nbsp;&nbsp;是否有权信息出席会议，使用任何媒体支持的用户。 根据定义，会议组织者也可以是演示者，并确定谁还可以成为演示者。 会议安排或会议开始时，组织者可以做出决定。
- **与会者**&nbsp;&nbsp;用户被邀请参加会议，但用户无权担任演示者。

演示者还可以在会议期间将某一与会者升格为演示者。

### <a name="participant-types"></a>参与者类型

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **属于租户的用户**&nbsp;&nbsp;这些用户必须在 Azure Active Directory 中为租户的凭据。<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **属于租户的用户** &nbsp;&nbsp; 这些用户在租户的 Azure Active Directory 中拥有一个凭据。<br/>a.*联盟用户*-联盟用户拥有联盟伙伴的有效凭据和，因此被视为已通过 SfBO 身份验证。联盟的用户可以加入会议，并加入会议，但他们不能与之联盟的企业中创建会议后被提升为演示者。<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>参与者与会
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

默认情况下，从 PSTN 拨入的与会者直接进入会议，但可以更改此选项以强制拨入与会者前往大厅。  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **只有我，会议组织者**&nbsp;&nbsp;除组织者之外，每个人都必须在大厅等候，直到被允许参加会议。
- **我从我公司邀请的人**&nbsp;&nbsp;即使没有被邀请，公司内的任何人都可以直接参加会议。
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- **任何人**&nbsp;&nbsp;人 （没有限制） 有权访问会议链接到会议直接获取中。
如果指定了“仅限组织者（锁定）”以外的任何方法，会议组织者还可以指定通过电话拨入的人员直接参加会议而绕过大厅。 

### <a name="presenter-capabilities"></a>演示者功能
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **仅组织者**&nbsp;&nbsp;仅会议组织者可以演示。
- **我公司的人员**&nbsp;&nbsp;所有内部用户均可演示。
- **包含公司以外人员的所有人**&nbsp;&nbsp;可以演示的所有人 （没有限制） 加入会议。
- **我选择的人**&nbsp;&nbsp;会议组织者通过将其添加到演示者列表中来指定哪些用户可以演示。

## <a name="related-topics"></a>相关主题
[Office 365 信任中心](https://products.office.com/en-us/business/office-365-trust-center-security)

