---
title: MediationServers 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 表是一个支持表。 每个记录存储数据库中包含记录的呼叫中所涉及的一台中介服务器的信息。
ms.openlocfilehash: 77173fbb81bc2046a1906c61456f607ec7f2b5b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877068"
---
# <a name="mediationservers-table"></a><span data-ttu-id="22999-104">MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="22999-104">MediationServers table</span></span>
 
<span data-ttu-id="22999-105">MediationServers 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="22999-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="22999-106">每个记录存储数据库中包含记录的呼叫中所涉及的一台中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="22999-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="22999-107">**列**</span><span class="sxs-lookup"><span data-stu-id="22999-107">**Column**</span></span>|<span data-ttu-id="22999-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="22999-108">**Data Type**</span></span>|<span data-ttu-id="22999-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="22999-109">**Key/Index**</span></span>|<span data-ttu-id="22999-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="22999-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22999-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="22999-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="22999-112">int</span><span class="sxs-lookup"><span data-stu-id="22999-112">int</span></span>  <br/> |<span data-ttu-id="22999-113">Primary</span><span class="sxs-lookup"><span data-stu-id="22999-113">Primary</span></span>  <br/> |<span data-ttu-id="22999-114">标识此中介服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="22999-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="22999-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="22999-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="22999-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="22999-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="22999-117">中介服务器名称。</span><span class="sxs-lookup"><span data-stu-id="22999-117">Mediation Server name.</span></span>  <br/> |
   

