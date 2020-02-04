---
title: 验证 Lync Server 2010 环境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>验证 Lync Server 2010 环境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

在使用 Lync Server 2010 在共存状态中部署 Lync Server 2013 之前，需要验证是否已配置并启动 Lync Server 2010 服务。 在部署 Lync Server 2013 试验池之前，请务必确定旧版环境中存在的关键服务和功能。 在使用旧版 XMPP 部署在共存状态中部署 Microsoft Lync Server 2013 XMPP 之前，需要验证旧的 XMPP 服务是否已配置并启动，并确定旧版 XMPP 配置支持的联盟合作伙伴。 验证旧版 Lync Server 2010 部署需要执行以下操作：

  - 验证是否已启动 Lync Server 2010 服务

  - 在 Lync Server 2010 中查看拓扑和用户。

  - 验证联盟和边缘服务器设置。

  - 验证 XMPP 服务和联盟合作伙伴。

**验证是否已启动 Lync Server 2010 服务**

1.  从 Lync Server 2010 前端服务器，导航到 "管理工具\\服务" 小程序。

2.  验证以下服务是否在前端服务器上运行：
    
    ![前端服务器上运行的服务列表](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "前端服务器上运行的服务列表")

**在 Lync Server "控制面板" 中查看 Lync Server 2010 拓扑**

1.  使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。

2.  打开 Lync Server "控制面板"。

3.  选择 "**拓扑**"。 验证是否列出了 Lync Server 2010 部署中的各种服务器。
    
    ![Lync Server 2010 控制面板拓扑页面](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制面板拓扑页面")

**在 Lync Server "控制面板" 中查看 Lync Server 2010 用户**

1.  打开 Lync Server "控制面板"。

2.  选择 "**用户**"，然后单击 "**查找**"。

3.  验证 "**注册机构池**" 列是否指向列出的每个用户的 Lync Server 2010 池。
    
    ![Lync Server 2010 "控制面板"，其中列出了用户](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 "控制面板"，其中列出了用户")

**验证 Lync Server 2010 Edge 和联盟设置**

1.  启动拓扑生成器。

2.  **从现有部署中选择 "下载拓扑**"。

3.  选择文件名，并使用默认的 tbxml 文件类型保存拓扑。

4.  展开 Lync Server 2010 节点以显示部署中的各种服务器角色。

5.  选择 "网站" 节点并验证是否设置了 "**网站联合" 路由分配**值。
    
    ![拓扑生成器、站点联合身份验证路线](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓扑生成器、站点联合身份验证路线")

6.  接下来，选择 "标准版服务器" 或 "企业版前端池"。 确定是否已针对 "**关联**" 下的媒体配置了 Edge 池。
    
    ![拓扑生成器，显示服务器和池](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "拓扑生成器，显示服务器和池")

7.  最后，选择 "边缘" 池并确定下一个跃点池是否在**下一个跃点选择**下配置。
    
    ![拓扑生成器，下一跃点选择](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓扑生成器，下一跃点选择")

**验证旧版 XMPP 联盟合作伙伴配置**

1.  从旧的 XMPP 服务器中，导航到 "管理\\工具服务" 小程序。

2.  验证是否已启动 Office 通信服务器 XMPP 网关服务。
    
    ![Office 通信服务器 XMPP 网关服务](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通信服务器 XMPP 网关服务")

</div>

<span> </span>

</div>

</div>

</div>

