---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898935"
---
# <a name="tblconfig"></a><span data-ttu-id="393e3-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="393e3-103">tblConfig</span></span>
 
<span data-ttu-id="393e3-104">tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。</span><span class="sxs-lookup"><span data-stu-id="393e3-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="393e3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="393e3-105">**Columns**</span></span>

|<span data-ttu-id="393e3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="393e3-106">**Column**</span></span>|<span data-ttu-id="393e3-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="393e3-107">**Type**</span></span>|<span data-ttu-id="393e3-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="393e3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="393e3-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="393e3-109">configLabel</span></span>  <br/> |<span data-ttu-id="393e3-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="393e3-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="393e3-111">包含"池。</span><span class="sxs-lookup"><span data-stu-id="393e3-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="393e3-112">configContent</span><span class="sxs-lookup"><span data-stu-id="393e3-112">configContent</span></span>  <br/> |<span data-ttu-id="393e3-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="393e3-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="393e3-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="393e3-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="393e3-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="393e3-115">configPoolID</span></span>  <br/> |<span data-ttu-id="393e3-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="393e3-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="393e3-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="393e3-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="393e3-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="393e3-118">**Key**</span></span>

|<span data-ttu-id="393e3-119">**列**</span><span class="sxs-lookup"><span data-stu-id="393e3-119">**Column**</span></span>|<span data-ttu-id="393e3-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="393e3-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="393e3-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="393e3-121">configLabel</span></span>  <br/> |<span data-ttu-id="393e3-122">主键。</span><span class="sxs-lookup"><span data-stu-id="393e3-122">Primary key.</span></span>  <br/> |
   

