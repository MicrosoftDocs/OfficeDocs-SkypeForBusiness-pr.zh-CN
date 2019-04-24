---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是已注册的加载可与节点关联的列表。
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212381"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="90933-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="90933-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="90933-104">tblSiopWhiteList 是已注册的加载可与节点关联的列表。</span><span class="sxs-lookup"><span data-stu-id="90933-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="90933-105">**列**</span><span class="sxs-lookup"><span data-stu-id="90933-105">**Columns**</span></span>

|<span data-ttu-id="90933-106">**列**</span><span class="sxs-lookup"><span data-stu-id="90933-106">**Column**</span></span>|<span data-ttu-id="90933-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="90933-107">**Type**</span></span>|<span data-ttu-id="90933-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="90933-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90933-109">siopID</span><span class="sxs-lookup"><span data-stu-id="90933-109">siopID</span></span>  <br/> |<span data-ttu-id="90933-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="90933-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="90933-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="90933-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="90933-112">siopName</span><span class="sxs-lookup"><span data-stu-id="90933-112">siopName</span></span>  <br/> |<span data-ttu-id="90933-113">nvarchar (50)，不为 null</span><span class="sxs-lookup"><span data-stu-id="90933-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="90933-114">外接程序的显示名称。</span><span class="sxs-lookup"><span data-stu-id="90933-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="90933-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="90933-115">siopUrl</span></span>  <br/> |<span data-ttu-id="90933-116">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="90933-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="90933-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="90933-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="90933-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="90933-118">**Key**</span></span>

|<span data-ttu-id="90933-119">**列**</span><span class="sxs-lookup"><span data-stu-id="90933-119">**Column**</span></span>|<span data-ttu-id="90933-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="90933-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90933-121">siopID</span><span class="sxs-lookup"><span data-stu-id="90933-121">siopID</span></span>  <br/> |<span data-ttu-id="90933-122">主键。</span><span class="sxs-lookup"><span data-stu-id="90933-122">Primary key.</span></span>  <br/> |
   

