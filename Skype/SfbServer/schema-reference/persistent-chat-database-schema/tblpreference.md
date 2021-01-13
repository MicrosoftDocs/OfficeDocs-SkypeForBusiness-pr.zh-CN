---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含用户的客户端首选项。 这通常由 Lync 2013 之前的客户端使用。
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815902"
---
# <a name="tblpreference"></a><span data-ttu-id="3370f-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="3370f-104">tblPreference</span></span>

<span data-ttu-id="3370f-105">tblPreference 包含用户的客户端首选项。</span><span class="sxs-lookup"><span data-stu-id="3370f-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="3370f-106">这通常由 Lync 2013 之前的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="3370f-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="3370f-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="3370f-107">**Columns**</span></span>


| <span data-ttu-id="3370f-108">**列**</span><span class="sxs-lookup"><span data-stu-id="3370f-108">**Column**</span></span>            | <span data-ttu-id="3370f-109">**类型**</span><span class="sxs-lookup"><span data-stu-id="3370f-109">**Type**</span></span>                        | <span data-ttu-id="3370f-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="3370f-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="3370f-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="3370f-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="3370f-112">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="3370f-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="3370f-113">带如下格式的标签： \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="3370f-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="3370f-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="3370f-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="3370f-115">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="3370f-115">int, not null</span></span>  <br/>            | <span data-ttu-id="3370f-116">出于版本 (，每个标签) 顺序编号。</span><span class="sxs-lookup"><span data-stu-id="3370f-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="3370f-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="3370f-117">prefContent</span></span>  <br/>    | <span data-ttu-id="3370f-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3370f-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="3370f-119">编码的内容。</span><span class="sxs-lookup"><span data-stu-id="3370f-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="3370f-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="3370f-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="3370f-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="3370f-121">int, not null</span></span>  <br/>            | <span data-ttu-id="3370f-122">更新首选项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="3370f-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="3370f-123">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="3370f-123">**Key**</span></span>

|<span data-ttu-id="3370f-124">**列**</span><span class="sxs-lookup"><span data-stu-id="3370f-124">**Column**</span></span>|<span data-ttu-id="3370f-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="3370f-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="3370f-126">主键。</span><span class="sxs-lookup"><span data-stu-id="3370f-126">Primary key.</span></span>  <br/> |


