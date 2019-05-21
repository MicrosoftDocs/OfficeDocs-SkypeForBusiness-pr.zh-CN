---
title: MediationServers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个中介服务器的信息。
ms.openlocfilehash: a79c7c1d81f220e034e63263ef8dbf81a13d4024
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295991"
---
# <a name="mediationservers-table"></a><span data-ttu-id="d0749-104">MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="d0749-104">MediationServers table</span></span>
 
<span data-ttu-id="d0749-105">MediationServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="d0749-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="d0749-106">每个记录存储有关在数据库中具有记录的通话中涉及的一个中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="d0749-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="d0749-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d0749-107">**Column**</span></span>|<span data-ttu-id="d0749-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d0749-108">**Data Type**</span></span>|<span data-ttu-id="d0749-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d0749-109">**Key/Index**</span></span>|<span data-ttu-id="d0749-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d0749-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0749-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="d0749-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="d0749-112">int</span><span class="sxs-lookup"><span data-stu-id="d0749-112">int</span></span>  <br/> |<span data-ttu-id="d0749-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d0749-113">Primary</span></span>  <br/> |<span data-ttu-id="d0749-114">标识此中介服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d0749-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="d0749-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="d0749-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="d0749-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d0749-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d0749-117">中介服务器名称。</span><span class="sxs-lookup"><span data-stu-id="d0749-117">Mediation Server name.</span></span>  <br/> |
   

