---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>部署试点 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

本主题重点介绍在部署 Lync Server 2013 Edge 服务器之前应注意的配置设置。 本部分仅重点介绍你应考虑的要点, 作为试点边缘池部署的一部分。 有关详细步骤, 请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" (介绍部署过程), 还提供外部用户访问的配置信息。

通过 "**定义新的边缘池**" 向导导航时, 请查看以下步骤中所示的关键配置设置。 请注意, 仅显示 "**定义新边缘池**" 向导的几个页面。

**定义边缘池**

1.  使用拓扑生成器打开 "引导池" 拓扑。

2.  导航到 Lync Server 2013 节点。 右键单击 "**边缘池**", 然后单击 "**新建边缘池**"。
    
    ![定义 "新建边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定义 \"新建边缘池\" 对话框")

3.  边缘池可以是**多台计算机池**或**单个计算机池**。
    
    ![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 \"边缘池 FQDN\" 对话框")

4.  在 "**选择功能**" 页面上, 不要启用联盟或 XMPP 联合身份验证。 联盟和 XMPP 联合身份验证当前通过旧版 Office 通信服务器 2007 R2 Edge 服务器路由。 将在迁移的后续阶段配置这些功能。
    
    !["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "\"选择功能\" 对话框")

5.  接下来, 继续完成以下向导页:**选择 "IP 选项**"、"**外部 fqdn**"、"**定义内部 Ip 地址**" 和 "**定义外部 ip 地址**"。

6.  在 "**定义下一个跃点**" 页面上, 选择 Lync Server 2013 Edge 池的下一跃点的控制器。
    
    !["定义新的边缘池" 对话框, 下一个跃点池列表](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "\"定义新的边缘池\" 对话框, 下一个跃点池列表")

7.  在 "**关联前端池**" 页面上, 请不要在此时间将池与此边界池关联。 外部媒体流量当前通过旧版 Office 通信服务器 2007 R2 Edge 服务器路由。 将在迁移的后续阶段配置此设置。
    
    "![定义新的边缘池" 对话框]"(images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "定义新的边缘池\" 对话框")

8.  单击 "**完成**", 然后**发布**拓扑。

9.  按照部署文档中[Lync server 2013 的安装边缘服务器](lync-server-2013-install-edge-servers.md)中的步骤操作, 将文件安装在新的边缘服务器上, 配置证书, 然后启动服务。

请务必遵循部署文档中[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)主题中的指南。 本部分仅提供了有关安装这些服务器角色时的配置设置指南。

现在, 你应该有一个旧式 Office 通信服务器 2007 R2 Edge 服务器部署, 该部署由 BackCompatSite 的存在以及与 Lync Server 2013 Edge 服务器部署同时进行指示。 将联盟配置为使用 Office 通信服务器 2007 R2 控制器。 验证两个部署是否正常运行, 服务是否已启动, 并且你可以在迁移到下一阶段之前管理每个部署。

![显示 OCS 边缘服务器的拓扑生成器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "显示 OCS 边缘服务器的拓扑生成器")

</div>

<span> </span>

</div>

</div>

</div>

