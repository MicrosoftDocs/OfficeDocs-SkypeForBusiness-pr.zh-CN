---
title: 部署试点边缘服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>部署试点边缘服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

本主题重点介绍在部署 Lync Server 2013 边缘服务器之前应注意的配置设置。 本节只着重介绍在部署试点边缘池的过程中应考虑的关键点。 有关详细步骤，请参阅部署文档中的在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)，它介绍了部署过程，同时提供了外部用户访问的配置信息。

在“定义新的边缘池”**** 向导中导航时，查看以下步骤中显示的关键配置设置。请注意，仅显示了“定义新的边缘池”**** 向导的部分页面。

**定义边缘池**

1.  使用拓扑生成器打开试点池拓扑。

2.  导航到 "Lync Server 2013" 节点。 右键单击“边缘池”****，然后单击“新建边缘池”****。
    
    !["定义新的边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg ""定义新的边缘池" 对话框")

3.  边缘池可以是**多计算机池**，也可以是**单计算机池**。
    
    ![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 "边缘池 FQDN" 对话框")

4.  在“选择功能”**** 页上，不要启用联盟或 XMPP 联盟。 联盟和 XMPP 联合身份验证当前是通过旧版 Office 通信服务器 2007 R2 Edge 服务器路由的。 将在迁移的稍后阶段中配置这些功能。
    
    !["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg ""选择功能" 对话框")

5.  接下来，继续完成以下向导页：“选择 IP 选项”****、“外部 FQDN”****、“定义内部 IP 地址”**** 和“定义外部 IP 地址”****。

6.  在 "**定义下一个跃点**" 页上，选择 Lync Server 2013 边缘池的下一个跃点的控制器。
    
    !["定义新的边缘池" 对话框，"下一跃点池" 列表](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg ""定义新的边缘池" 对话框，"下一跃点池" 列表")

7.  在 "**关联前端池**" 页上，此时不要将池与此边缘池相关联。 外部媒体流量当前通过旧版 Office 通信服务器 2007 R2 边缘服务器路由。 将在迁移的稍后阶段中配置此设置。
    
    !["定义新的边缘池" 对话框](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg ""定义新的边缘池" 对话框")

8.  单击“完成”****，然后**发布**拓扑。

9.  按照部署文档中的安装边缘服务器上的[Lync Server 2013](lync-server-2013-install-edge-servers.md)中的步骤操作，将文件安装在新的边缘服务器上，配置证书，并启动这些服务。

请务必遵循部署文档中的 "在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" 主题中的准则。 本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。

现在，您应具有与 Lync Server 2013 边缘服务器部署并行存在的 BackCompatSite 的旧版 Office 通信服务器 2007 R2 Edge 服务器部署。 将联盟配置为使用 Office 通信服务器 2007 R2 控制器。 在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。

![显示 OCS 边缘服务器的拓扑生成器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "显示 OCS 边缘服务器的拓扑生成器")

</div>

<span> </span>

</div>

</div>

</div>

