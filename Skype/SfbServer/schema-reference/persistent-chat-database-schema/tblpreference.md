---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常使用 Lync 2013 之前的客户端。
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929915"
---
# <a name="tblpreference"></a><span data-ttu-id="0f1ac-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="0f1ac-104">tblPreference</span></span>

<span data-ttu-id="0f1ac-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="0f1ac-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="0f1ac-106">这通常使用 Lync 2013 之前的客户端。</span><span class="sxs-lookup"><span data-stu-id="0f1ac-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="0f1ac-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-107">**Columns**</span></span>


| <span data-ttu-id="0f1ac-108">**列**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-108">**Column**</span></span>            | <span data-ttu-id="0f1ac-109">**类型**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-109">**Type**</span></span>                        | <span data-ttu-id="0f1ac-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="0f1ac-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="0f1ac-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="0f1ac-112">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="0f1ac-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="0f1ac-113">如标签格式：\<用户 sip uri\></span><span class="sxs-lookup"><span data-stu-id="0f1ac-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="0f1ac-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="0f1ac-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="0f1ac-115">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="0f1ac-115">int, not null</span></span>  <br/>            | <span data-ttu-id="0f1ac-116">序列号 （每标签） 用于版本控制。</span><span class="sxs-lookup"><span data-stu-id="0f1ac-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="0f1ac-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="0f1ac-117">prefContent</span></span>  <br/>    | <span data-ttu-id="0f1ac-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="0f1ac-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="0f1ac-119">编码的内容。</span><span class="sxs-lookup"><span data-stu-id="0f1ac-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="0f1ac-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="0f1ac-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="0f1ac-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="0f1ac-121">int, not null</span></span>  <br/>            | <span data-ttu-id="0f1ac-122">更新首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="0f1ac-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="0f1ac-123">**关键字**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-123">**Key**</span></span>

|<span data-ttu-id="0f1ac-124">**列**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-124">**Column**</span></span>|<span data-ttu-id="0f1ac-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f1ac-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f1ac-126">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="0f1ac-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="0f1ac-127">主键。</span><span class="sxs-lookup"><span data-stu-id="0f1ac-127">Primary key.</span></span>  <br/> |


