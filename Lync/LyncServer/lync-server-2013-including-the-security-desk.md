---
title: Lync Server 2013：包括安全桌面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d792626a973a790313b2cdc1bd9df9092175f28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="99f9f-102">在 Lync Server 2013 中包括安全桌面</span><span class="sxs-lookup"><span data-stu-id="99f9f-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99f9f-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="99f9f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="99f9f-p101">公司可能要求安全服务台参与紧急呼叫。为帮助确定如何将安全服务台集成到 E9-1-1 部署，应回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="99f9f-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="99f9f-106">**发出紧急呼叫时，是否希望通知安全服务台？**</span><span class="sxs-lookup"><span data-stu-id="99f9f-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="99f9f-107">你可以配置位置策略，以便 Lync 服务器向一个或多个安全人员的 Lync SIP 地址发送即时消息（IM）警报。</span><span class="sxs-lookup"><span data-stu-id="99f9f-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="99f9f-108">这些警报包含拨打紧急呼叫的人员的姓名、号码和位置，并可在紧急情况下实现安全性。</span><span class="sxs-lookup"><span data-stu-id="99f9f-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="99f9f-109">**是否要在发出每个紧急呼叫时通知安全服务台？**</span><span class="sxs-lookup"><span data-stu-id="99f9f-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="99f9f-p103">如果紧急服务服务提供商支持，可以将位置策略配置为在每个紧急呼叫中包含回拨号码。提供商随后使用此号码通知组织的安全人员参加有关紧急呼叫的会议。可在位置策略中将此会议配置为单向（仅侦听）或双向（双向）。</span><span class="sxs-lookup"><span data-stu-id="99f9f-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99f9f-p104">如果需要，可针对每个位置策略配置不同的紧急服务人员。这允许您为公司内的不同区域自定义响应，或为来自与网络外部相对的网络内部的紧急呼叫创建不同的行为。您可使用通讯组指定要通知的人员。</span><span class="sxs-lookup"><span data-stu-id="99f9f-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

