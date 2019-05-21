---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295340"
---
# <a name="tblpreference"></a><span data-ttu-id="c8acd-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="c8acd-104">tblPreference</span></span>

<span data-ttu-id="c8acd-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="c8acd-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="c8acd-106">这通常由 Lync 2013 之前的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="c8acd-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="c8acd-107">**多**</span><span class="sxs-lookup"><span data-stu-id="c8acd-107">**Columns**</span></span>


| <span data-ttu-id="c8acd-108">**列**</span><span class="sxs-lookup"><span data-stu-id="c8acd-108">**Column**</span></span>            | <span data-ttu-id="c8acd-109">**类型**</span><span class="sxs-lookup"><span data-stu-id="c8acd-109">**Type**</span></span>                        | <span data-ttu-id="c8acd-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8acd-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="c8acd-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="c8acd-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="c8acd-112">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="c8acd-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="c8acd-113">标签, 格式如下: \<用户 sip uri\></span><span class="sxs-lookup"><span data-stu-id="c8acd-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="c8acd-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="c8acd-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="c8acd-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="c8acd-115">int, not null</span></span>  <br/>            | <span data-ttu-id="c8acd-116">用于进行版本控制的序列号 (每个标签)。</span><span class="sxs-lookup"><span data-stu-id="c8acd-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="c8acd-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="c8acd-117">prefContent</span></span>  <br/>    | <span data-ttu-id="c8acd-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c8acd-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="c8acd-119">编码内容。</span><span class="sxs-lookup"><span data-stu-id="c8acd-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="c8acd-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="c8acd-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="c8acd-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="c8acd-121">int, not null</span></span>  <br/>            | <span data-ttu-id="c8acd-122">已更新首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="c8acd-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="c8acd-123">**关键字**</span><span class="sxs-lookup"><span data-stu-id="c8acd-123">**Key**</span></span>

|<span data-ttu-id="c8acd-124">**列**</span><span class="sxs-lookup"><span data-stu-id="c8acd-124">**Column**</span></span>|<span data-ttu-id="c8acd-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8acd-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c8acd-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="c8acd-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="c8acd-127">主键。</span><span class="sxs-lookup"><span data-stu-id="c8acd-127">Primary key.</span></span>  <br/> |


