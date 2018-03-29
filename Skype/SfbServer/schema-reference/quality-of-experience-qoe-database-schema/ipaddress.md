---
title: Ip 地址表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Ip 地址表将 IP 地址映射到体验质量数据库中的其他位置使用唯一 IP 地址标识。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a><span data-ttu-id="8240c-104">Ip 地址表</span><span class="sxs-lookup"><span data-stu-id="8240c-104">IPAddress table</span></span>
 
<span data-ttu-id="8240c-105">Ip 地址表将 IP 地址映射到体验质量数据库中的其他位置使用唯一 IP 地址标识。</span><span class="sxs-lookup"><span data-stu-id="8240c-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="8240c-106">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="8240c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8240c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8240c-107">**Column**</span></span>|<span data-ttu-id="8240c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8240c-108">**Data Type**</span></span>|<span data-ttu-id="8240c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8240c-109">**Key/Index**</span></span>|<span data-ttu-id="8240c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8240c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8240c-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="8240c-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="8240c-112">int</span><span class="sxs-lookup"><span data-stu-id="8240c-112">int</span></span>  <br/> |<span data-ttu-id="8240c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8240c-113">Primary</span></span>  <br/> |<span data-ttu-id="8240c-114">指定的 IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8240c-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="8240c-115">**Ip 地址**</span><span class="sxs-lookup"><span data-stu-id="8240c-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="8240c-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="8240c-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="8240c-117">唯一</span><span class="sxs-lookup"><span data-stu-id="8240c-117">Unique</span></span>  <br/> |<span data-ttu-id="8240c-118">唯一的 IP 地址 (例如，189.168.1.1) 映射到 IpAddressKey。</span><span class="sxs-lookup"><span data-stu-id="8240c-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="8240c-119">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="8240c-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

