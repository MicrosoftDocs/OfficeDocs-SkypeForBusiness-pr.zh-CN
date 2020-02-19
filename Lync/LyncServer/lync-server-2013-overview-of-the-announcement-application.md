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
ms.openlocfilehash: 264fbf5faf3fbce830a8d55cd7626d1ff67c2d58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="2fc59-102">Lync Server 2013 中的通知应用程序概述</span><span class="sxs-lookup"><span data-stu-id="2fc59-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fc59-103">_**上次修改的主题：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="2fc59-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="2fc59-104">当您部署通知应用程序时，您需要配置一个未分配号码表，该表格决定了当有人拨打未分配号码时要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="2fc59-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="2fc59-105">未分配号码表包含对组织有效的电话号码的范围，并指定哪个通知应用程序处理每个范围。</span><span class="sxs-lookup"><span data-stu-id="2fc59-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="2fc59-106">当呼叫者拨打对您的组织有效但未分配给任何人的电话号码时，Lync Server 将在未分配号码路由表中查找该号码，确定该号码属于哪个范围，并将呼叫路由到通知为该范围指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc59-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="2fc59-107">通知应用程序应答呼叫并播放音频消息（如果已将其配置为执行此操作），然后断开呼叫连接或将其传输到预先确定的目标，例如操作员。</span><span class="sxs-lookup"><span data-stu-id="2fc59-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="2fc59-108">您可以使用 Lync Server 命令行管理程序 cmdlet 来配置多个音频消息或传输目标。</span><span class="sxs-lookup"><span data-stu-id="2fc59-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="2fc59-p102">配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="2fc59-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="2fc59-114">在 Lync Server 2013 中，通知应用程序将随响应组应用程序一起自动安装。</span><span class="sxs-lookup"><span data-stu-id="2fc59-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="2fc59-115">通知和响应组应用程序是企业语音部署的标准组件：部署企业语音时，将自动部署这两个应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc59-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

