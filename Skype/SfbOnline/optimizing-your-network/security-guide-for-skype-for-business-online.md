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
audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Skype for Business Online 安全指南 <add description>
ms.openlocfilehash: c10dc554cc1d07dbefb4fba84aed55ae14e9374e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164891"
---
# <a name="security-and-skype-for-business-online"></a>安全和 Skype for business Online

作为 Microsoft 365 和 Office 365 服务的一部分，Skype for business Online （SfBO）通过纵深防御、服务中的客户控件、安全强化和操作最佳做法等所有安全最佳做法和过程（如服务级别安全）。有关完整的详细信息，请参阅 Microsoft 信任中心https://microsoft.com/trustcenter)（。

## <a name="trustworthy-by-design"></a>设计上可信任
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>默认可信任
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>SfBO 如何处理常见的安全威胁
本部分确定 SfBO 服务安全性的更常见威胁以及 Microsoft 如何降低每个威胁。

### <a name="compromised-key-attack"></a>被盗用密钥攻击
密钥是用于加密、解密或验证机密信息的机密代码或数字。必须考虑的公钥基础结构（PKI）中使用两个敏感密钥：每个证书持有者具有的私钥以及通信合作伙伴成功识别和会话密钥交换后使用的会话密钥。攻击者确定私钥或会话密钥时会发生受损密钥攻击。当攻击者成功确定密钥时，攻击者可以使用密钥解密加密的数据，而不知道发件人的知识。

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>网络拒绝服务攻击
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- 向受到攻击的网络中正在运行的应用程序和服务发送无效数据，干扰它们的正常工作。
- 发送大量流量以造成系统过载，直到系统停止对合理请求做出响应或对合理请求做出响应的速度变得很慢。
- 隐藏攻击证据。
- 阻止用户访问网络资源。

SfBO 通过运行 Azure DDOS 网络保护和限制来自相同终结点、子网和联合实体的客户端请求来减少这些攻击。

### <a name="eavesdropping"></a>窃听
在攻击者获取对网络中数据路径的访问权并能够监控和读取流量内容时，会发生窃听。窃听也称为监听或窥探。如果流量内容采用纯文本形式，则攻击者在获取路径的访问权之后即可读取流量内容。例如，通过控制数据路径上的路由器进行攻击。 

SfBO 使用相互 TLS （MTLS）来实现 Microsoft 365 或 Office 365 中的服务器通信和从客户端到服务的 TLS，因此在给定对话可能遭受攻击的时段内，呈现此攻击很难实现。TLS 对所有方进行身份验证，并加密所有通信。这不会阻止窃听，但攻击者无法读取流量，除非加密已损坏。

TURN 协议用于实时媒体用途。TURN 协议不要求加密通信，并且它正在发送的信息受消息完整性保护。尽管它是开放的，但通过查看数据包的源地址和目标地址即可直接提取发送的信息（即 IP 地址和端口）。SfBO 服务通过检查邮件的消息完整性来确保数据的有效性，方法是使用从一些项目派生的密钥，包括一个密码，这些项目从不以明文形式发送。SRTP 用于媒体流量，也是加密的。

### <a name="identity-spoofing-ip-address-spoofing"></a>标识欺骗（IP 地址欺骗）
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- 已配置仅支持传输控制协议 (TCP) 的连接（建议不要这样做，因为 TCP 通信未经过加密）。
- 将这些连接的 IP 地址标记为受信任的主机。 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>中间人攻击
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

中间人攻击还可能发生在两个客户端之间的媒体流量中，但在 SfBO 中点对点音频、视频和应用程序共享流使用基于 TLS 的会话启动协议 (SIP) 在对等设备之间协商的加密密钥通过 SRTP 进行加密。 

### <a name="rtp-replay-attack"></a>RTP 重放攻击
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>SPIM
Spim 是主动提供的商业即时消息或状态订阅请求。虽然 Spim 本身并不会导致网络问题，但至少会有些烦人，占用资源和生产时间，而且可能会导致网络问题。例如，用户通过发送请求相互发送垃圾消息。用户可以相互阻止对方来防止出现这种情况，但对于联盟，如果建立了协作的 Spim 攻击，则很难防止出现这种情况，除非你禁用联盟伙伴关系。

### <a name="viruses-and-worms"></a>病毒与蠕虫
病毒是一种代码单元，其用途是重现其他类似的代码单元。若要工作，病毒需要一个主机，例如文件、电子邮件或程序。与病毒一样，蠕虫是编码为再现其他类似代码单元的代码单元，但与病毒不需要主机。病毒和蠕虫主要在客户端之间的文件传输期间或从其他用户发送 Url 时显示。如果您的计算机上有病毒，则可以使用您的身份，并以您的名义发送即时消息。标准客户端安全最佳做法（如定期扫描病毒）可缓解此问题。 

## <a name="personally-identifiable-information"></a>个人身份信息
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***表 1 - 增强状态数据***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Data**             | **可能的** **设置**                                                                  |   |
| 个人数据        | 姓名、职务、公司、电子邮件地址、时区                                             |   |
| 电话号码    | 工作电话号码、手机号码、住宅电话号码                                                                         |   |
| 日历信息 | 忙/闲、城镇通知、会议详细信息（对有权访问您的日历的用户） |   |
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
- 公钥基础结构（PKI）使用由受信任的证书颁发机构（Ca）颁发的证书对服务器进行身份验证并确保数据完整性。
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- 用于用户身份验证的行业标准协议，如果可能。

本部分中的主题介绍了每个基本元素的工作方式，以增强 SfBO 服务的安全性。
 
### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory 函数作为 Microsoft 365 和 Office 365 的目录服务。它存储所有用户目录信息和策略分配。 

### <a name="public-key-infrastructure-for-sfbo"></a>SfBO 的公钥基础架构
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>CRL 分发点
SfBO 要求所有服务器证书都包含一个或多个证书吊销列表（CRL）分发点。CRL 分发点（Cdp）是可供下载 Crl 的位置，用于验证证书自颁发之日起未被吊销以及证书仍在有效期内。CRL 分发点在证书的属性中以 URL 的形式注明，并且是安全的 HTTP。SfBO 服务通过每个证书身份验证检查 CRL。

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
受信任的用户是其凭据已通过 Microsoft 365 或 Office 365 中的 AAD 进行身份验证的用户。 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **新式验证**是用于客户端到服务器通信的 OAUTH 2.0 的 Microsoft 实现。它支持诸如基于证书的身份验证、多重身份验证和条件访问等安全功能。为了使用 MA，需要为 MA 启用联机租户和客户端。默认情况下，在 2017 5 月后创建的 SfBO 租户已启用 MA。对于在此时间之前创建的租户，请按照此处的说明将其打开。以下客户端都支持 MA： Skype for business 2015 或2016客户端、Mac 版 Skype for business、Lync 2013 客户端、3PIP IP 手机、iOS 和 Android。 
- 当新式身份验证未启用（或不可用）时，将使用**组织 ID** 。
- **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。

SfBO 身份验证包含两个阶段：
1. 在客户端和服务器之间建立安全关联。
2. 客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

客户端证书为用户提供了另一种通过 SfBO 进行身份验证的方法。用户不提供用户名和密码，而是拥有与解决加密质询所需证书对应的证书和私钥。 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Windows PowerShell 和 SfBO 管理工具
在 SfBO 中，IT 管理员可以通过 O365 管理门户或使用租户远程 PowerShell （TRPS）管理其服务。租户管理员使用新式身份验证对 TRPS 进行身份验证。

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>在 Internet 边界配置对 SfBO 的访问
若要使 SfBO 正常工作（用户能够加入会议等），客户需要配置其 internet 访问权限，以便允许向 SfBO 云中的服务进行出站 UDP 和 TCP 流量。有关详细信息，请参阅此处：https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 和 TCP 443

客户端使用 UDP 3478-3481 和 TCP 443 端口从 A/V 边缘服务请求服务。客户端使用这两个端口分别分配 UDP 和 TCP 端口，以便远程方连接。若要访问 A/V 边缘服务，客户端必须首先建立与 SfBO 注册机构的经过身份验证的 SIP 信号会话，以获取 A/V 边缘服务身份验证凭据。这些值通过受 TLS 保护的信号通道发送，并由计算机生成以减少词典攻击。然后，客户可以使用这些凭据进行摘要式身份验证，使用 A/V 边缘服务分配端口以在媒体会话中使用。初始分配请求从客户端发送，并通过 A/V 边缘服务中的 401 nonce/质询消息进行响应。客户端发送第二个分配，其中包含用户名和 nonce 的用户名称和哈希消息身份验证代码（HMAC）哈希。 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50000-59999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>外部用户 A/V 流量遍历
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![在会议加入中的呼叫顺序](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>用户通过单击电子邮件中的会议 URL，在用户计算机上启动客户端检测过程来启动联接过程。如果检测到客户端，则会启动此客户端。如果未检测到该用户，则会将用户重定向到 web 客户端。<p/>
2. SfBO 客户端发送包含用户凭据的 SIP 邀请。联盟或远程用户使用其企业凭据加入会议。对于联盟用户，SIP 邀请首先发送给他或她的主服务器，该服务器对用户进行身份验证并将邀请转发到 SfBO。需要匿名用户才能传递摘要式身份验证。<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. 客户端发送 INFO 请求以将用户添加到 A/V 会议。

    A/V 会议会将包含令牌的添加用户响应发送到 A/V 会议边缘服务，并在其他信息中显示。

    提示 所有前面的 SIP 流量通过访问边缘服务流动。

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. 在客户端和 A/V 会议服务器之间，将在 SRTP 上协商和设置媒体连接。
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>SfBO 的联盟安全措施
联合身份验证为你的组织提供与其他组织进行通信以共享 IM 和状态的功能。默认情况下，SfBO 联盟处于打开状态。但是，租户管理员可以通过 Microsoft 365 或 Office 365 管理门户控制此功能。查看更多信息。

## <a name="addressing-threats-to-sfbo-conferences"></a>应对 SfBO 会议的威胁

SfBO 为企业用户提供创建和加入实时 Web 会议的功能。企业用户还可以邀请没有 AAD、Microsoft 365 或 Office 365 帐户的外部用户参与这些会议。联盟合作伙伴使用安全和经过身份验证的标识的用户也可以加入会议，并且，如果提升该用户，则可以充当演示者。匿名用户无法作为演示者创建或加入会议，但他们可以在加入后提升为演示者。

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- 参与者的角色决定了其会议控制权限。
- 参与者类型可让你限制对特定会议的访问。
- 已定义的会议类型决定了哪类参与者可以参加。
- 会议日程安排仅限拥有 AAD 帐户和 SfBO 许可证的用户。
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>参与者角色
会议参与者分为三组，每组都有自己的权利和限制：
- **组织者** &nbsp; &nbsp;创建会议的用户，无论是即席还是按日程安排。组织者必须是经过身份验证的企业用户，并且能够控制会议的所有最终用户方面。
- **演示者** &nbsp; &nbsp;授权在会议中显示信息的用户，使用受支持的任何媒体。会议组织者也是由演示者定义的，它决定了其他人可以成为演示者。组织者可以在安排会议或正在会议时做出此决定。
- **Attendee** &nbsp;与会者&nbsp;已被邀请参加会议但无权充当演示者的用户。

演示者还可以在会议期间将某一与会者升格为演示者。

### <a name="participant-types"></a>参与者类型

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **属于租户** &nbsp; &nbsp;的用户这些用户在 Azure Active Directory 中为租户提供凭据。<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **属于租户的用户** &nbsp;&nbsp; 这些用户在租户的 Azure Active Directory 中拥有一个凭据。<br/>a.*联合用户*-联合用户拥有与联盟伙伴的有效凭据，因此被视为通过 SfBO 进行身份验证。联盟用户可以加入会议，并在加入会议后升级到演示者，但不能在与其联盟的企业中创建会议。<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>参与者与会
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

默认情况下，从 PSTN 拨入的与会者直接进入会议，但可以更改此选项以强制拨入与会者前往大厅。  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **只有我，会议组织者**&nbsp;&nbsp;除组织者之外，每个人都必须在大厅等候，直到被允许参加会议。
- **我从我公司邀请的人**&nbsp;&nbsp;即使没有被邀请，公司内的任何人都可以直接参加会议。
- **来自我的组织**&nbsp;&nbsp;的任何人 SfBO Microsoft 365 或 Office 365 租户中的所有用户都可以加入会议，而无需在大厅中等待，即使他们不在通讯组列表中。所有其他用户（包括所有外部和匿名用户）都必须在大厅中等待，直到获准。
- **Anyone**有权访问会议链接的任何人（无限制）将直接进入会议。&nbsp;&nbsp;如果指定了 "仅组织者（已锁定）" 以外的任何方法，则会议组织者还可以通过 "通过电话绕过会议厅" 指定拨入的人员。 

### <a name="presenter-capabilities"></a>演示者功能
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **仅组织者**&nbsp;只能显示会议组织&nbsp;者。
- **公司中所有**&nbsp;内部用户均可&nbsp;出席。
- **包括我公司**&nbsp;&nbsp;外部人员的每个人（无限制）加入会议的人员都可以出席。
- **我选择的人选择**&nbsp;&nbsp;会议组织者通过将用户添加到演示者列表来指定可显示的用户。

## <a name="related-topics"></a>相关主题
[Microsoft 信任中心](https://microsoft.com/trustcenter)

