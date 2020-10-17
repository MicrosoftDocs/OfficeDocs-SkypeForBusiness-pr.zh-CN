---
title: Lync Server 2013：定义 SIP/CSTA 网关 IP 地址
description: Lync Server 2013：定义 SIP/CSTA 网关 IP 地址。
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
ms.openlocfilehash: 23286b2748df3af06f905a791bf0ee80c6f0a919
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560428"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

如果 Lync Server 将连接到您为远程呼叫控制部署的 SIP/CSTA 网关（使用 (TCP) 连接的传输控制协议），则必须在拓扑生成器中定义网关的 IP 地址。 对于支持传输层安全性 (TLS) 连接的网关来说，这一步不是必需的。 对于任何支持 TLS 连接的网关，您可以跳过此过程并继续部署远程呼叫控制，方法是按照在 [Lync Server 2013 中为远程呼叫控制启用 lync 用户](lync-server-2013-enable-lync-users-for-remote-call-control.md)中的步骤。

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>使用拓扑生成器定义 SIP/CSTA 网关 IP 地址

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

3.  选择相应的选项以下载现有拓扑。

4.  展开“受信任的应用程序服务器”**** 节点。

5.  右键单击您创建的受信任应用程序池，如在 [Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)中所述，然后单击 **编辑属性**。

6.  清除“允许将配置数据复制到此池”**** 复选框。

7.  单击“将服务用途限制为所选 IP 地址”****。默认设置为“使用所有已配置的 IP 地址”****。

8.  在“主 IP 地址”**** 文本框中，输入 SIP/CSTA 网关的 IP 地址。

9.  要更新中央管理存储中的拓扑，请在控制台树中单击“Lync Server”****，然后从“操作”**** 窗格中单击“发布”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

