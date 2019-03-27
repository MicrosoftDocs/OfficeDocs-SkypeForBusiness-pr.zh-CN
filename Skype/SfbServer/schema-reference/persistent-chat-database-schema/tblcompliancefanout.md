---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874047"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="f6f61-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="f6f61-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="f6f61-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="f6f61-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="f6f61-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f6f61-105">**Columns**</span></span>

|<span data-ttu-id="f6f61-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f6f61-106">**Column**</span></span>|<span data-ttu-id="f6f61-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="f6f61-107">**Type**</span></span>|<span data-ttu-id="f6f61-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6f61-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6f61-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="f6f61-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="f6f61-110">int</span><span class="sxs-lookup"><span data-stu-id="f6f61-110">int</span></span>  <br/> |<span data-ttu-id="f6f61-111">事件 id。</span><span class="sxs-lookup"><span data-stu-id="f6f61-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="f6f61-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="f6f61-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="f6f61-113">int</span><span class="sxs-lookup"><span data-stu-id="f6f61-113">int</span></span>  <br/> |<span data-ttu-id="f6f61-114">服务器标识 （与 tblServerIdentity.serverID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="f6f61-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="f6f61-115">**关键字**</span><span class="sxs-lookup"><span data-stu-id="f6f61-115">**Key**</span></span>

|<span data-ttu-id="f6f61-116">**列**</span><span class="sxs-lookup"><span data-stu-id="f6f61-116">**Column**</span></span>|<span data-ttu-id="f6f61-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6f61-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6f61-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="f6f61-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="f6f61-119">包含在 tblComplianceData.cmplEventID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="f6f61-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

