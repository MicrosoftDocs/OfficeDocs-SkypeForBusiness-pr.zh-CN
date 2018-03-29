---
title: tblConfig
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久的聊天服务器不支持的配置，在一行中。
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="c606e-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="c606e-103">tblConfig</span></span>
 
<span data-ttu-id="c606e-104">tblConfig 包含一些持久的聊天服务器不支持的配置，在一行中。</span><span class="sxs-lookup"><span data-stu-id="c606e-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="c606e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="c606e-105">**Columns**</span></span>

|<span data-ttu-id="c606e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c606e-106">**Column**</span></span>|<span data-ttu-id="c606e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="c606e-107">**Type**</span></span>|<span data-ttu-id="c606e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c606e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c606e-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="c606e-109">configLabel</span></span>  <br/> |<span data-ttu-id="c606e-110">nvarchar (255) 不为空</span><span class="sxs-lookup"><span data-stu-id="c606e-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="c606e-111">包含"池。</span><span class="sxs-lookup"><span data-stu-id="c606e-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="c606e-112">configContent</span><span class="sxs-lookup"><span data-stu-id="c606e-112">configContent</span></span>  <br/> |<span data-ttu-id="c606e-113">nvarchar （最大）</span><span class="sxs-lookup"><span data-stu-id="c606e-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="c606e-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="c606e-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="c606e-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="c606e-115">configPoolID</span></span>  <br/> |<span data-ttu-id="c606e-116">GUID，不为空</span><span class="sxs-lookup"><span data-stu-id="c606e-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="c606e-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c606e-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="c606e-118">**密钥**</span><span class="sxs-lookup"><span data-stu-id="c606e-118">**Key**</span></span>

|<span data-ttu-id="c606e-119">**列**</span><span class="sxs-lookup"><span data-stu-id="c606e-119">**Column**</span></span>|<span data-ttu-id="c606e-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="c606e-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c606e-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="c606e-121">configLabel</span></span>  <br/> |<span data-ttu-id="c606e-122">为主键。</span><span class="sxs-lookup"><span data-stu-id="c606e-122">Primary key.</span></span>  <br/> |
   

