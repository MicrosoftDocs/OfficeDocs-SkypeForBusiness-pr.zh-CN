---
title: 将 Lync Server 配置为与 System Center Operations Manager 配合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accadd3f12c9f07ec5dfa295a037ce50a72f11ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>配置 Lync Server 2013 以使用 System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

为了将 Microsoft Lync Server 2013 基础结构配置为与 System Center Operations Manager 配合使用，您必须执行以下三项操作：

  - 确定并配置您的主 System Center Operations Manager 管理服务器。 配置管理服务器包括安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及使用 SQL Server 设置后端数据库。 您需要使用的 SQL Server 的实际版本取决于所使用的 System Center Operations Manager 的版本。 有关详细信息，请参阅[在 Lync server 2013 中配置主管理服务器](lync-server-2013-configuring-the-primary-management-server.md)。

  - 确定并配置要监视的 Lync Server 计算机。 若要使用 System Center Operations Manager 监视 Lync Server 计算机，必须安装 System Center Operations Manager 代理文件，并将每台服务器配置为充当代理。

  - 确定并配置要充当 Lync Server*观察程序节点*的计算机。 观察程序节点是定期运行 Lync Server 合成事务的计算机，这些 cmdlet 是验证关键 Lync Server 组件（如登录到系统或 exchange 即时消息的能力）的 Windows PowerShell cmdlet。按预期工作。

本节中的主题包含执行其中每项任务的说明。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置主管理服务器](lync-server-2013-configuring-the-primary-management-server.md)

  - [安装 Lync Server 2013 管理包](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [配置将在 Lync Server 2013 中监视的 Lync Server 计算机](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [在 Lync Server 2013 中安装和配置观察程序节点](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

