---
title: MediationServers 表
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
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 表是一个支持表。 每条记录都存储有关在数据库中具有记录的呼叫中涉及的一台中介服务器的信息。
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814762"
---
# <a name="mediationservers-table"></a><span data-ttu-id="bf1c8-104">MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="bf1c8-104">MediationServers table</span></span>
 
<span data-ttu-id="bf1c8-105">MediationServers 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="bf1c8-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="bf1c8-106">每条记录都存储有关在数据库中具有记录的呼叫中涉及的一台中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="bf1c8-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="bf1c8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bf1c8-107">**Column**</span></span>|<span data-ttu-id="bf1c8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bf1c8-108">**Data Type**</span></span>|<span data-ttu-id="bf1c8-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="bf1c8-109">**Key/Index**</span></span>|<span data-ttu-id="bf1c8-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="bf1c8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf1c8-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="bf1c8-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="bf1c8-112">int</span><span class="sxs-lookup"><span data-stu-id="bf1c8-112">int</span></span>  <br/> |<span data-ttu-id="bf1c8-113">主</span><span class="sxs-lookup"><span data-stu-id="bf1c8-113">Primary</span></span>  <br/> |<span data-ttu-id="bf1c8-114">标识此中介服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="bf1c8-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="bf1c8-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="bf1c8-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="bf1c8-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="bf1c8-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="bf1c8-117">中介服务器名称。</span><span class="sxs-lookup"><span data-stu-id="bf1c8-117">Mediation Server name.</span></span>  <br/> |
   

