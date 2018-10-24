---
title: 为持久聊天服务器运行向后兼容
TOCTitle: 为持久聊天服务器运行向后兼容
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204901(v=OCS.15)
ms:contentKeyID: 49312862
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为持久聊天服务器运行向后兼容

 

_**上一次修改主题：** 2013-02-21_

利用 Lync Server 2013持久聊天服务器终结点，可以创建指向 持久聊天服务器池的简单 URL。这对于旧式客户端（ Microsoft Office Communications Server 2007 R2群聊服务器或 Lync Server 2010 群聊）很有用，因为用户可在尝试将旧式客户端指向运行 Lync 2013持久聊天的计算机时在手动配置中输入简单 URL。 持久聊天不使用此终结点，仅旧式客户端需要它。这对于可能要迁移聊天室但 Lync 2013 客户端尚未部署到组织中的过渡时期会很有用。之后，运行 Lync 2010群聊（客户端）的用户仍可连接到 持久聊天服务器后端服务器。

您不需要创建多个 持久聊天服务器终结点；而只需要为每个 持久聊天服务器池创建一个终结点。管理员可以创建多个终结点（每个池一个），但仅能将旧式客户端配置为一次连接到一个池。在常见或主流方案中，旧式部署只有一个池。新部署通常将该池迁移到新的 Lync Server 2013，并可能添加其他一些新的 持久聊天服务器池。

此主流方案通常采用以下模式：

  - 使用一个 Lync Server 2010 群聊 池管理用户，并且您的 Lync 2010 群聊 客户端通过一些已知用户（默认的 sip:ocschat@*\<domainName\>*.com 或类似用户）连接到该池。这些用户是启用 SIP 的 Active Directory 域服务，并且查找服务会注册这些用户以接收传入请求。

  - 然后，安装 Lync Server 2013持久聊天服务器和 持久聊天服务器池。

  - 在用户通常处于脱机状态期间（例如周末）：
    
      - 关闭 Lync Server 2010 群聊。
    
      - 将数据从 Lync Server 2010 群聊池迁移到 Lync Server 2013持久聊天服务器池。
    
      - 从 Active Directory 域服务 中删除已知用户。
    
      - 使用与之前删除的已知用户相同的 SIP URI 创建新的 *旧终结点* 。
    
      - 启动 Lync Server 2013持久聊天服务器。

  - 用户使用他们的 Lync 2010 群聊（客户端）重新登录并连接到他们的数据，而无需更改任何配置。

  - 稍后，您可以停用 Lync Server 2010 群聊。然后，您可以部署 Lync Server 2013持久聊天服务器，并安装新的 Lync Server 2013持久聊天服务器池。

有关从 Lync Server 2010 群聊迁移到 Lync Server 2013持久聊天服务器的详细信息，请参阅 [从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

运行向后兼容（创建指向可以由旧式 群聊池客户端使用的 持久聊天服务器池的 持久聊天服务器终结点）：

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

接下来，将 持久聊天客户端配置为将该 SIP 地址用作其联系人对象。该 SIP 地址是使用 **New-CsPersistentChatEndpoint** cmdlet 为特定 持久聊天服务器池创建的。

要使用 Windows PowerShell 命令行接口添加持久聊天服务器终结点，请考虑以下示例。在此示例中，您在池的完全限定的域名 (FQDN) 为“pcpool.contoso.com”的“contoso.com”拓扑中配置名为“persistentchat”的联系人对象：

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

## 另请参阅

#### 概念

[从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

