---
title: 'Lync Server 2013: 公告应用程序概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e9cedddf6dfdf714bb3d0eef0e0cd01063b89f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的公告应用程序概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-13_

部署公告应用程序时, 需要配置一个未分配的数字表, 用于确定当某人拨打未分配的号码时要执行的操作。 "未分配的号码" 表包含对组织有效的电话号码范围, 并指定哪个公告应用程序处理每个范围。 当呼叫者拨打对您的组织有效但未分配给任何人的电话号码时, Lync Server 将在 "未分配的号码" 路由表中查找该号码, 标识该号码所属的范围, 并将呼叫路由到公告为该范围指定的应用程序。 "通知" 应用程序将应答呼叫并播放音频消息 (如果将其配置为执行此操作), 然后断开通话或将其转移到预先确定的目标, 如 "操作员"。 你可以使用 Lync Server Management Shell cmdlet 配置多条音频消息或传输目标。

配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。

在 Lync Server 2013 中, 通知应用程序将随响应组应用程序一起自动安装。 "通知" 和 "响应" 组应用程序是企业语音部署的标准组件: 当部署企业语音时, 将自动部署这两个应用程序。

</div>

<span> </span>

</div>

</div>

</div>

