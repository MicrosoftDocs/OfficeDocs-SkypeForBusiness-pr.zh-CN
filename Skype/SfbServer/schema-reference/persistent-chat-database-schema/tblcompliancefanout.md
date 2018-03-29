---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理法规遵从性事件中的所有服务器。
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="dde63-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="dde63-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="dde63-104">tblComplianceFanout 包含处理法规遵从性事件中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="dde63-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="dde63-105">**列**</span><span class="sxs-lookup"><span data-stu-id="dde63-105">**Columns**</span></span>

|<span data-ttu-id="dde63-106">**列**</span><span class="sxs-lookup"><span data-stu-id="dde63-106">**Column**</span></span>|<span data-ttu-id="dde63-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="dde63-107">**Type**</span></span>|<span data-ttu-id="dde63-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="dde63-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dde63-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="dde63-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="dde63-110">int</span><span class="sxs-lookup"><span data-stu-id="dde63-110">int</span></span>  <br/> |<span data-ttu-id="dde63-111">事件 id。</span><span class="sxs-lookup"><span data-stu-id="dde63-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="dde63-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="dde63-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="dde63-113">int</span><span class="sxs-lookup"><span data-stu-id="dde63-113">int</span></span>  <br/> |<span data-ttu-id="dde63-114">服务器标识 （对应于 tblServerIdentity.serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="dde63-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="dde63-115">**密钥**</span><span class="sxs-lookup"><span data-stu-id="dde63-115">**Key**</span></span>

|<span data-ttu-id="dde63-116">**列**</span><span class="sxs-lookup"><span data-stu-id="dde63-116">**Column**</span></span>|<span data-ttu-id="dde63-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="dde63-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dde63-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="dde63-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="dde63-119">TblComplianceData.cmplEventID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="dde63-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

