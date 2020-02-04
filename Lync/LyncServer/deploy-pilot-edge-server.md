---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>部署试点 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

本主题重点介绍在部署 Lync Server 2013 Edge 服务器之前应注意的配置设置。 Lync Server 2013 的部署和配置过程非常类似于 Lync Server 2010。 本部分仅重点介绍您在试验池部署中应考虑的要点。 有关详细步骤，请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" （介绍部署过程），还提供外部用户访问的配置信息。

通过 "**定义新的边缘池**" 向导导航时，请查看以下步骤中所示的关键配置设置。 请注意，仅显示 "**定义新边缘池**" 向导的几个页面。

**定义边缘池**

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  导航到 Lync Server 2013 节点。 右键单击 "**边缘池**"，然后单击 "**新建边缘池**"。
    
    ![定义 "新建边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定义 "新建边缘池" 对话框")

3.  边缘池可以是**多台计算机池**或**单个计算机池**。
    
    ![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 "边缘池 FQDN" 对话框")

4.  在 "**选择功能**" 页面上，不要启用联盟或 XMPP 联合身份验证。 联合身份验证和 XMPP 联合身份验证当前通过旧版 Lync Server 2010 Edge 服务器路由。 将在迁移的后续阶段配置这些功能。
    
    !["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg ""选择功能" 对话框")

5.  接下来，继续完成以下向导页：**外部 fqdn**、**定义内部 Ip 地址**以及**定义外部 IP 地址**。

6.  在 "**定义下一个跃点**" 页面上，选择 Lync Server 2010 Edge 池的下一跃点的控制器。
    
    !["定义下一跃点" 对话框](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg ""定义下一跃点" 对话框")

7.  此时，在 "**关联前端或中介池**" 页面上，不要将池与此边界池关联。 外部媒体流量当前通过旧版 Lync Server 2010 Edge 服务器路由。 将在迁移的后续阶段配置此设置。
    
    !["关联前端池" 对话框](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg ""关联前端池" 对话框")

8.  单击 "**完成**"，然后**发布**拓扑。

9.  按照部署文档中[Lync server 2013 的安装边缘服务器](lync-server-2013-install-edge-servers.md)中的步骤操作，将文件安装在新的边缘服务器上，配置证书，然后启动服务。

请务必遵循部署文档中[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)主题中的指南。 本部分仅提供了有关安装这些服务器角色时的配置设置指南。

现在，你应该与 Lync Server 2013 Edge 服务器部署并行部署旧版 Lync Server 2010 Edge 服务器。 验证两个部署是否正常运行，服务是否已启动，并且你可以在迁移到下一阶段之前管理每个部署。

</div>

<span> </span>

</div>

</div>

</div>

