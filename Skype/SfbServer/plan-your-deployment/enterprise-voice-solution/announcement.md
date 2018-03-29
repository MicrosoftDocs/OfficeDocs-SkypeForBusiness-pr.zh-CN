---
title: 在 Skype for Business 2015 中规划通知应用程序
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 该规划业务服务器企业语音在 Skype 的发布应用程序，配置如何向您组织中未指定的电话号码的电话。 包括音频文件要求。
ms.openlocfilehash: c7ed700c749f1d5692b78c931e225fee5d0497be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-announcement-application-in-skype-for-business-2015"></a><span data-ttu-id="dffe5-104">在 Skype for Business 2015 中规划通知应用程序</span><span class="sxs-lookup"><span data-stu-id="dffe5-104">Plan for the Announcement application in Skype for Business 2015</span></span>
 
<span data-ttu-id="dffe5-105">该规划业务服务器企业语音在 Skype 的发布应用程序，配置如何向您组织中未指定的电话号码的电话。</span><span class="sxs-lookup"><span data-stu-id="dffe5-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="dffe5-106">包括音频文件要求。</span><span class="sxs-lookup"><span data-stu-id="dffe5-106">Includes audio file requirements.</span></span>
  
<span data-ttu-id="dffe5-107">Skype 业务服务器发布应用程序使您能够配置传入电话呼叫处理时拨叫的号码为您的组织有效但未分配给一个用户或一部电话。</span><span class="sxs-lookup"><span data-stu-id="dffe5-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="dffe5-108">可以将这些呼叫转换到预确定的目标（电话号码、SIP URI 或语音邮件）和/或播放音频通知。</span><span class="sxs-lookup"><span data-stu-id="dffe5-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="dffe5-109">该通知应用程序帮助您可以避免呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。</span><span class="sxs-lookup"><span data-stu-id="dffe5-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="dffe5-110">本部分包括规划特定于产品发布应用程序的信息</span><span class="sxs-lookup"><span data-stu-id="dffe5-110">This section includes planning information that is specific to the Announcement application</span></span>
  
<span data-ttu-id="dffe5-111">在部署时通知应用程序，您需要配置确定有人拨打未分配的号码时要采取的操作未分配数字表。</span><span class="sxs-lookup"><span data-stu-id="dffe5-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="dffe5-112">未分配的数字表包含区域组织有效的电话号码和指定的发布应用程序处理每个范围。</span><span class="sxs-lookup"><span data-stu-id="dffe5-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="dffe5-113">当呼叫者拨叫的电话号码，为您的组织有效，但不是授予任何人时，Skype 的业务服务器查找中未分配的数字路由表，数字标识哪些范围数落中，并将路由到该调用为该范围指定的发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="dffe5-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="dffe5-114">发布应用程序应答呼叫和播放的音频消息 （如果您配置它来做到这一点的） 然后断开与呼叫的连接或将其传送到一个预先确定的目标，如对运算符。</span><span class="sxs-lookup"><span data-stu-id="dffe5-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="dffe5-115">要配置多个音频邮件或者转移目标，可以使用业务服务器管理外壳 cmdlet 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="dffe5-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>
  
<span data-ttu-id="dffe5-p105">配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="dffe5-p105">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="dffe5-121">部署和要求</span><span class="sxs-lookup"><span data-stu-id="dffe5-121">Deployment and requirements</span></span>

<span data-ttu-id="dffe5-122">Tthe 发布应用程序会自动安装与响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="dffe5-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="dffe5-123">通知和响应组的应用程序的标准组件的企业语音部署： 部署企业语音时，这两个应用程序会自动部署。</span><span class="sxs-lookup"><span data-stu-id="dffe5-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span> 
  
### <a name="software-requirements"></a><span data-ttu-id="dffe5-124">软件要求</span><span class="sxs-lookup"><span data-stu-id="dffe5-124">Software requirements</span></span>

<span data-ttu-id="dffe5-125">运行发布应用程序的所有前端服务器或标准版服务器必须运行 Windows Server 2012 的服务器中运行 Windows Server 2008 R2 或 Microsoft 媒体基础的服务器安装的 Windows 媒体格式运行时或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="dffe5-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="dffe5-126">对于 Windows Server 2008 R2，Windows 媒体格式运行时安装作为 Windows 桌面体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="dffe5-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="dffe5-127">Windows 媒体格式运行时或 Microsoft 媒体基础是公告和音乐发布应用程序播放的 Windows Media 音频 (.wma) 文件需要。</span><span class="sxs-lookup"><span data-stu-id="dffe5-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span> 
  
### <a name="port-requirements"></a><span data-ttu-id="dffe5-128">端口要求</span><span class="sxs-lookup"><span data-stu-id="dffe5-128">Port Requirements</span></span>

<span data-ttu-id="dffe5-129">发布应用程序使用 SIP 侦听请求的**端口 5071** 。</span><span class="sxs-lookup"><span data-stu-id="dffe5-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dffe5-130">此端口是默认设置，您可以通过**设置 CsApplicationServer** cmdlet 更改。</span><span class="sxs-lookup"><span data-stu-id="dffe5-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="dffe5-131">此 cmdlet 的详细信息，请参阅有关业务服务器管理外壳程序文档 Skype。</span><span class="sxs-lookup"><span data-stu-id="dffe5-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="dffe5-132">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="dffe5-132">Audio File Requirements</span></span>

<span data-ttu-id="dffe5-133">发布应用程序支持波形 (.wav) 文件格式以及 Windows Media 音频 (.wma) 音乐和公告的文件格式。</span><span class="sxs-lookup"><span data-stu-id="dffe5-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="dffe5-134">发布应用程序的音频文件要求都响应组应用程序一样。</span><span class="sxs-lookup"><span data-stu-id="dffe5-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="dffe5-135">有关详细信息，请参阅[响应组的技术要求](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dffe5-135">For details, see [Technical Requirements for Response Groups](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>
  

