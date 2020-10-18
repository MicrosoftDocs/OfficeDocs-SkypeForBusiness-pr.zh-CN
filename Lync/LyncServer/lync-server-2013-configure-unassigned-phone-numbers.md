---
title: Lync Server 2013：配置未分配的电话号码
description: Lync Server 2013：配置未分配的电话号码。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702f297ea0a77d5e81be8b650a514ea4fa939d32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578048"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="a9cd2-103">在 Lync Server 2013 中配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="a9cd2-103">Configure unassigned phone numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9cd2-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a9cd2-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a9cd2-105">Lync Server 允许您配置对你的组织有效但未分配给用户或电话的电话号码的传入呼叫发生的情况。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-105">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="a9cd2-106">若要配置对此类呼叫的处理，请设置未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-106">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="a9cd2-107">您可以使用表将呼叫路由到通知应用程序或 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-107">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="a9cd2-p102">配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码定制所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码并将其分配给提供新号码的通知。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9cd2-114">在配置未分配号码表之前，必须已定义一个或多个通知，或者已设置 Exchange UM 自动助理。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-114">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="a9cd2-115">有关创建通知的详细信息，请参阅 <A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</A>。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-115">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="a9cd2-116">若要查看是否已配置 Exchange UM 设置，请运行 <STRONG>CsExUmContact</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-116">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="a9cd2-117">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9cd2-118">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a9cd2-118">In This Section</span></span>

  - [<span data-ttu-id="a9cd2-119">在 Lync Server 2013 中创建或修改未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="a9cd2-119">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="a9cd2-120">在 Lync Server 2013 中删除未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="a9cd2-120">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

