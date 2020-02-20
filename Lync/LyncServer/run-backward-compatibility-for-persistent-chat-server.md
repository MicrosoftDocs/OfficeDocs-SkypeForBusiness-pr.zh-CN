---
title: 持久聊天服务器的运行后向兼容性
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad689dace5e302cad8d41dff77dd575637b99ae6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>持久聊天服务器的运行后向兼容性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

Lync Server 2013、持久聊天服务器终结点提供了一种创建指向持久聊天服务器池的简单 URL 的方法。 这对于旧版客户端（Microsoft Office 通信服务器 2007 R2 组聊天服务器或 Lync Server 2010 组聊天）很有用，因为当尝试将旧版客户端指向运行 Lync 2013 的计算机时，用户可以在手动配置中输入简单 URL。持久聊天。 持续聊天不使用此终结点，仅在旧客户端中是必需的。 这对可以迁移会议室的临时时段很有用，但尚未在整个组织中部署 Lync 2013 客户端。 随后，运行 Lync 2010 组聊天（客户端）的用户仍可以连接到持久聊天服务器后端服务器。

您无需创建多个持久聊天服务器终结点;您只需要每个持久聊天服务器池对应一个。 管理员可以创建多个终结点（每个池一个），但仅能将旧式客户端配置为一次连接到一个池。 在常见或主流方案中，旧式部署只有一个池。 新部署通常会将该池迁移到新的 Lync Server 2013，并且可能会添加一些新的附加持久聊天服务器池。

此主流方案通常采用以下模式：

  - 通过使用某个已知用户（默认 sip： ocschat@\<domainName\>或类似的用户），使用一个 Lync Server 2010、Group chat 池和你的 lync 2010 组聊天客户端来管理用户连接到该池。 用户是启用了 SIP 的 Active Directory 域服务，并且查找服务会向其注册以接收传入的请求。

  - 随后，安装 Lync Server 2013 持久聊天服务器和持久聊天服务器池。

  - 在用户通常处于脱机状态期间（例如周末）：
    
      - 关闭 Lync Server 2010、组聊天。
    
      - 将数据从 Lync Server 2010、Group 聊天室池迁移到 Lync Server 2013 持久聊天服务器池。
    
      - 从 Active Directory 域服务中删除已知用户。
    
      - 使用与之前删除的已知用户相同的 SIP URI 创建新的*旧终结点*。
    
      - 启动 Lync Server 2013 持久聊天服务器。

  - 用户使用其 Lync 2010 组聊天（客户端）重新登录，并连接到其数据，而无需更改任何配置。

  - 您可以在以后停止 Lync Server 2010、组聊天。 随后，您可以部署 Lync Server 2013、持久聊天服务器，并安装新的 Lync Server 2013 持久聊天服务器池。

有关从 Lync Server 2010 进行迁移的详细信息，请将聊天组聊天到 Lync Server 2013、持久聊天服务器，请参阅[从 Lync server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天到 Lync server 2013、持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

若要运行向后兼容性（以创建指向持久聊天服务器池的持久聊天服务器终结点，可供旧版组聊天池客户端使用）：

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

接下来，配置持久聊天客户端以将该 SIP 地址用作 contact 对象。 SIP 地址是使用**CsPersistentChatEndpoint** cmdlet 为特定的持久聊天服务器池创建的。

若要使用 Windows PowerShell 命令行界面添加持久聊天服务器终结点，请考虑以下示例。 在此示例中，您在池的完全限定域名 (FQDN) 为“pcpool.contoso.com”的“contoso.com”拓扑中配置名为“persistentchat”的联系人对象：

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>另请参阅


[从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

