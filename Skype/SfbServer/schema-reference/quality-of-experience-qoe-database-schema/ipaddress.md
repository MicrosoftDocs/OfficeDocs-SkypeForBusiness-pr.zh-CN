---
title: IPAddress 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212205"
---
# <a name="ipaddress-table"></a><span data-ttu-id="cfa95-104">IPAddress 表</span><span class="sxs-lookup"><span data-stu-id="cfa95-104">IPAddress table</span></span>
 
<span data-ttu-id="cfa95-105">IPAddress 表将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。</span><span class="sxs-lookup"><span data-stu-id="cfa95-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="cfa95-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cfa95-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cfa95-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cfa95-107">**Column**</span></span>|<span data-ttu-id="cfa95-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cfa95-108">**Data Type**</span></span>|<span data-ttu-id="cfa95-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="cfa95-109">**Key/Index**</span></span>|<span data-ttu-id="cfa95-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cfa95-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfa95-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="cfa95-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="cfa95-112">int</span><span class="sxs-lookup"><span data-stu-id="cfa95-112">int</span></span>  <br/> |<span data-ttu-id="cfa95-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cfa95-113">Primary</span></span>  <br/> |<span data-ttu-id="cfa95-114">指定的 IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="cfa95-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="cfa95-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="cfa95-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="cfa95-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="cfa95-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="cfa95-117">唯一</span><span class="sxs-lookup"><span data-stu-id="cfa95-117">Unique</span></span>  <br/> |<span data-ttu-id="cfa95-118">唯一的 IP 地址 (例如，189.168.1.1) 映射到 IpAddressKey。</span><span class="sxs-lookup"><span data-stu-id="cfa95-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="cfa95-119">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="cfa95-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

