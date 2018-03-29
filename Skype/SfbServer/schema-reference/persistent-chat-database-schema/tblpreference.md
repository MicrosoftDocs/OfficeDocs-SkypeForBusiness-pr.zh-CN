---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="67491-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="67491-104">tblPreference</span></span>
 
<span data-ttu-id="67491-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="67491-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="67491-106">这通常使用 Lync 2013 之前的客户端。</span><span class="sxs-lookup"><span data-stu-id="67491-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="67491-107">**列**</span><span class="sxs-lookup"><span data-stu-id="67491-107">**Columns**</span></span>

|<span data-ttu-id="67491-108">**列**</span><span class="sxs-lookup"><span data-stu-id="67491-108">**Column**</span></span>|<span data-ttu-id="67491-109">**类型**</span><span class="sxs-lookup"><span data-stu-id="67491-109">**Type**</span></span>|<span data-ttu-id="67491-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="67491-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67491-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="67491-111">prefLabel</span></span>  <br/> |<span data-ttu-id="67491-112">nvarchar (255) 不为空</span><span class="sxs-lookup"><span data-stu-id="67491-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="67491-113">如标签的格式：\<用户的 sip uri\></span><span class="sxs-lookup"><span data-stu-id="67491-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="67491-114">用户名。\<的首选项组\>。</span><span class="sxs-lookup"><span data-stu-id="67491-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="67491-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="67491-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="67491-116">int，不为空</span><span class="sxs-lookup"><span data-stu-id="67491-116">int, not null</span></span>  <br/> |<span data-ttu-id="67491-117">顺序编号 （每个标签） 用于版本控制的目的。</span><span class="sxs-lookup"><span data-stu-id="67491-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="67491-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="67491-118">prefContent</span></span>  <br/> |<span data-ttu-id="67491-119">nvarchar （最大）</span><span class="sxs-lookup"><span data-stu-id="67491-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="67491-120">已编码的内容。</span><span class="sxs-lookup"><span data-stu-id="67491-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="67491-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="67491-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="67491-122">int，不为空</span><span class="sxs-lookup"><span data-stu-id="67491-122">int, not null</span></span>  <br/> |<span data-ttu-id="67491-123">更新首选项的主要用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="67491-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="67491-124">**密钥**</span><span class="sxs-lookup"><span data-stu-id="67491-124">**Key**</span></span>

|<span data-ttu-id="67491-125">**列**</span><span class="sxs-lookup"><span data-stu-id="67491-125">**Column**</span></span>|<span data-ttu-id="67491-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="67491-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67491-127">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="67491-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="67491-128">为主键。</span><span class="sxs-lookup"><span data-stu-id="67491-128">Primary key.</span></span>  <br/> |
   

