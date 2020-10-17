---
title: Lync Server 2013：配置未分配号码表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c73027511ec8798010f1d22fb9bd19eeab27a7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520249"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="6e6bb-102">在 Lync Server 2013 中配置未分配号码表</span><span class="sxs-lookup"><span data-stu-id="6e6bb-102">Configure the unassigned number table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e6bb-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6e6bb-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6e6bb-104">在 Lync Server 2013 中，您可以指定对组织有效但未分配给用户或电话的电话号码传入呼叫发生的情况。</span><span class="sxs-lookup"><span data-stu-id="6e6bb-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="6e6bb-105">呼叫者可以收听消息或将消息路由到其他目标，或同时实现这两者。</span><span class="sxs-lookup"><span data-stu-id="6e6bb-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="6e6bb-p102">配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。</span><span class="sxs-lookup"><span data-stu-id="6e6bb-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e6bb-112">在配置未分配号码表之前，系统必须已定义通知，或已设置 Exchange 统一消息 (UM) 自动助理。</span><span class="sxs-lookup"><span data-stu-id="6e6bb-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="6e6bb-113">当某人呼叫未分配的号码时，Lync Server 将从上到下搜索未分配号码表，并使用第一个匹配的范围。</span><span class="sxs-lookup"><span data-stu-id="6e6bb-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="6e6bb-114">因此，要在万不得已时执行的操作应指定给表中最后一个范围。</span><span class="sxs-lookup"><span data-stu-id="6e6bb-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e6bb-115">本部分内容</span><span class="sxs-lookup"><span data-stu-id="6e6bb-115">In This Section</span></span>

<span data-ttu-id="6e6bb-116">[在 lync server 2013 中创建或修改未分配号码范围在](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 2013 中创建通知](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="6e6bb-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

