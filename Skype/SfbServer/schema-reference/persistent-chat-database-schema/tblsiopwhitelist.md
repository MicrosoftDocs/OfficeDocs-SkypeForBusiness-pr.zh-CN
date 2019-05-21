---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295172"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="d028f-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="d028f-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="d028f-104">tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。</span><span class="sxs-lookup"><span data-stu-id="d028f-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="d028f-105">**多**</span><span class="sxs-lookup"><span data-stu-id="d028f-105">**Columns**</span></span>

|<span data-ttu-id="d028f-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d028f-106">**Column**</span></span>|<span data-ttu-id="d028f-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d028f-107">**Type**</span></span>|<span data-ttu-id="d028f-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d028f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d028f-109">siopID</span><span class="sxs-lookup"><span data-stu-id="d028f-109">siopID</span></span>  <br/> |<span data-ttu-id="d028f-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="d028f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d028f-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d028f-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d028f-112">siopName</span><span class="sxs-lookup"><span data-stu-id="d028f-112">siopName</span></span>  <br/> |<span data-ttu-id="d028f-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="d028f-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="d028f-114">显示-外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d028f-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="d028f-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="d028f-115">siopUrl</span></span>  <br/> |<span data-ttu-id="d028f-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="d028f-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d028f-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="d028f-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="d028f-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="d028f-118">**Key**</span></span>

|<span data-ttu-id="d028f-119">**列**</span><span class="sxs-lookup"><span data-stu-id="d028f-119">**Column**</span></span>|<span data-ttu-id="d028f-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="d028f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d028f-121">siopID</span><span class="sxs-lookup"><span data-stu-id="d028f-121">siopID</span></span>  <br/> |<span data-ttu-id="d028f-122">主键。</span><span class="sxs-lookup"><span data-stu-id="d028f-122">Primary key.</span></span>  <br/> |
   

