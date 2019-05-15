---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929919"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="253a0-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="253a0-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="253a0-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="253a0-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="253a0-105">**列**</span><span class="sxs-lookup"><span data-stu-id="253a0-105">**Columns**</span></span>

|<span data-ttu-id="253a0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="253a0-106">**Column**</span></span>|<span data-ttu-id="253a0-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="253a0-107">**Type**</span></span>|<span data-ttu-id="253a0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="253a0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="253a0-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="253a0-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="253a0-110">int</span><span class="sxs-lookup"><span data-stu-id="253a0-110">int</span></span>  <br/> |<span data-ttu-id="253a0-111">事件 id。</span><span class="sxs-lookup"><span data-stu-id="253a0-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="253a0-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="253a0-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="253a0-113">int</span><span class="sxs-lookup"><span data-stu-id="253a0-113">int</span></span>  <br/> |<span data-ttu-id="253a0-114">服务器标识 （与 tblServerIdentity.serverID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="253a0-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="253a0-115">**关键字**</span><span class="sxs-lookup"><span data-stu-id="253a0-115">**Key**</span></span>

|<span data-ttu-id="253a0-116">**列**</span><span class="sxs-lookup"><span data-stu-id="253a0-116">**Column**</span></span>|<span data-ttu-id="253a0-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="253a0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="253a0-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="253a0-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="253a0-119">包含在 tblComplianceData.cmplEventID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="253a0-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

