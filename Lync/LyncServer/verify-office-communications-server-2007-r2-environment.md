---
title: 验证 Office 通信服务器 2007 R2 环境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 885b1b08ef2d02c6a3cb3a77b83ca832e70281a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>验证 Office 通信服务器 2007 R2 环境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-16_

在 Office 通信服务器 2007 R2 的共存状态中部署 Lync Server 2013 之前，需要验证 Office 通信服务器 2007 R2 服务是否已配置并启动。

**验证是否已使用 Office 通信服务器 2007 R2 管理工具启动池**

1.  打开 Office 通信服务器 2007 R2 管理工具。

2.  展开“林”**** 节点，展开“Standard Edition 服务器”**** 或“企业版池”**** 节点，然后展开池或服务器名称。

3.  确保这些服务正运行在 Standard Edition Server 或企业版池上。
    
    ![Office 通信服务器 2007 R2 管理控制台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通信服务器 2007 R2 管理控制台")

**查看为 Office 通信服务器 2007 R2 配置的用户**

1.  打开 Office 通信服务器 2007 R2 管理工具。

2.  展开“林”**** 节点，展开“Standard Edition 服务器”**** 或“企业版池”**** 节点，然后展开池或服务器名称。

3.  单击“用户”****。

4.  验证 Office 通信服务器 2007 R2 用户的列表。
    
    ![OCS 管理工具中的用户列表 fo](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理工具中的用户列表 fo")

**确认旧的 XMPP 联盟伙伴配置**

1.  在旧版 XMPP 服务器上，导航到 "管理工具\\服务" 小程序。

2.  确认已启动 Office Communications Server XMPP 网关服务。
    
    ![Office 通信服务器 XMPP 网关服务](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通信服务器 XMPP 网关服务")

</div>

<span> </span>

</div>

</div>

</div>

