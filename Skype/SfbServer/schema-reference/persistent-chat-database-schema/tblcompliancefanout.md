---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809792"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="1d605-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="1d605-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="1d605-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="1d605-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="1d605-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="1d605-105">**Columns**</span></span>

|<span data-ttu-id="1d605-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1d605-106">**Column**</span></span>|<span data-ttu-id="1d605-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="1d605-107">**Type**</span></span>|<span data-ttu-id="1d605-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d605-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d605-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1d605-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1d605-110">int</span><span class="sxs-lookup"><span data-stu-id="1d605-110">int</span></span>  <br/> |<span data-ttu-id="1d605-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="1d605-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="1d605-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="1d605-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="1d605-113">int</span><span class="sxs-lookup"><span data-stu-id="1d605-113">int</span></span>  <br/> |<span data-ttu-id="1d605-114">服务器标识（与 tblServerIdentity.serverID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="1d605-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="1d605-115">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="1d605-115">**Key**</span></span>

|<span data-ttu-id="1d605-116">**列**</span><span class="sxs-lookup"><span data-stu-id="1d605-116">**Column**</span></span>|<span data-ttu-id="1d605-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d605-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d605-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1d605-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1d605-119">其查找包含在 tblComplianceData.cmplEventID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="1d605-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

