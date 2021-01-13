---
title: IPAddress 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表将 IP 地址映射到可在用户体验质量数据库中的任何其他位置使用的唯一 IP 地址标识符。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802772"
---
# <a name="ipaddress-table"></a><span data-ttu-id="d76ba-104">IPAddress 表</span><span class="sxs-lookup"><span data-stu-id="d76ba-104">IPAddress table</span></span>
 
<span data-ttu-id="d76ba-105">IPAddress 表将 IP 地址映射到可在用户体验质量数据库中的任何其他位置使用的唯一 IP 地址标识符。</span><span class="sxs-lookup"><span data-stu-id="d76ba-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d76ba-106">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="d76ba-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d76ba-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d76ba-107">**Column**</span></span>|<span data-ttu-id="d76ba-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d76ba-108">**Data Type**</span></span>|<span data-ttu-id="d76ba-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d76ba-109">**Key/Index**</span></span>|<span data-ttu-id="d76ba-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d76ba-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d76ba-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="d76ba-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="d76ba-112">int</span><span class="sxs-lookup"><span data-stu-id="d76ba-112">int</span></span>  <br/> |<span data-ttu-id="d76ba-113">主</span><span class="sxs-lookup"><span data-stu-id="d76ba-113">Primary</span></span>  <br/> |<span data-ttu-id="d76ba-114">指定的 IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d76ba-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="d76ba-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="d76ba-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="d76ba-116">varchar (50) </span><span class="sxs-lookup"><span data-stu-id="d76ba-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="d76ba-117">独特</span><span class="sxs-lookup"><span data-stu-id="d76ba-117">Unique</span></span>  <br/> |<span data-ttu-id="d76ba-p103">映射到 IpAddressKey 的唯一 IP 地址（例如，189.168.1.1）。这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="d76ba-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

