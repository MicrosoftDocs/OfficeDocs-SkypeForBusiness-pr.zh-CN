---
title: Skype for Business 服务器中的系统使用情况报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 187d316d-2456-417e-b636-05527a18ef06
description: 摘要：了解 Skype for Business 服务器中的系统使用情况报告。
ms.openlocfilehash: c5fc4e59de4dd66da40d07c17bb615e5abc697a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817641"
---
# <a name="system-usage-reports-in-skype-for-business-server"></a><span data-ttu-id="a0e9d-103">Skype for Business 服务器中的系统使用情况报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-103">System usage reports in Skype for Business Server</span></span>
 
<span data-ttu-id="a0e9d-104">**摘要：** 了解 Skype for Business 服务器中的系统使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-104">**Summary:** Learn about the System Usage Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="a0e9d-105">系统使用情况报告提供基于 Skype for Business 服务器收集的呼叫详细记录（CDR）数据的系统使用信息。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-105">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a0e9d-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="a0e9d-106">In this section</span></span>

- [<span data-ttu-id="a0e9d-107">Skype for Business 服务器中的用户注册报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-107">User Registration Report in Skype for Business Server</span></span>](user-registration-report.md)
    
    <span data-ttu-id="a0e9d-108">提供基于注册事件（如用户登录）的 Skype for Business 服务器部署的用户连接摘要。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-108">Provides a summary of user connectivity to the Skype for Business Server deployment based on registration events such as user logons.</span></span> <span data-ttu-id="a0e9d-109">报表提供一种查看内部和外部登录的方式，并将登录到 Skype for business 服务器的用户数与在登录时实际使用该服务的用户数进行比较。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-109">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Skype for Business Server with the number of users who actually used the service while they were logged on.</span></span>
    
- [<span data-ttu-id="a0e9d-110">Skype for Business Server 中的对等活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-110">Peer-to-Peer Activity Summary Report in Skype for Business Server</span></span>](peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="a0e9d-p102">提供对等即时消息 (IM)、音频、视频、文件传输和应用程序共享会话摘要。对等会话是指仅涉及两个用户的会话。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>
    
- [<span data-ttu-id="a0e9d-113">Skype for Business 服务器中的会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-113">Conference Summary Report in Skype for Business Server</span></span>](conference-summary-report.md)
    
    <span data-ttu-id="a0e9d-114">提供所有会议活动摘要。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-114">Provides a summary of all conference activities.</span></span> <span data-ttu-id="a0e9d-115">会议是涉及三个或更多人的会话。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-115">Conferences are sessions involving three or more people.</span></span>
    
- [<span data-ttu-id="a0e9d-116">Skype for Business 服务器中的 PSTN 会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-116">PSTN Conference Summary Report in Skype for Business Server</span></span>](pstn-conference-summary-report.md)
    
    <span data-ttu-id="a0e9d-117">提供所有 PSTN 会议摘要。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-117">Provides a summary of all PSTN conferences.</span></span> <span data-ttu-id="a0e9d-118">这些会议是至少一个用户使用公用电话交换网 (PSTN) 拨入的会议，该会议又称为电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-118">These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as dial-in conferencing.</span></span>
    
- [<span data-ttu-id="a0e9d-119">Skype for Business 服务器中的 "响应组使用情况" 报表</span><span class="sxs-lookup"><span data-stu-id="a0e9d-119">Response Group Usage Report in Skype for Business Server</span></span>](response-group-usage-report.md)
    
    <span data-ttu-id="a0e9d-120">提供响应组使用情况的摘要。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-120">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="a0e9d-121">"响应组" 应用程序为您提供了一种自动将电话呼叫路由到诸如帮助台或客户支持行等实体的方式。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-121">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>
    
- [<span data-ttu-id="a0e9d-122">Skype for Business 服务器中的 IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-122">IP Phone Inventory Report in Skype for Business Server</span></span>](ip-phone-inventory-report.md)
    
    <span data-ttu-id="a0e9d-123">提供有关当前在组织中使用的 IP 电话的信息。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-123">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="a0e9d-124">报表基于电话注册和登录。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-124">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="a0e9d-125">不应将其视为完整库存。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-125">It should not be considered a complete inventory.</span></span> <span data-ttu-id="a0e9d-126">例如，您可能已删除了仍在报告中列出的手机，因为他们至少登录过一次。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-126">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="a0e9d-127">同样，您还可能有新的手机不会显示在报告中，只是因为用户尚未登录到 Skype for business 服务器以及他们的新电话。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-127">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Skype for Business Server with their new phones yet.</span></span>
    
- [<span data-ttu-id="a0e9d-128">Skype for Business 服务器中的呼叫许可控制报告</span><span class="sxs-lookup"><span data-stu-id="a0e9d-128">Call Admission Control Report in Skype for Business Server</span></span>](call-admission-control-report.md)
    
    <span data-ttu-id="a0e9d-p107">提供使用呼叫允许控制的对等活动和会议活动的列表。呼叫允许控制 (CAC) 是一种确定是否应根据带宽限制允许建立实时通信会话（如语音呼叫或视频呼叫）的方法。</span><span class="sxs-lookup"><span data-stu-id="a0e9d-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>
    

