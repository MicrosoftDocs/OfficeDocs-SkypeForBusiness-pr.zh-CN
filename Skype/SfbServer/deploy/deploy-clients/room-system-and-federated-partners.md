---
title: Skype 会议室系统和 Skype for Business 联盟伙伴
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
ms.openlocfilehash: 040af495217217b3bfd10fb577b7194df354e027
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="70cd9-103">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="70cd9-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="70cd9-104">阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="70cd9-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="70cd9-105">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="70cd9-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="70cd9-106">Skype 的空间系统依赖于业务会议链接日历会议请求中加入 Skype。</span><span class="sxs-lookup"><span data-stu-id="70cd9-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="70cd9-107">加入链接通常可在会议请求的正文中找到。</span><span class="sxs-lookup"><span data-stu-id="70cd9-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="70cd9-108">但是，Skype 的空间系统取决于消息的 MAPI 属性中存在此链接。</span><span class="sxs-lookup"><span data-stu-id="70cd9-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="70cd9-109">当此会议请求发送到远程组织 (Skype 联合的商业伙伴)，默认情况下远程组织的 Skype 的空间系统将不会显示在日历的会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="70cd9-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="70cd9-110">实际上，远程组织中的任何 Outlook 用户将不能参加商务会议，用右键单击该日历的 Skype 项目，还是从会议提醒内。</span><span class="sxs-lookup"><span data-stu-id="70cd9-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="70cd9-111">他们必须打开会议邀请并单击加入 Skype 在邮件正文中的商务会议。</span><span class="sxs-lookup"><span data-stu-id="70cd9-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="70cd9-112">此限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊方法来打包用于跨 Internet 发送邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="70cd9-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="70cd9-113">对于从 Exchange 组织外部发送的邮件，此方法（称为传输中立封装格式 (TNEF)）默认情况下被禁用。</span><span class="sxs-lookup"><span data-stu-id="70cd9-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="70cd9-114">会议联接链接出现在远程的 Skype 的空间系统，发送组织必须使用以下命令来启用 TNEF:</span><span class="sxs-lookup"><span data-stu-id="70cd9-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="70cd9-115">在为远程组织启用 TNEF 之后，通过 Internet 发送到该组织的任何邮件都将采用 TNEF 格式作为附件发送。</span><span class="sxs-lookup"><span data-stu-id="70cd9-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="70cd9-116">与已启用的 TNEF 时为 Skype, 业务会议请求发送到对商业联盟伙伴，Skype Skype 的空间系统将能够呈现联接 Skype 业务会议和远程用户将能够加入 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="70cd9-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 