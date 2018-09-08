---
title: Plan for Business 的 Skype 中的通知应用程序
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 规划业务 Server 企业语音中 Skype 的通知应用程序，其配置如何处理对组织中的未分配的电话号码的电话呼叫。 包括音频文件要求。
ms.openlocfilehash: 2642dc13653f18520371b31c9e5ff41bc6a479d3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882103"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a><span data-ttu-id="c1e5b-104">Plan for Business 的 Skype 中的通知应用程序</span><span class="sxs-lookup"><span data-stu-id="c1e5b-104">Plan for the Announcement application in Skype for Business</span></span>

<span data-ttu-id="c1e5b-105">规划业务 Server 企业语音中 Skype 的通知应用程序，其配置如何处理对组织中的未分配的电话号码的电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="c1e5b-106">包括音频文件要求。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-106">Includes audio file requirements.</span></span>

<span data-ttu-id="c1e5b-107">业务服务器通知应用程序的 Skype 使您能够配置处理的传入电话呼叫时所拨打的号码供您的组织，但未分配给用户或电话。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="c1e5b-108">可以将这些呼叫转换到预确定的目标（电话号码、SIP URI 或语音邮件）和/或播放音频通知。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="c1e5b-109">该通知应用程序帮助您可以避免呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="c1e5b-110">本节包括特定于通知应用程序的规划信息</span><span class="sxs-lookup"><span data-stu-id="c1e5b-110">This section includes planning information that is specific to the Announcement application</span></span>

<span data-ttu-id="c1e5b-111">通知应用程序部署时，您需要配置确定当某人拨打未分配的号码时要采取的操作未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="c1e5b-112">未分配号码表包含有效的组织的电话号码的区域，并指定的通知应用程序处理每个范围。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="c1e5b-113">当呼叫者拨电话号码供组织使用但未分配给任何人时，Skype 的业务服务器查找，未分配号码路由表中的数字标识的范围中属于和路由对呼叫数为该区域指定的通知应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="c1e5b-114">通知应用程序应答呼叫 （如果您配置其） 播放音频消息，然后断开呼叫或将其传输到预定目标，如到一个运算符。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="c1e5b-115">配置多个音频消息或传送目标的呼叫，可以使用 Skype 业务 Server Management Shell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="c1e5b-p105">配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-p105">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="c1e5b-121">部署和要求</span><span class="sxs-lookup"><span data-stu-id="c1e5b-121">Deployment and requirements</span></span>

<span data-ttu-id="c1e5b-122">响应组应用程序自动安装它通知应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="c1e5b-123">通知和响应组应用程序是企业语音部署的标准组件： 当您部署企业语音时，这两个这些应用程序会自动部署。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="c1e5b-124">软件要求</span><span class="sxs-lookup"><span data-stu-id="c1e5b-124">Software requirements</span></span>

<span data-ttu-id="c1e5b-125">运行通知应用程序的所有前端服务器或 Standard Edition 服务器必须运行 Windows Server 2012 的服务器运行 Windows Server 2008 R2 或 Microsoft 媒体 Foundation 的服务器上安装 Windows Media Format Runtime 或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="c1e5b-126">对于 Windows Server 2008 R2，作为 Windows 桌面体验的一部分安装 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="c1e5b-127">Windows Media Format Runtime 或 Microsoft 媒体基础，则需要 Windows Media 音频 (.wma) 文件的通知应用程序播放通知和保持音乐。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="c1e5b-128">端口要求</span><span class="sxs-lookup"><span data-stu-id="c1e5b-128">Port Requirements</span></span>

<span data-ttu-id="c1e5b-129">通知应用程序使用**端口 5071**用于 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>

> [!NOTE]
> <span data-ttu-id="c1e5b-130">此端口是默认设置，您可以使用**集 CsApplicationServer** cmdlet 更改。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="c1e5b-131">有关此 cmdlet 的详细信息，请参阅 Business Server Management Shell 文档 Skype。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="c1e5b-132">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="c1e5b-132">Audio File Requirements</span></span>

<span data-ttu-id="c1e5b-133">通知应用程序支持 Wave (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式音乐和公告。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="c1e5b-134">通知应用程序的音频文件要求都与响应组应用程序相同。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="c1e5b-135">有关详细信息，请参阅[响应组的技术要求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c1e5b-135">For details, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>


