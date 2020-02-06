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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天服务器不支持的配置，其中一行。
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814620"
---
# <a name="tblconfig"></a><span data-ttu-id="5b24d-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="5b24d-103">tblConfig</span></span>
 
<span data-ttu-id="5b24d-104">tblConfig 包含一些持久聊天服务器不支持的配置，其中一行。</span><span class="sxs-lookup"><span data-stu-id="5b24d-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="5b24d-105">**多**</span><span class="sxs-lookup"><span data-stu-id="5b24d-105">**Columns**</span></span>

|<span data-ttu-id="5b24d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5b24d-106">**Column**</span></span>|<span data-ttu-id="5b24d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b24d-107">**Type**</span></span>|<span data-ttu-id="5b24d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b24d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b24d-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="5b24d-109">configLabel</span></span>  <br/> |<span data-ttu-id="5b24d-110">nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="5b24d-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5b24d-111">包含 "pool"。</span><span class="sxs-lookup"><span data-stu-id="5b24d-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="5b24d-112">configContent</span><span class="sxs-lookup"><span data-stu-id="5b24d-112">configContent</span></span>  <br/> |<span data-ttu-id="5b24d-113">nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="5b24d-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="5b24d-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="5b24d-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="5b24d-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="5b24d-115">configPoolID</span></span>  <br/> |<span data-ttu-id="5b24d-116">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="5b24d-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="5b24d-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="5b24d-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="5b24d-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="5b24d-118">**Key**</span></span>

|<span data-ttu-id="5b24d-119">**列**</span><span class="sxs-lookup"><span data-stu-id="5b24d-119">**Column**</span></span>|<span data-ttu-id="5b24d-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b24d-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b24d-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="5b24d-121">configLabel</span></span>  <br/> |<span data-ttu-id="5b24d-122">主键。</span><span class="sxs-lookup"><span data-stu-id="5b24d-122">Primary key.</span></span>  <br/> |
   

