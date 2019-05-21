---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295501"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="0f4bc-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="0f4bc-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="0f4bc-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="0f4bc-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="0f4bc-105">**多**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-105">**Columns**</span></span>

|<span data-ttu-id="0f4bc-106">**列**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-106">**Column**</span></span>|<span data-ttu-id="0f4bc-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-107">**Type**</span></span>|<span data-ttu-id="0f4bc-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f4bc-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="0f4bc-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="0f4bc-110">int</span><span class="sxs-lookup"><span data-stu-id="0f4bc-110">int</span></span>  <br/> |<span data-ttu-id="0f4bc-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="0f4bc-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="0f4bc-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="0f4bc-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="0f4bc-113">int</span><span class="sxs-lookup"><span data-stu-id="0f4bc-113">int</span></span>  <br/> |<span data-ttu-id="0f4bc-114">服务器标识 (对应于 tblServerIdentity 表)。</span><span class="sxs-lookup"><span data-stu-id="0f4bc-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="0f4bc-115">**关键字**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-115">**Key**</span></span>

|<span data-ttu-id="0f4bc-116">**列**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-116">**Column**</span></span>|<span data-ttu-id="0f4bc-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f4bc-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f4bc-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="0f4bc-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="0f4bc-119">TblComplianceData 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="0f4bc-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

