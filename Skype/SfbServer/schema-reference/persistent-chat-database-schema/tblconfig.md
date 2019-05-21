---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天服务器不支持的配置, 其中一行。
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295452"
---
# <a name="tblconfig"></a><span data-ttu-id="ed2d7-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="ed2d7-103">tblConfig</span></span>
 
<span data-ttu-id="ed2d7-104">tblConfig 包含一些持久聊天服务器不支持的配置, 其中一行。</span><span class="sxs-lookup"><span data-stu-id="ed2d7-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="ed2d7-105">**多**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-105">**Columns**</span></span>

|<span data-ttu-id="ed2d7-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-106">**Column**</span></span>|<span data-ttu-id="ed2d7-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-107">**Type**</span></span>|<span data-ttu-id="ed2d7-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed2d7-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="ed2d7-109">configLabel</span></span>  <br/> |<span data-ttu-id="ed2d7-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="ed2d7-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ed2d7-111">包含 "pool"。</span><span class="sxs-lookup"><span data-stu-id="ed2d7-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="ed2d7-112">configContent</span><span class="sxs-lookup"><span data-stu-id="ed2d7-112">configContent</span></span>  <br/> |<span data-ttu-id="ed2d7-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ed2d7-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ed2d7-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="ed2d7-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="ed2d7-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="ed2d7-115">configPoolID</span></span>  <br/> |<span data-ttu-id="ed2d7-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="ed2d7-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="ed2d7-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ed2d7-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="ed2d7-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-118">**Key**</span></span>

|<span data-ttu-id="ed2d7-119">**列**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-119">**Column**</span></span>|<span data-ttu-id="ed2d7-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed2d7-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed2d7-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="ed2d7-121">configLabel</span></span>  <br/> |<span data-ttu-id="ed2d7-122">主键。</span><span class="sxs-lookup"><span data-stu-id="ed2d7-122">Primary key.</span></span>  <br/> |
   

