---
title: Skype for Business Online 报告 cmdlet 和 REST web 服务
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1e11b4c9d68dbc5e177d684cd3053a83df8ea
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="5e8ea-102">Skype for Business Online 报告 cmdlet 和 REST web 服务</span><span class="sxs-lookup"><span data-stu-id="5e8ea-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e8ea-103">_**主题上次修改时间:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="5e8ea-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="5e8ea-104">通过结合报告功能, Skype for Business Online 提供对五个 Windows PowerShell cmdlet 的访问权限, 可帮助生成这些报告, 并且管理员也可以使用这些 cmdlet 返回自定义报告数据。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="5e8ea-105">Skype for Business Online 还包括 REST (Representational 状态转移), 开发人员可以使用它们检索自定义报告信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="5e8ea-106">管理员可用的报告 cmdlet 包括:</span><span class="sxs-lookup"><span data-stu-id="5e8ea-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="5e8ea-107">CsActiveUserReport, 它提供有关活动用户数 (即登录到 Skype for Business Online 的用户以及至少参与了一个会议或对等通信会话) 的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="5e8ea-108">CsAVConferenceTimeReport, 提供有关用户在音频/视频会议中花费的时间量 (以分钟为单位) 的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="5e8ea-109">CsConferenceReport, 提供有关用户参与的会议的数量和类型的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="5e8ea-110">CsP2PAVTimeReport, 它提供有关用户在包含音频和/或视频的对等会话中花费的时间量 (以分钟为单位) 的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="5e8ea-111">CsP2PSessionReport, 提供有关用户参与的对等会话的数量和类型的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="5e8ea-112">大多数管理员将使用 Microsoft 365 管理中心提供的报表: 不仅是自动生成的报表, 还提供了数据的图形化表示形式, 这些数据通常更易于理解, 而不是所返回的原始数字值报告 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="5e8ea-113">但是, 熟悉 Windows PowerShell 的管理员可以使用报告 cmdlet 从 Lync Online 报告中返回不容易提供的数据。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="5e8ea-114">例如, 报告 cmdlet 返回有关会话持续时间的信息 (每个会话持续时间的分钟数)。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="5e8ea-115">使用 Lync Online 报表不提供单个会话持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="5e8ea-116">同样, 在 "每日" 视图中, Lync Online 报表仅显示之前14天的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="5e8ea-117">如果您想要查看不同日期的每日总计 (例如, 四个月前的日期), 您可以使用报告 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="5e8ea-118">管理员还可能对[使用 Excel 检索 Office 365 报告数据](http://msdn.microsoft.com/en-us/library/dn781442.aspx)的文章感兴趣, 其中介绍了如何使用 Microsoft Excel 中的 OData 数据查询功能来创建自定义 Office 365 报表。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/en-us/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="5e8ea-119">自定义报表使你能够指示从 Office 365 报告服务返回哪些数据 (以及多少数据)。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="5e8ea-120">自定义报表还允许你执行如下操作: 指定应如何对数据进行排序和分组, 并提供对不在管理中心中显示的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="5e8ea-121">具有开发背景的管理员可以使用 REST web 服务获取未在 Skype for Business Online 管理中心中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="5e8ea-122">REST 服务类似于 SOAP 服务, 因为每种技术都提供了一种在客户端和服务器之间传输 XML 数据的方法。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="5e8ea-123">但是, REST 服务至少具有与 SOAP 服务相比的两个优势。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="5e8ea-124">对于一个, REST 使用称为 ATOM 供稿格式的标准化格式执行 XML 数据传输。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="5e8ea-125">相比之下, 传输数据时使用非标准格式的 SOAP。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="5e8ea-126">此外, REST 能够跨阻止 "获取" 和 "发布" 等 HTTP 谓词的网络传输数据。</span><span class="sxs-lookup"><span data-stu-id="5e8ea-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5e8ea-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e8ea-127">See Also</span></span>


<span data-ttu-id="5e8ea-128">[Lync Online 报告](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5e8ea-128">[Lync Online reporting](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="5e8ea-129">Office 365 报告 Web 服务</span><span class="sxs-lookup"><span data-stu-id="5e8ea-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[<span data-ttu-id="5e8ea-130">了解 Office 365 Reporting Web 服务</span><span class="sxs-lookup"><span data-stu-id="5e8ea-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
<span data-ttu-id="5e8ea-131">[Exchange Online 报告 Cmdlet](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5e8ea-131">[The Exchange Online Reporting Cmdlets](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="5e8ea-132">使用 Excel 检索 Office 365 报告数据</span><span class="sxs-lookup"><span data-stu-id="5e8ea-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

