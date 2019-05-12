---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是已注册的加载可与节点关联的列表。
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924771"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="f32cb-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="f32cb-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="f32cb-104">tblSiopWhiteList 是已注册的加载可与节点关联的列表。</span><span class="sxs-lookup"><span data-stu-id="f32cb-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="f32cb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f32cb-105">**Columns**</span></span>

|<span data-ttu-id="f32cb-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f32cb-106">**Column**</span></span>|<span data-ttu-id="f32cb-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="f32cb-107">**Type**</span></span>|<span data-ttu-id="f32cb-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="f32cb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f32cb-109">siopID</span><span class="sxs-lookup"><span data-stu-id="f32cb-109">siopID</span></span>  <br/> |<span data-ttu-id="f32cb-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="f32cb-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f32cb-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f32cb-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="f32cb-112">siopName</span><span class="sxs-lookup"><span data-stu-id="f32cb-112">siopName</span></span>  <br/> |<span data-ttu-id="f32cb-113">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="f32cb-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="f32cb-114">外接程序的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f32cb-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="f32cb-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="f32cb-115">siopUrl</span></span>  <br/> |<span data-ttu-id="f32cb-116">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="f32cb-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f32cb-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="f32cb-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="f32cb-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="f32cb-118">**Key**</span></span>

|<span data-ttu-id="f32cb-119">**列**</span><span class="sxs-lookup"><span data-stu-id="f32cb-119">**Column**</span></span>|<span data-ttu-id="f32cb-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="f32cb-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f32cb-121">siopID</span><span class="sxs-lookup"><span data-stu-id="f32cb-121">siopID</span></span>  <br/> |<span data-ttu-id="f32cb-122">主键。</span><span class="sxs-lookup"><span data-stu-id="f32cb-122">Primary key.</span></span>  <br/> |
   

