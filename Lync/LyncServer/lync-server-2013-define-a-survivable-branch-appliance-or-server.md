---
title: Lync Server 2013：定义 Survivable Branch Appliance 或 Survivable Branch Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-07_

如果在将 Survivable 分支装置或服务器添加到拓扑中时未定义该装置或服务器, 请在中心站点执行此过程。

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>定义 Survivable 分支装置或 Survivable 分支服务器

1.  单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中, 展开中心网站, 展开 "**分支网站**", 然后展开您计划在其中部署 Survivable 分支装置或 Survivable 分支服务器的分支站点的名称。

3.  右键单击 " **Survivable 分支装置**", 然后单击 "**新建 Survivable 分支装置**"。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable 分支装置</STRONG>可用于定义 Survivable 分支服务器和 Survivable 分支装置。

    
    </div>

4.  在 "**定义 Survivable 分支装置**" 对话框中, 单击 " **FQDN**", 键入将在此分支站点上部署的 Survivable 分支装置或 Survivable 分支服务器的完全限定的域名 (FQDN), 然后单击 "**下一步**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果要定义 Survivable 分支设备, 则在<STRONG>FQDN</STRONG>中输入的名称必须与分配给<STRONG>ServicePrincipalName</STRONG>属性的 Survivable 分支装置 FQDN 相同。 有关详细信息, 请参阅<A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">在 Lync Server 2013 中将 Survivable 分支装置添加到 Active Directory</A>。

    
    </div>

5.  单击 "**前端池**", 单击此 Survivable 分支设备或 Survivable 分支服务器将连接到的中心网站上的前端服务器 (用户服务池), 然后单击 "**下一步**"。

6.  单击 "**边缘服务器**", 单击此 Survivable 分支装置或 Survivable 分支服务器将连接到分支站点的远程用户的 PSTN 连接, 然后单击 "**下一步**"。

7.  单击 "**网关 FQDN" 或 "IP 地址**", 然后键入与 Survivable 分支装置或 Survivable 分支服务器关联的网关对等的 FQDN 或 IP 地址, 以便路由入站或出站 PSTN 呼叫。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果你要定义 Survivable 分支设备, 这是 Survivable 分支设备中的中介服务器将连接到 PSTN 连接的网关。

    
    </div>

8.  单击 "**用于 IP/PSTN 网关的侦听端口**", 然后接受默认端口。

9.  在**Sip 传输协议**中, 单击 Survivable 分支装置或 Survivable 分支服务器将使用的传输协议, 然后单击 "**完成**"。
    
    <div>
    

    > [!NOTE]  
    > 出于安全考虑, 强烈建议你使用传输层安全 (TLS)。 如果你要定义 Survivable 分支设备, 请参阅 Survivable 分支设备供应商文档, 以验证你的 Survivable 分支设备是否支持 TLS 协议。

    
    </div>

10. 在控制台树中, 右键单击新的 Survivable 分支装置或服务器, 单击 "**拓扑**", 然后单击 "**发布**"。

**下一步**:[使用 Lync Server 2013 部署 Survivable 分支装置或服务器-分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

