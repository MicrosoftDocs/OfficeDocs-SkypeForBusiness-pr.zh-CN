---
title: 配置中介服务器
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>配置中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012年-09-28_

该过程详细说明 Lync Server 2013 池配置为使用 Lync Server 2013 中介服务器，而不是旧 Office Communications Server 2007 R2 中介服务器的步骤。

若要成功发布、 启用或禁用拓扑时添加或删除服务器角色，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 还有可能要委派的相应的管理员权限和权限添加服务器角色。 有关详细信息，请参阅 Standard Edition server 或 Enterprise Edition server 部署文档中的委派安装权限。 其他配置更改，需要的只是 RTCUniversalServerAdmins 组中的成员。

<div>


> [!NOTE]  
> 查找合格的 PSTN 网关、 Ip-pbx 和 SIP 中继服务的使用 Lync Server 2013 的最新信息，请参阅"Microsoft 统一通信开放互操作性计划"在<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>配置中介服务器使用拓扑生成器

1.  从拓扑生成器中打开现有拓扑。

2.  在左窗格中，导航到**PSTN 网关**。

3.  **PSTN 网关**，右键单击，然后单击**新建 IP/PSTN 网关**。

4.  完成**定义新的 IP/PSTN 网关**页上的以下信息：
    
      - 输入的网关 FQDN 或 IP 地址。 如果网关使用 TLS 协议，则需要使用网关的 FQDN。
    
      - 接受默认值的**IP/PSTN 网关的侦听端口**或输入新的侦听端口，如果已修改。
    
      - 设置**Sip 传输协议**。

5.  在左窗格中，导航到**Enterprise Edition 前端池**或**Standard Edition Server**。

6.  右键单击池，，，然后单击**编辑属性**。

7.  在**中介服务器****侦听端口**的设置。

8.  接下来，通过选择并单击**添加**关联的新创建的 PSTN 网关。

9.  在**拓扑生成器**中，选择顶层节点**Lync Server**。

10. 从**操作**菜单中，选择**发布拓扑**，然后单击**下一步**。

11. **发布向导**完成后，单击**完成**以关闭向导。

<div>


> [!NOTE]  
> 请务必完成下一主题，<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">更改语音路由以使用新的 Lync Server 2013 中介服务器</A>，以确保语音路由指向正确的中介服务器。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

