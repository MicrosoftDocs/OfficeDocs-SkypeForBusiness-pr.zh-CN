---
title: Skype for Business Server 2015 中的 EdgeServers 表
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
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 表是一个支持表。 每条记录都存储有关数据库中具有记录的呼叫所涉及的一台边缘服务器的信息。
ms.openlocfilehash: 98f37ecbf976fb08ae27e080f5e9e498558131fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813202"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="eb4fa-104">Skype for Business Server 2015 中的 EdgeServers 表</span><span class="sxs-lookup"><span data-stu-id="eb4fa-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eb4fa-105">EdgeServers 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="eb4fa-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="eb4fa-106">每条记录都存储有关数据库中具有记录的呼叫所涉及的一台边缘服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="eb4fa-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="eb4fa-107">**列**</span><span class="sxs-lookup"><span data-stu-id="eb4fa-107">**Column**</span></span>|<span data-ttu-id="eb4fa-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="eb4fa-108">**Data Type**</span></span>|<span data-ttu-id="eb4fa-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="eb4fa-109">**Key/Index**</span></span>|<span data-ttu-id="eb4fa-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="eb4fa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eb4fa-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="eb4fa-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="eb4fa-112">int</span><span class="sxs-lookup"><span data-stu-id="eb4fa-112">int</span></span>  <br/> |<span data-ttu-id="eb4fa-113">主</span><span class="sxs-lookup"><span data-stu-id="eb4fa-113">Primary</span></span>  <br/> |<span data-ttu-id="eb4fa-114">标识此边缘服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="eb4fa-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="eb4fa-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="eb4fa-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="eb4fa-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="eb4fa-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="eb4fa-117">边缘服务器名称。</span><span class="sxs-lookup"><span data-stu-id="eb4fa-117">Edge Server name.</span></span>  <br/> |
   

