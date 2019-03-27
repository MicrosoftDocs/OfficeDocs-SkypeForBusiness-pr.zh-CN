---
title: tblPreference
ms.reviewer: ''
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
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879789"
---
# <a name="tblpreference"></a><span data-ttu-id="12403-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="12403-104">tblPreference</span></span>

<span data-ttu-id="12403-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="12403-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="12403-106">这通常使用 Lync 2013 之前的客户端。</span><span class="sxs-lookup"><span data-stu-id="12403-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="12403-107">**列**</span><span class="sxs-lookup"><span data-stu-id="12403-107">**Columns**</span></span>


| <span data-ttu-id="12403-108">**列**</span><span class="sxs-lookup"><span data-stu-id="12403-108">**Column**</span></span>            | <span data-ttu-id="12403-109">**类型**</span><span class="sxs-lookup"><span data-stu-id="12403-109">**Type**</span></span>                        | <span data-ttu-id="12403-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="12403-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="12403-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="12403-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="12403-112">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="12403-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="12403-113">如标签格式：\<用户 sip uri\></span><span class="sxs-lookup"><span data-stu-id="12403-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="12403-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="12403-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="12403-115">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="12403-115">int, not null</span></span>  <br/>            | <span data-ttu-id="12403-116">序列号 （每标签） 用于版本控制。</span><span class="sxs-lookup"><span data-stu-id="12403-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="12403-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="12403-117">prefContent</span></span>  <br/>    | <span data-ttu-id="12403-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="12403-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="12403-119">编码的内容。</span><span class="sxs-lookup"><span data-stu-id="12403-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="12403-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="12403-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="12403-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="12403-121">int, not null</span></span>  <br/>            | <span data-ttu-id="12403-122">更新首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="12403-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="12403-123">**关键字**</span><span class="sxs-lookup"><span data-stu-id="12403-123">**Key**</span></span>

|<span data-ttu-id="12403-124">**列**</span><span class="sxs-lookup"><span data-stu-id="12403-124">**Column**</span></span>|<span data-ttu-id="12403-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="12403-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12403-126">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="12403-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="12403-127">主键。</span><span class="sxs-lookup"><span data-stu-id="12403-127">Primary key.</span></span>  <br/> |


