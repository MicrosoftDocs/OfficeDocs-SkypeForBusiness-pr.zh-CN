---
title: IPAddress 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到 "体验质量" 数据库中其他位置使用的唯一 IP 地址标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809540"
---
# <a name="ipaddress-table"></a><span data-ttu-id="a33e0-104">IPAddress 表</span><span class="sxs-lookup"><span data-stu-id="a33e0-104">IPAddress table</span></span>
 
<span data-ttu-id="a33e0-105">IPAddress 表将 IP 地址映射到 "体验质量" 数据库中其他位置使用的唯一 IP 地址标识符。</span><span class="sxs-lookup"><span data-stu-id="a33e0-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a33e0-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a33e0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a33e0-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a33e0-107">**Column**</span></span>|<span data-ttu-id="a33e0-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a33e0-108">**Data Type**</span></span>|<span data-ttu-id="a33e0-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a33e0-109">**Key/Index**</span></span>|<span data-ttu-id="a33e0-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a33e0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a33e0-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="a33e0-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="a33e0-112">int</span><span class="sxs-lookup"><span data-stu-id="a33e0-112">int</span></span>  <br/> |<span data-ttu-id="a33e0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a33e0-113">Primary</span></span>  <br/> |<span data-ttu-id="a33e0-114">指定 IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a33e0-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="a33e0-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="a33e0-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="a33e0-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="a33e0-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="a33e0-117">唯一</span><span class="sxs-lookup"><span data-stu-id="a33e0-117">Unique</span></span>  <br/> |<span data-ttu-id="a33e0-118">映射到 IpAddressKey 的唯一 IP 地址（例如，189.168.1.1）。</span><span class="sxs-lookup"><span data-stu-id="a33e0-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="a33e0-119">这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a33e0-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

