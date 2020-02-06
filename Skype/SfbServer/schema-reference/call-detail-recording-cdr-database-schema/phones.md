---
title: Phones 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: "\"电话\" 表是支持表。 表中的每条记录存储了在具有数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。"
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815000"
---
# <a name="phones-table"></a><span data-ttu-id="5f720-104">Phones 表</span><span class="sxs-lookup"><span data-stu-id="5f720-104">Phones table</span></span>
 
<span data-ttu-id="5f720-105">"电话" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="5f720-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="5f720-106">表中的每条记录存储了在具有数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。</span><span class="sxs-lookup"><span data-stu-id="5f720-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="5f720-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5f720-107">**Column**</span></span>|<span data-ttu-id="5f720-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5f720-108">**Data Type**</span></span>|<span data-ttu-id="5f720-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5f720-109">**Key/Index**</span></span>|<span data-ttu-id="5f720-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5f720-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f720-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="5f720-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="5f720-112">int</span><span class="sxs-lookup"><span data-stu-id="5f720-112">int</span></span>  <br/> |<span data-ttu-id="5f720-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5f720-113">Primary</span></span>  <br/> |<span data-ttu-id="5f720-114">标识此电话的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="5f720-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="5f720-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="5f720-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="5f720-116">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="5f720-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="5f720-117">电话号码。</span><span class="sxs-lookup"><span data-stu-id="5f720-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="5f720-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5f720-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5f720-119">从中</span><span class="sxs-lookup"><span data-stu-id="5f720-119">dateTime</span></span>  <br/> ||<span data-ttu-id="5f720-120">时间戳（仅供内部使用）。</span><span class="sxs-lookup"><span data-stu-id="5f720-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="5f720-121">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5f720-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

