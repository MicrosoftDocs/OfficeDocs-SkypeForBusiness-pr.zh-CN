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
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="619fe-102">在 Lync Server 2013 中配置未分配号码表</span><span class="sxs-lookup"><span data-stu-id="619fe-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="619fe-103">_**主题上次修改时间：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="619fe-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="619fe-104">在 Lync Server 2013 中，你可以指定传入呼叫对你的组织有效但未分配给用户或手机的电话号码所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="619fe-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="619fe-105">呼叫者可以听到消息，也可以将消息路由到另一个目标，或者同时路由到其他目标。</span><span class="sxs-lookup"><span data-stu-id="619fe-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="619fe-p102">配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。</span><span class="sxs-lookup"><span data-stu-id="619fe-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="619fe-112">配置 "未分配的号码" 表之前，您的系统必须已定义公告或 "Exchange 统一消息（UM）" 自动助理设置。</span><span class="sxs-lookup"><span data-stu-id="619fe-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="619fe-113">当某人呼叫未分配的号码时，Lync Server 将从上到下搜索 "未分配的号码" 表，并使用第一个匹配区域。</span><span class="sxs-lookup"><span data-stu-id="619fe-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="619fe-114">因此，要在万不得已时执行的操作应指定给表中最后一个范围。</span><span class="sxs-lookup"><span data-stu-id="619fe-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="619fe-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="619fe-115">In This Section</span></span>

<span data-ttu-id="619fe-116">[在 lync server 2013 中创建或修改未分配的号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md)在[lync server 2013 中创建公告](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="619fe-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

