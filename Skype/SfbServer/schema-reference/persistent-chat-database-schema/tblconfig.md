---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930020"
---
# <a name="tblconfig"></a><span data-ttu-id="cca15-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="cca15-103">tblConfig</span></span>
 
<span data-ttu-id="cca15-104">tblConfig 包含不支持某些持久聊天服务器的配置，在一行中。</span><span class="sxs-lookup"><span data-stu-id="cca15-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="cca15-105">**列**</span><span class="sxs-lookup"><span data-stu-id="cca15-105">**Columns**</span></span>

|<span data-ttu-id="cca15-106">**列**</span><span class="sxs-lookup"><span data-stu-id="cca15-106">**Column**</span></span>|<span data-ttu-id="cca15-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="cca15-107">**Type**</span></span>|<span data-ttu-id="cca15-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="cca15-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cca15-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="cca15-109">configLabel</span></span>  <br/> |<span data-ttu-id="cca15-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="cca15-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="cca15-111">包含"池。</span><span class="sxs-lookup"><span data-stu-id="cca15-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="cca15-112">configContent</span><span class="sxs-lookup"><span data-stu-id="cca15-112">configContent</span></span>  <br/> |<span data-ttu-id="cca15-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="cca15-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="cca15-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="cca15-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="cca15-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="cca15-115">configPoolID</span></span>  <br/> |<span data-ttu-id="cca15-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="cca15-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="cca15-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="cca15-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="cca15-118">**关键字**</span><span class="sxs-lookup"><span data-stu-id="cca15-118">**Key**</span></span>

|<span data-ttu-id="cca15-119">**列**</span><span class="sxs-lookup"><span data-stu-id="cca15-119">**Column**</span></span>|<span data-ttu-id="cca15-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="cca15-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cca15-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="cca15-121">configLabel</span></span>  <br/> |<span data-ttu-id="cca15-122">主键。</span><span class="sxs-lookup"><span data-stu-id="cca15-122">Primary key.</span></span>  <br/> |
   

