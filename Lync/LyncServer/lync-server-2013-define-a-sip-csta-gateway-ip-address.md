---
title: Lync Server 2013：定义 SIP/CSTA 网关 IP 地址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50958f2c7c44045e25ff4ac9619f3ad73a5f302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

如果 Lync Server 将连接到您通过使用传输控制协议（TCP）连接为远程呼叫控制部署的 SIP/CSTA 网关，则必须在拓扑生成器中定义网关的 IP 地址。 对于支持传输层安全（TLS）连接的网关，此步骤不是必需的。 对于支持 TLS 连接的任何网关，您可以跳过此过程并继续部署远程呼叫控制，方法是按照在[Lync Server 2013 中启用 "远程呼叫控制" 的 "启用 Lync 用户](lync-server-2013-enable-lync-users-for-remote-call-control.md)" 中的步骤操作。

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>使用拓扑生成器定义 SIP/CSTA 网关 IP 地址

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

3.  选择下载现有拓扑的选项。

4.  展开 "**受信任的应用程序服务器**" 节点。

5.  右键单击您创建的受信任的应用程序池，如在[Lync Server 2013 中的 "配置远程呼叫控制的受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)" 中所述，然后单击 "**编辑属性**"。

6.  清除 "**启用将配置数据复制到此池**" 复选框。

7.  单击 "**将服务使用限制为所选 IP 地址**"。 默认设置是**使用所有配置的 IP 地址**。

8.  在 "**主 IP 地址**" 文本框中，输入 SIP/CSTA 网关的 IP 地址。

9.  若要更新中央管理存储中的拓扑，请在控制台树中单击 " **Lync Server**"，然后在 "**操作**" 窗格中单击 "**发布**"。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

