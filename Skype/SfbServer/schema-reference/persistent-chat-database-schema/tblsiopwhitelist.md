---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831482"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="d6a5d-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="d6a5d-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="d6a5d-104">tblSiopWhiteList 是可与节点关联的注册外接程序的列表。</span><span class="sxs-lookup"><span data-stu-id="d6a5d-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="d6a5d-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-105">**Columns**</span></span>

|<span data-ttu-id="d6a5d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-106">**Column**</span></span>|<span data-ttu-id="d6a5d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-107">**Type**</span></span>|<span data-ttu-id="d6a5d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6a5d-109">siopID</span><span class="sxs-lookup"><span data-stu-id="d6a5d-109">siopID</span></span>  <br/> |<span data-ttu-id="d6a5d-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="d6a5d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d6a5d-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d6a5d-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d6a5d-112">siopName</span><span class="sxs-lookup"><span data-stu-id="d6a5d-112">siopName</span></span>  <br/> |<span data-ttu-id="d6a5d-113">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="d6a5d-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="d6a5d-114">外接程序的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d6a5d-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d6a5d-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="d6a5d-115">siopUrl</span></span>  <br/> |<span data-ttu-id="d6a5d-116">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="d6a5d-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d6a5d-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a5d-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="d6a5d-118">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-118">**Key**</span></span>

|<span data-ttu-id="d6a5d-119">**列**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-119">**Column**</span></span>|<span data-ttu-id="d6a5d-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6a5d-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6a5d-121">siopID</span><span class="sxs-lookup"><span data-stu-id="d6a5d-121">siopID</span></span>  <br/> |<span data-ttu-id="d6a5d-122">主键。</span><span class="sxs-lookup"><span data-stu-id="d6a5d-122">Primary key.</span></span>  <br/> |
   

