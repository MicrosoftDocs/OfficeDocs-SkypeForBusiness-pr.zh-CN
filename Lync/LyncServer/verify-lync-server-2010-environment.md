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
ms.openlocfilehash: a162c51dabf88231edc7fb5a5f5372a9f29d8687
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>验证 Lync Server 2010 环境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

在使用 Lync Server 2010 在共存状态中部署 Lync Server 2013 之前，需要验证是否已配置并启动 Lync Server 2010 服务。 在部署 Lync Server 2013 试点池之前，请务必确定旧环境中存在的关键服务和功能。 在使用旧版 XMPP 部署在共存状态中部署 Microsoft Lync Server 2013 XMPP 之前，您需要验证是否已配置并启动旧的 XMPP 服务，并确定旧版 XMPP 配置支持的联盟伙伴。 验证旧版 Lync Server 2010 部署需要以下各项：

  - 验证是否已启动 Lync Server 2010 服务

  - 在 Lync Server 2010 中查看拓扑和用户。

  - 确认联盟和边缘服务器设置。

  - 确认 XMPP 服务和联盟伙伴。

**验证是否已启动 Lync Server 2010 服务**

1.  在 Lync Server 2010 前端服务器中，导航到 "管理工具\\服务" 小程序。

2.  确认以下服务正在前端服务器上运行：
    
    ![前端服务器上运行的服务的列表](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "前端服务器上运行的服务的列表")

**在 Lync Server 控制面板中查看 Lync Server 2010 拓扑**

1.  使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。

2.  打开“Lync Server 控制面板”。

3.  选择“拓扑”****。 验证是否列出了 Lync Server 2010 部署中的各种服务器。
    
    ![Lync Server 2010 控制面板拓扑页面](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制面板拓扑页面")

**在 Lync Server 控制面板中查看 Lync Server 2010 用户**

1.  打开“Lync Server 控制面板”。

2.  选择“用户”****，然后单击“查找”****。

3.  验证 "**注册器池**" 列是否指向列出的每个用户的 Lync Server 2010 池。
    
    ![Lync Server 2010 控制面板，其中列出了用户](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 控制面板，其中列出了用户")

**验证 Lync Server 2010 边缘和联盟设置**

1.  启动拓扑生成器。

2.  选择“从现有部署下载拓扑”****。

3.  选择文件名并保存具有默认 .tbxml 文件类型的拓扑。

4.  展开 "Lync Server 2010" 节点，以显示部署中的各种服务器角色。

5.  选择站点节点，并确认是否已设置“站点联盟路由分配”**** 值。
    
    ![拓扑生成器、站点联合路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓扑生成器、站点联合路由")

6.  接下来，选择 Standard Edition Server 或 Enterprise Edition 前端池。确定是否已在“关联”**** 下为媒体配置边缘池。
    
    ![显示服务器和池的拓扑生成器](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "显示服务器和池的拓扑生成器")

7.  最后，选择边缘池，并确认是否已在“下一个跃点选择”**** 下配置下一个跃点池。
    
    ![拓扑生成器，下一个跃点选择](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓扑生成器，下一个跃点选择")

**确认旧的 XMPP 联盟伙伴配置**

1.  在旧版 XMPP 服务器上，导航到 "管理工具\\服务" 小程序。

2.  确认已启动 Office Communications Server XMPP 网关服务。
    
    ![Office 通信服务器 XMPP 网关服务](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通信服务器 XMPP 网关服务")

</div>

<span> </span>

</div>

</div>

</div>

