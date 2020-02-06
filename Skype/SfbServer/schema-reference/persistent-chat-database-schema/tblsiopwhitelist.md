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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812110"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="3a513-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="3a513-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="3a513-104">tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。</span><span class="sxs-lookup"><span data-stu-id="3a513-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="3a513-105">**多**</span><span class="sxs-lookup"><span data-stu-id="3a513-105">**Columns**</span></span>

|<span data-ttu-id="3a513-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3a513-106">**Column**</span></span>|<span data-ttu-id="3a513-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="3a513-107">**Type**</span></span>|<span data-ttu-id="3a513-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a513-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a513-109">siopID</span><span class="sxs-lookup"><span data-stu-id="3a513-109">siopID</span></span>  <br/> |<span data-ttu-id="3a513-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="3a513-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3a513-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3a513-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="3a513-112">siopName</span><span class="sxs-lookup"><span data-stu-id="3a513-112">siopName</span></span>  <br/> |<span data-ttu-id="3a513-113">nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="3a513-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="3a513-114">显示-外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="3a513-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="3a513-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="3a513-115">siopUrl</span></span>  <br/> |<span data-ttu-id="3a513-116">nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="3a513-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3a513-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="3a513-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="3a513-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="3a513-118">**Key**</span></span>

|<span data-ttu-id="3a513-119">**列**</span><span class="sxs-lookup"><span data-stu-id="3a513-119">**Column**</span></span>|<span data-ttu-id="3a513-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a513-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a513-121">siopID</span><span class="sxs-lookup"><span data-stu-id="3a513-121">siopID</span></span>  <br/> |<span data-ttu-id="3a513-122">主键。</span><span class="sxs-lookup"><span data-stu-id="3a513-122">Primary key.</span></span>  <br/> |
   

