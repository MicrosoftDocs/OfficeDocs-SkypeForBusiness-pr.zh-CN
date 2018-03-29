---
title: 在业务服务器 2015年的 Skype 的 EdgeServers 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 表是支持表。 每个记录存储在数据库中具有记录的调用所涉及的一个边缘服务器有关的信息。
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8ecf6-104">在业务服务器 2015年的 Skype 的 EdgeServers 表</span><span class="sxs-lookup"><span data-stu-id="8ecf6-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ecf6-105">EdgeServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="8ecf6-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="8ecf6-106">每个记录存储在数据库中具有记录的调用所涉及的一个边缘服务器有关的信息。</span><span class="sxs-lookup"><span data-stu-id="8ecf6-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="8ecf6-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8ecf6-107">**Column**</span></span>|<span data-ttu-id="8ecf6-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8ecf6-108">**Data Type**</span></span>|<span data-ttu-id="8ecf6-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8ecf6-109">**Key/Index**</span></span>|<span data-ttu-id="8ecf6-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8ecf6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ecf6-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="8ecf6-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="8ecf6-112">int</span><span class="sxs-lookup"><span data-stu-id="8ecf6-112">int</span></span>  <br/> |<span data-ttu-id="8ecf6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8ecf6-113">Primary</span></span>  <br/> |<span data-ttu-id="8ecf6-114">标识此边缘服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="8ecf6-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="8ecf6-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="8ecf6-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="8ecf6-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8ecf6-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="8ecf6-117">边缘服务器名称。</span><span class="sxs-lookup"><span data-stu-id="8ecf6-117">Edge Server name.</span></span>  <br/> |
   

