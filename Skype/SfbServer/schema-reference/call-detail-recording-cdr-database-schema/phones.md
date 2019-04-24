---
title: Phones 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 表是一个支持表。 每个表中的记录存储有关数据库中包含记录的 VoIP 呼叫中所涉及的一个电话号码的信息。
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212885"
---
# <a name="phones-table"></a><span data-ttu-id="d9f1e-104">Phones 表</span><span class="sxs-lookup"><span data-stu-id="d9f1e-104">Phones table</span></span>
 
<span data-ttu-id="d9f1e-105">Phones 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="d9f1e-106">每个表中的记录存储有关数据库中包含记录的 VoIP 呼叫中所涉及的一个电话号码的信息。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="d9f1e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-107">**Column**</span></span>|<span data-ttu-id="d9f1e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-108">**Data Type**</span></span>|<span data-ttu-id="d9f1e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-109">**Key/Index**</span></span>|<span data-ttu-id="d9f1e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9f1e-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="d9f1e-112">int</span><span class="sxs-lookup"><span data-stu-id="d9f1e-112">int</span></span>  <br/> |<span data-ttu-id="d9f1e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d9f1e-113">Primary</span></span>  <br/> |<span data-ttu-id="d9f1e-114">标识此电话的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="d9f1e-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="d9f1e-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d9f1e-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="d9f1e-117">电话号码。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="d9f1e-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d9f1e-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d9f1e-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="d9f1e-119">dateTime</span></span>  <br/> ||<span data-ttu-id="d9f1e-120">时间戳 （仅供内部使用）。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="d9f1e-121">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d9f1e-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

