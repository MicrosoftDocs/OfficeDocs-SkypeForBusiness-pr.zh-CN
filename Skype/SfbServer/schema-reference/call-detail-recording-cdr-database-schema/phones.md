---
title: Phones 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 表是一个支持表。 表中的每条记录都存储有关在数据库中具有记录的 VoIP 呼叫中涉及的一个电话号码的信息。
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823262"
---
# <a name="phones-table"></a><span data-ttu-id="39593-104">Phones 表</span><span class="sxs-lookup"><span data-stu-id="39593-104">Phones table</span></span>
 
<span data-ttu-id="39593-105">Phones 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="39593-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="39593-106">表中的每条记录都存储有关在数据库中具有记录的 VoIP 呼叫中涉及的一个电话号码的信息。</span><span class="sxs-lookup"><span data-stu-id="39593-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="39593-107">**列**</span><span class="sxs-lookup"><span data-stu-id="39593-107">**Column**</span></span>|<span data-ttu-id="39593-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="39593-108">**Data Type**</span></span>|<span data-ttu-id="39593-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="39593-109">**Key/Index**</span></span>|<span data-ttu-id="39593-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="39593-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39593-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="39593-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="39593-112">int</span><span class="sxs-lookup"><span data-stu-id="39593-112">int</span></span>  <br/> |<span data-ttu-id="39593-113">主</span><span class="sxs-lookup"><span data-stu-id="39593-113">Primary</span></span>  <br/> |<span data-ttu-id="39593-114">标识此电话的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="39593-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="39593-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="39593-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="39593-116">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="39593-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="39593-117">电话号码。</span><span class="sxs-lookup"><span data-stu-id="39593-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="39593-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="39593-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="39593-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="39593-119">dateTime</span></span>  <br/> ||<span data-ttu-id="39593-120">时间戳 (供内部使用) 。</span><span class="sxs-lookup"><span data-stu-id="39593-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="39593-121">此字段在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="39593-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

