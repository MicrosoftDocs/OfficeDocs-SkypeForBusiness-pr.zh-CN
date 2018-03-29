---
title: 在业务服务器 2015年的 Skype 的内容类型表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: 内容类型表是一个支持的表来存储对等会话和会议会话中使用的内容类型的列表。 每个表中的记录表示一种内容类型。
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1a525-104">在业务服务器 2015年的 Skype 的内容类型表</span><span class="sxs-lookup"><span data-stu-id="1a525-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1a525-105">内容类型表是一个支持的表来存储对等会话和会议会话中使用的内容类型的列表。</span><span class="sxs-lookup"><span data-stu-id="1a525-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="1a525-106">每个表中的记录表示一种内容类型。</span><span class="sxs-lookup"><span data-stu-id="1a525-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="1a525-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1a525-107">**Column**</span></span>|<span data-ttu-id="1a525-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1a525-108">**Data Type**</span></span>|<span data-ttu-id="1a525-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="1a525-109">**Key/Index**</span></span>|<span data-ttu-id="1a525-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="1a525-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1a525-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="1a525-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="1a525-112">int</span><span class="sxs-lookup"><span data-stu-id="1a525-112">int</span></span>  <br/> |<span data-ttu-id="1a525-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1a525-113">Primary</span></span>  <br/> |<span data-ttu-id="1a525-114">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="1a525-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="1a525-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="1a525-115">**ContentType**</span></span> <br/> |<span data-ttu-id="1a525-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1a525-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="1a525-117">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="1a525-117">Content type name.</span></span>  <br/> |
   

