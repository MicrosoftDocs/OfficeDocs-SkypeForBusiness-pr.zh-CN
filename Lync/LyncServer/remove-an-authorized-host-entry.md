---
title: 删除授权主机条目
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9bc99382e904c398dbb7434b2ee6343ab661ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a>删除授权主机条目

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-26_

本主题介绍了如何删除旧式授权主机条目 (在 Lync Server 2013 中称为 "*受信任的应用程序" 条目*)。 将远程呼叫控制迁移到 Lync Server 2013 部署时, 必须删除 Office 通信服务器 2007 R2 部署中任何 SIP/CSTA 网关的现有授权主机条目。 您必须使用 Office 通信服务器 2007 R2 附带的管理工具删除现有授权主机条目。

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a>删除 Office 通信服务器 2007 R2 部署中的授权主机条目

1.  打开 Office 通信服务器 2007 R2 管理控制台。

2.  展开树, 右键单击创建授权主机的池。

3.  单击 "**属性**", 然后单击 "**前端属性**"。

4.  单击 "**主机授权**" 选项卡。

5.  选择服务器, 然后单击 "**删除**"。

6.  在 "**属性**" 中, 单击 **"确定"**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

