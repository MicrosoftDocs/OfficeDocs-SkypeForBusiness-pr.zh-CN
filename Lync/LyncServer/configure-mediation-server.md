---
title: 配置中介服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>配置中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

此过程详细介绍了将 Lync Server 2013 池配置为使用 Lync Server 2013 中介服务器（而不是旧版 Office 通信服务器 2007 R2 中介服务器）的步骤。

To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.

<div>


> [!NOTE]  
> 有关查找适用于 Lync Server 2013 的合格 PSTN 网关、IP Pbx 和 SIP 中继服务的最新信息，请参阅 at 中的 "Microsoft 统一通信开放互操作性计划" <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> 。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>使用拓扑生成器配置中介服务器

1.  从拓扑生成器中打开现有拓扑。

2.  在左窗格中，导航到“PSTN 网关”****。

3.  右键单击“PSTN 网关”****，然后单击“新建 IP/PSTN 网关”****。

4.  参考以下信息，完成“定义新的 IP/PSTN 网关”**** 页：
    
      - Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.
    
      - 接受“IP/PSTN 网关的侦听端口”**** 的默认值，或者输入新侦听端口（如果已修改）。
    
      - 设置“SIP 传输协议”****。

5.  在左窗格中，导航到“Enterprise Edition 前端池”**** 或“Standard Edition Server”****。

6.  右键单击该池，然后单击“编辑属性”****。

7.  在“中介服务器”**** 下，设置“侦听端口”****。

8.  接下来，选择新创建的 PSTN 网关，然后单击“添加”****，以关联该网关。

9.  在“拓扑生成器”**** 中，选择最顶层节点“Lync Server”****。

10. 从“操作”**** 菜单中，选择“发布拓扑”****，然后单击“下一步”****。

11. “发布向导”**** 完成时，单击“完成”**** 关闭向导。

<div>


> [!NOTE]  
> 请务必填写下一个主题，将<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">语音路由更改为使用新的 Lync server 2013 中介服务器</A>，以确保语音路由指向正确的中介服务器。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

