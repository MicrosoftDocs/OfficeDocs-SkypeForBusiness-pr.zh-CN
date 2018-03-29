---
title: 在业务服务器 2015年的 Skype 的网关表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 网关表是一个支持的表。 每个记录在数据库中具有记录的公用交换的电话网络 (PSTN) 调用存储有关所涉及的一个网关信息。
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d0b52-104">在业务服务器 2015年的 Skype 的网关表</span><span class="sxs-lookup"><span data-stu-id="d0b52-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d0b52-105">网关表是一个支持的表。</span><span class="sxs-lookup"><span data-stu-id="d0b52-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="d0b52-106">每个记录在数据库中具有记录的公用交换的电话网络 (PSTN) 调用存储有关所涉及的一个网关信息。</span><span class="sxs-lookup"><span data-stu-id="d0b52-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="d0b52-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d0b52-107">**Column**</span></span>|<span data-ttu-id="d0b52-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d0b52-108">**Data Type**</span></span>|<span data-ttu-id="d0b52-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d0b52-109">**Key/Index**</span></span>|<span data-ttu-id="d0b52-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d0b52-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0b52-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="d0b52-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="d0b52-112">int</span><span class="sxs-lookup"><span data-stu-id="d0b52-112">int</span></span>  <br/> |<span data-ttu-id="d0b52-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d0b52-113">Primary</span></span>  <br/> |<span data-ttu-id="d0b52-114">标识此网关的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d0b52-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="d0b52-115">**网关**</span><span class="sxs-lookup"><span data-stu-id="d0b52-115">**Gateway**</span></span> <br/> |<span data-ttu-id="d0b52-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d0b52-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d0b52-117">网关名称。</span><span class="sxs-lookup"><span data-stu-id="d0b52-117">Gateway name.</span></span>  <br/> |
   

