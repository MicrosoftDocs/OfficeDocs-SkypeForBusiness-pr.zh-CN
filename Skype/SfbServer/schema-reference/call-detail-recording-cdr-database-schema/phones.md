---
title: Phones 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 电话表是支持表。 表中的每条记录存储信息涉及数据库中具有记录的 VoIP 电话一个电话号码。
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a><span data-ttu-id="75b3c-104">Phones 表</span><span class="sxs-lookup"><span data-stu-id="75b3c-104">Phones table</span></span>
 
<span data-ttu-id="75b3c-105">电话表是支持表。</span><span class="sxs-lookup"><span data-stu-id="75b3c-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="75b3c-106">表中的每条记录存储信息涉及数据库中具有记录的 VoIP 电话一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="75b3c-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="75b3c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="75b3c-107">**Column**</span></span>|<span data-ttu-id="75b3c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="75b3c-108">**Data Type**</span></span>|<span data-ttu-id="75b3c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="75b3c-109">**Key/Index**</span></span>|<span data-ttu-id="75b3c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="75b3c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75b3c-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="75b3c-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="75b3c-112">int</span><span class="sxs-lookup"><span data-stu-id="75b3c-112">int</span></span>  <br/> |<span data-ttu-id="75b3c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="75b3c-113">Primary</span></span>  <br/> |<span data-ttu-id="75b3c-114">标识此电话的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="75b3c-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="75b3c-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="75b3c-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="75b3c-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="75b3c-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="75b3c-117">电话号码。</span><span class="sxs-lookup"><span data-stu-id="75b3c-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="75b3c-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="75b3c-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="75b3c-119">日期时间</span><span class="sxs-lookup"><span data-stu-id="75b3c-119">dateTime</span></span>  <br/> ||<span data-ttu-id="75b3c-120">时间戳 （仅供内部使用）。</span><span class="sxs-lookup"><span data-stu-id="75b3c-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="75b3c-121">在 Microsoft Lync Server 2013 引入了此字段。</span><span class="sxs-lookup"><span data-stu-id="75b3c-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

