---
title: Skype for Business Online 报告 cmdlet 和 REST web 服务
description: Skype for Business Online 报告 cmdlet 和 REST web 服务。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2160e0910d42f811ec8b03fa50450d5f73c59b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567938"
---
# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="7e630-103">Skype for Business Online 报告 cmdlet 和 REST web 服务</span><span class="sxs-lookup"><span data-stu-id="7e630-103">The Skype for Business Online reporting cmdlets and REST web service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e630-104">_**上次修改的主题：** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="7e630-104">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="7e630-105">通过与报告功能结合使用，Skype for Business Online 提供了对五个 Windows PowerShell cmdlet 的访问权限，可帮助生成这些报告，并且管理员也可以使用它们返回自定义报告数据。</span><span class="sxs-lookup"><span data-stu-id="7e630-105">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="7e630-106">Skype for Business Online 还包括 REST (代表性状态转移) ，可供开发人员用来检索自定义报告信息。</span><span class="sxs-lookup"><span data-stu-id="7e630-106">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="7e630-107">可供管理员使用的报告 cmdlet 包括：</span><span class="sxs-lookup"><span data-stu-id="7e630-107">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="7e630-108">Get-csactiveuserreport，它提供有关 (的活动用户数的信息，即登录到 Skype for Business Online 并参与至少一个会议或对等通信会话) 的用户。</span><span class="sxs-lookup"><span data-stu-id="7e630-108">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="7e630-109">Get-csavconferencetimereport，它提供有关) 用户在音频/视频会议中花费的 (时间量的信息（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="7e630-109">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="7e630-110">Get-csconferencereport，它提供有关用户参与的会议的数量和类型的信息。</span><span class="sxs-lookup"><span data-stu-id="7e630-110">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="7e630-111">Get-csp2pavtimereport，它提供有关) 用户在包含音频和/或视频的对等会话中花费的 (时间量（以分钟为单位）的信息。</span><span class="sxs-lookup"><span data-stu-id="7e630-111">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="7e630-112">Get-csp2psessionreport，它提供有关用户参与的对等会话的数量和类型的信息。</span><span class="sxs-lookup"><span data-stu-id="7e630-112">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="7e630-113">大多数管理员将使用 Microsoft 365 管理中心提供的报告：这些报告不仅是自动生成的，而且还提供了数据的图形表示形式，这些数据通常比报告 cmdlet 返回的原始号码值更容易理解。</span><span class="sxs-lookup"><span data-stu-id="7e630-113">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="7e630-114">但是，熟悉 Windows PowerShell 的管理员可以使用报告 cmdlet 从 Lync Online 报告中返回不容易提供的数据。</span><span class="sxs-lookup"><span data-stu-id="7e630-114">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="7e630-115">例如，报告 cmdlet 将返回有关会话持续时间的信息， (每个会话持续) 的时间量（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="7e630-115">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="7e630-116">使用 Lync Online 报告无法获取单个会话持续时间。</span><span class="sxs-lookup"><span data-stu-id="7e630-116">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="7e630-117">同样，在每日视图中，Lync Online 报告仅显示前14天的信息。</span><span class="sxs-lookup"><span data-stu-id="7e630-117">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="7e630-118">如果您想要查看不同天的每日汇总 (例如，从四个月前开始的日期) 您可以使用报告 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7e630-118">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="7e630-119">管理员可能还会对 [使用 Excel 检索 Office 365 报告数据](https://msdn.microsoft.com/library/dn781442.aspx)的文章感兴趣，这说明了如何使用 Microsoft Excel 中的 OData 数据查询功能创建自定义 Office 365 报告。</span><span class="sxs-lookup"><span data-stu-id="7e630-119">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="7e630-120">自定义报告使您能够规定哪些数据 (，以及从 Office 365 报告服务返回多少数据) 。</span><span class="sxs-lookup"><span data-stu-id="7e630-120">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="7e630-121">自定义报告还允许您执行以下操作：指定数据的排序和分组方式，并提供对不在管理中心中显示的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7e630-121">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="7e630-122">具有开发背景的管理员可以使用 REST web 服务来获取未在 Skype for Business Online 管理中心中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="7e630-122">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="7e630-123">REST 服务类似于 SOAP 服务，在这种服务中，每种技术都提供了一种在客户端和服务器之间传输 XML 数据的方法。</span><span class="sxs-lookup"><span data-stu-id="7e630-123">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="7e630-124">但是，REST 服务至少具有与 SOAP 服务相比的两个优势。</span><span class="sxs-lookup"><span data-stu-id="7e630-124">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="7e630-125">对于一个，REST 使用称为 ATOM 联合联合格式的标准化格式执行 XML 数据传输。</span><span class="sxs-lookup"><span data-stu-id="7e630-125">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="7e630-126">相比之下，在传输数据时，使用非标准格式的 SOAP。</span><span class="sxs-lookup"><span data-stu-id="7e630-126">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="7e630-127">此外，REST 可以跨阻止 GET 和 POST 之外的 HTTP 谓词的网络传输数据。</span><span class="sxs-lookup"><span data-stu-id="7e630-127">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7e630-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e630-128">See Also</span></span>


<span data-ttu-id="7e630-129">[Lync Online 报告](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7e630-129">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="7e630-130">Office 365 报告 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7e630-130">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="7e630-131">了解 Office 365 报告 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7e630-131">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="7e630-132">[Exchange Online 报告 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7e630-132">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="7e630-133">使用 Excel 检索 Office 365 报告数据</span><span class="sxs-lookup"><span data-stu-id="7e630-133">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

