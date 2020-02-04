---
title: 配置中介服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>配置中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

此过程详细介绍了将 Lync Server 2013 池配置为使用 Lync Server 2013 中介服务器的步骤，而不是旧版 Office 通信服务器 2007 R2 中介服务器。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，您应作为 RTCUniversalServerAdmins 和域管理员组成员的用户登录。 也可以委派正确的管理员权限和权限来添加服务器角色。 有关详细信息，请参阅标准版服务器或企业版服务器部署文档中的委派设置权限。 对于其他配置更改，仅需要 RTCUniversalServerAdmins 组中的成员身份。

<div>


> [!NOTE]  
> 有关查找适用于 Lync Server 2013 的合格 PSTN 网关、IP Pbx 和 SIP 中继服务的最新信息，请参阅 "Microsoft 统一通信打开互操作性计划<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>"。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>使用拓扑生成器配置中介服务器

1.  从拓扑生成器打开现有拓扑。

2.  在左窗格中，导航到**PSTN 网关**。

3.  右键单击 " **PSTN 网关**"，然后单击 "**新建 IP/PSTN 网关**"。

4.  填写 "**定义新的 IP/PSTN 网关**" 页面，其中包含以下信息：
    
      - 输入网关 FQDN 或 IP 地址。 如果网关使用 TLS 协议，则需要使用网关的 FQDN。
    
      - 接受**IP/PSTN 网关的侦听端口**的默认值，或者，如果已修改，请输入新的侦听端口。
    
      - 设置**Sip 传输协议**。

5.  在左窗格中，导航到 "**企业版前端池**" 或 "**标准版服务器**"。

6.  右键单击该池，然后单击 "**编辑属性**"。

7.  在 "**中介服务器**" 下，设置**侦听端口**。

8.  接下来，选择新创建的 PSTN 网关，然后单击 "**添加**" 将其关联。

9.  在**拓扑生成器**中，选择最前面的节点**Lync 服务器**。

10. 从 "**操作**" 菜单中，选择 "**发布拓扑**"，然后单击 "**下一步**"。

11. **发布向导**完成后，单击 "**完成**" 关闭向导。

<div>


> [!NOTE]  
> 请务必填写下一个主题，<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">将语音路由更改为使用新的 Lync server 2013 中介服务器</A>，以确保语音路由指向正确的中介服务器。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

