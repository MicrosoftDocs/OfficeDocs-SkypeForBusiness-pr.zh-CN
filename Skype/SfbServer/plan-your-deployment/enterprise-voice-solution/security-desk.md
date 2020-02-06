---
title: 在 Skype for Business 服务器中包括安全桌面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 在 Skype for business Server 企业语音中，计划如何在 E9 部署中加入组织的安全桌面。
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802452"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="a12c2-103">在 Skype for Business 服务器中包括安全桌面</span><span class="sxs-lookup"><span data-stu-id="a12c2-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="a12c2-104">在 Skype for business Server 企业语音中，计划如何在 E9 部署中加入组织的安全桌面。</span><span class="sxs-lookup"><span data-stu-id="a12c2-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a12c2-p101">公司可能要求安全服务台参与紧急呼叫。为帮助确定如何将安全服务台集成到 E9-1-1 部署，应回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="a12c2-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="a12c2-107">**发出紧急呼叫时，是否希望通知安全服务台？**</span><span class="sxs-lookup"><span data-stu-id="a12c2-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="a12c2-108">你可以配置位置策略，以便 Skype for Business 服务器向一个或多个安全人员的 Skype for business SIP 地址发送即时消息（IM）警报。</span><span class="sxs-lookup"><span data-stu-id="a12c2-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="a12c2-109">这些警报包含拨打紧急呼叫的人员的姓名、号码和位置，并可在紧急情况下实现安全性。</span><span class="sxs-lookup"><span data-stu-id="a12c2-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="a12c2-110">**是否要在发出每个紧急呼叫时通知安全服务台？**</span><span class="sxs-lookup"><span data-stu-id="a12c2-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="a12c2-p103">如果紧急服务服务提供商支持，可以将位置策略配置为在每个紧急呼叫中包含回拨号码。提供商随后使用此号码通知组织的安全人员参加有关紧急呼叫的会议。可在位置策略中将此会议配置为单向（仅侦听）或双向（双向）。</span><span class="sxs-lookup"><span data-stu-id="a12c2-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a12c2-p104">如果需要，可针对每个位置策略配置不同的紧急服务人员。这允许您为公司内的不同区域自定义响应，或为来自与网络外部相对的网络内部的紧急呼叫创建不同的行为。您可使用通讯组指定要通知的人员。</span><span class="sxs-lookup"><span data-stu-id="a12c2-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

