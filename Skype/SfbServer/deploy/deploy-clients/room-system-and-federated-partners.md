---
title: Skype 会议室系统和 Skype for Business 联盟伙伴
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
ms.openlocfilehash: e954bf5d7586c651d9d045b2d428f86f01de8a30
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699542"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="e79ed-103">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="e79ed-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="e79ed-104">阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="e79ed-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="e79ed-105">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="e79ed-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="e79ed-106">Skype 会议室系统依赖于业务会议链接日历会议请求中的加入 Skype。</span><span class="sxs-lookup"><span data-stu-id="e79ed-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="e79ed-107">加入链接通常可在会议请求的正文中找到。</span><span class="sxs-lookup"><span data-stu-id="e79ed-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="e79ed-108">但是，Skype 会议室系统取决于此链接出现在邮件的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="e79ed-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="e79ed-109">此会议的请求时是发送到远程组织 (Skype 联合的业务合作伙伴的)，默认情况下远程组织的 Skype 会议室系统将不会显示与会日历的链接。</span><span class="sxs-lookup"><span data-stu-id="e79ed-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="e79ed-110">实际上，远程组织中的任何 Outlook 用户将无法加入的日历的右键单击与业务会议 Skype 项目或从会议提醒中。</span><span class="sxs-lookup"><span data-stu-id="e79ed-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="e79ed-111">它们必须打开会议邀请，并单击加入 Skype 的邮件正文中的业务会议。</span><span class="sxs-lookup"><span data-stu-id="e79ed-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="e79ed-112">此限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊方法来打包用于跨 Internet 发送邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="e79ed-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="e79ed-113">对于从 Exchange 组织外部发送的邮件，此方法（称为传输中立封装格式 (TNEF)）默认情况下被禁用。</span><span class="sxs-lookup"><span data-stu-id="e79ed-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="e79ed-114">会议加入链接上远程 Skype 会议室系统，显示发送组织必须使用以下命令来启用 TNEF:</span><span class="sxs-lookup"><span data-stu-id="e79ed-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="e79ed-115">在为远程组织启用 TNEF 之后，通过 Internet 发送到该组织的任何邮件都将采用 TNEF 格式作为附件发送。</span><span class="sxs-lookup"><span data-stu-id="e79ed-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="e79ed-116">使用 TNEF 启用时的 Skype, 业务会议请求是发送到的业务联盟伙伴，Skype Skype 会议室系统都将能够加入 Skype 呈现业务会议和远程用户将能够加入 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="e79ed-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 