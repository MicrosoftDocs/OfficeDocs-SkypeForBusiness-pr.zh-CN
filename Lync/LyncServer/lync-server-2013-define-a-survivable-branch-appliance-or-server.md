---
title: Lync Server 2013：定义 Survivable 分支装置或服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9006aa3a54a2aa38cecb4b49ef56094eb24494fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>在 Lync Server 2013 中定义 Survivable 分支设备或服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-07_

如果在将 Survivable Branch Appliance 或 Survivable Branch Server 添加到拓扑时尚未对其进行定义，则在中央站点执行以下过程。

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>定义 Survivable 分支设备或 Survivable 分支服务器

1.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中，展开中央站点，展开 "**分支站点**"，然后展开您计划部署 Survivable 分支装置或 Survivable 分支服务器的分支站点的名称。

3.  右键单击 " **Survivable 分支装置**"，然后单击 "**新建 Survivable 分支设备**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 在<STRONG>Survivable 分支装置</STRONG>中，可以定义 Survivable 分支服务器和 Survivable 分支装置。

    
    </div>

4.  在 "**定义 Survivable 分支设备**" 对话框中，单击 " **FQDN**"，键入将在此分支站点上部署的 Survivable 分支机构或 Survivable 分支服务器的完全限定域名（FQDN），然后单击 "**下一步**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果要定义 Survivable 分支设备，则在<STRONG>FQDN</STRONG>中输入的名称必须与分配给<STRONG>ServicePrincipalName</STRONG>属性的 Survivable 分支装置 FQDN 相同。 有关详细信息，请参阅<A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">在 Lync Server 2013 中将 Survivable 分支设备添加到 Active Directory</A>。

    
    </div>

5.  单击 "**前端池**"，单击此 Survivable 分支设备或 Survivable 分支服务器将连接到的中央站点的前端服务器（用户服务池），然后单击 "**下一步**"。

6.  单击 "**边缘服务器**"，单击此 Survivable 分支设备或 Survivable 分支服务器将连接到的边缘池，以提供到分支站点的远程用户的 PSTN 连接，然后单击 "**下一步**"。

7.  单击 "**网关 FQDN" 或 "Ip 地址**"，然后键入与 Survivable 分支设备或 Survivable 分支服务器关联的网关对等方的 FQDN 或 ip 地址，以路由入站或出站 PSTN 呼叫。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果要定义 Survivable Branch Appliance，这是 Survivable Branch Appliance 内的中介服务器为实现 PSTN 连接而连接的网关。

    
    </div>

8.  单击“IP/PSTN 网关的侦听端口”****，然后接受默认端口。

9.  在 " **Sip 传输协议**" 中，单击 Survivable 分支设备或 Survivable 分支服务器将使用的传输协议，然后单击 "**完成**"。
    
    <div>
    

    > [!NOTE]  
    > 出于安全考虑，强烈建议使用传输层安全性 (TLS)。 如果要定义 Survivable Branch Appliance，请参考 Survivable Branch Appliance 供应商文档，以验证 Survivable Branch Appliance 是否支持 TLS 协议。

    
    </div>

10. 在控制台树中，右键单击新的 Survivable Branch Appliance 或 Survivable Branch Server，再单击“拓扑”****，然后单击“发布”****。

**下一步**：[使用 Lync Server 2013 部署 Survivable 分支设备或服务器-分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

