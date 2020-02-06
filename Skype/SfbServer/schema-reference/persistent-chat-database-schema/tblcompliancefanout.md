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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含处理合规性事件的所有服务器。
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814650"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="afa0b-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="afa0b-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="afa0b-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="afa0b-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="afa0b-105">**多**</span><span class="sxs-lookup"><span data-stu-id="afa0b-105">**Columns**</span></span>

|<span data-ttu-id="afa0b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="afa0b-106">**Column**</span></span>|<span data-ttu-id="afa0b-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="afa0b-107">**Type**</span></span>|<span data-ttu-id="afa0b-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="afa0b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afa0b-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="afa0b-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="afa0b-110">int</span><span class="sxs-lookup"><span data-stu-id="afa0b-110">int</span></span>  <br/> |<span data-ttu-id="afa0b-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="afa0b-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="afa0b-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="afa0b-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="afa0b-113">int</span><span class="sxs-lookup"><span data-stu-id="afa0b-113">int</span></span>  <br/> |<span data-ttu-id="afa0b-114">服务器标识（对应于 tblServerIdentity 表）。</span><span class="sxs-lookup"><span data-stu-id="afa0b-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="afa0b-115">**Key**</span><span class="sxs-lookup"><span data-stu-id="afa0b-115">**Key**</span></span>

|<span data-ttu-id="afa0b-116">**列**</span><span class="sxs-lookup"><span data-stu-id="afa0b-116">**Column**</span></span>|<span data-ttu-id="afa0b-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="afa0b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="afa0b-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="afa0b-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="afa0b-119">TblComplianceData 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="afa0b-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

