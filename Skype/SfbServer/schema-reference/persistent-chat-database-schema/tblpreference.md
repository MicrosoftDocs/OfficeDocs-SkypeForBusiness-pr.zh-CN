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
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375941"
---
# <a name="tblpreference"></a><span data-ttu-id="2897b-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="2897b-104">tblPreference</span></span>

<span data-ttu-id="2897b-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="2897b-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="2897b-106">这通常使用 Lync 2013 之前的客户端。</span><span class="sxs-lookup"><span data-stu-id="2897b-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="2897b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2897b-107">**Columns**</span></span>


| <span data-ttu-id="2897b-108">**列**</span><span class="sxs-lookup"><span data-stu-id="2897b-108">**Column**</span></span>            | <span data-ttu-id="2897b-109">**类型**</span><span class="sxs-lookup"><span data-stu-id="2897b-109">**Type**</span></span>                        | <span data-ttu-id="2897b-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="2897b-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="2897b-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="2897b-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="2897b-112">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="2897b-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="2897b-113">如标签格式：\<用户 sip uri\></span><span class="sxs-lookup"><span data-stu-id="2897b-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="2897b-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="2897b-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="2897b-115">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="2897b-115">int, not null</span></span>  <br/>            | <span data-ttu-id="2897b-116">序列号 （每标签） 用于版本控制。</span><span class="sxs-lookup"><span data-stu-id="2897b-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="2897b-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="2897b-117">prefContent</span></span>  <br/>    | <span data-ttu-id="2897b-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2897b-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="2897b-119">编码的内容。</span><span class="sxs-lookup"><span data-stu-id="2897b-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="2897b-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2897b-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="2897b-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="2897b-121">int, not null</span></span>  <br/>            | <span data-ttu-id="2897b-122">更新首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="2897b-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="2897b-123">**关键字**</span><span class="sxs-lookup"><span data-stu-id="2897b-123">**Key**</span></span>

|<span data-ttu-id="2897b-124">**列**</span><span class="sxs-lookup"><span data-stu-id="2897b-124">**Column**</span></span>|<span data-ttu-id="2897b-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="2897b-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2897b-126">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="2897b-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="2897b-127">主键。</span><span class="sxs-lookup"><span data-stu-id="2897b-127">Primary key.</span></span>  <br/> |


