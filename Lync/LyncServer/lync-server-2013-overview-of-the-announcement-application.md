---
title: Lync Server 2013：通知应用程序概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0bceaef7a165f4594d825a80b93ee167b68c85a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520809"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的通知应用程序概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-13_

当您部署通知应用程序时，您需要配置一个未分配号码表，该表格决定了当有人拨打未分配号码时要采取的操作。 未分配号码表包含对组织有效的电话号码的范围，并指定哪个通知应用程序处理每个范围。 当呼叫者拨打对您的组织有效但未分配给任何人的电话号码时，Lync Server 将在未分配号码路由表中查找该号码，确定该号码属于哪个范围，并将呼叫路由到该范围指定的通知应用程序。 通知应用程序将应答呼叫，并在将其配置为执行此操作时播放音频邮件 () 然后断开呼叫连接或将其传输到预先确定的目标（如操作员）。 您可以使用 Lync Server 命令行管理程序 cmdlet 来配置多个音频消息或传输目标。

配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。

在 Lync Server 2013 中，通知应用程序将随响应组应用程序一起自动安装。 通知和响应组应用程序是企业语音部署的标准组件：部署企业语音时，将自动部署这两个应用程序。

</div>

<span> </span>

</div>

</div>

</div>

