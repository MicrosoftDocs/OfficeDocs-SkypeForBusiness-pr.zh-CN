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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213065"
---
# <a name="tblconfig"></a><span data-ttu-id="6c819-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="6c819-103">tblConfig</span></span>
 
<span data-ttu-id="6c819-104">tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。</span><span class="sxs-lookup"><span data-stu-id="6c819-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="6c819-105">**列**</span><span class="sxs-lookup"><span data-stu-id="6c819-105">**Columns**</span></span>

|<span data-ttu-id="6c819-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6c819-106">**Column**</span></span>|<span data-ttu-id="6c819-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="6c819-107">**Type**</span></span>|<span data-ttu-id="6c819-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c819-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c819-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="6c819-109">configLabel</span></span>  <br/> |<span data-ttu-id="6c819-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="6c819-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="6c819-111">包含"池。</span><span class="sxs-lookup"><span data-stu-id="6c819-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="6c819-112">configContent</span><span class="sxs-lookup"><span data-stu-id="6c819-112">configContent</span></span>  <br/> |<span data-ttu-id="6c819-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6c819-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="6c819-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="6c819-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="6c819-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="6c819-115">configPoolID</span></span>  <br/> |<span data-ttu-id="6c819-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="6c819-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="6c819-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="6c819-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="6c819-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="6c819-118">**Key**</span></span>

|<span data-ttu-id="6c819-119">**列**</span><span class="sxs-lookup"><span data-stu-id="6c819-119">**Column**</span></span>|<span data-ttu-id="6c819-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c819-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c819-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="6c819-121">configLabel</span></span>  <br/> |<span data-ttu-id="6c819-122">主键。</span><span class="sxs-lookup"><span data-stu-id="6c819-122">Primary key.</span></span>  <br/> |
   

