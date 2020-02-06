---
title: Skype for Business Server 2015 中的 ContentTypes 表
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型的列表。 表中的每条记录表示一种内容类型。
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815300"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="45571-104">Skype for Business Server 2015 中的 ContentTypes 表</span><span class="sxs-lookup"><span data-stu-id="45571-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="45571-105">ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型的列表。</span><span class="sxs-lookup"><span data-stu-id="45571-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="45571-106">表中的每条记录表示一种内容类型。</span><span class="sxs-lookup"><span data-stu-id="45571-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="45571-107">**列**</span><span class="sxs-lookup"><span data-stu-id="45571-107">**Column**</span></span>|<span data-ttu-id="45571-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="45571-108">**Data Type**</span></span>|<span data-ttu-id="45571-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="45571-109">**Key/Index**</span></span>|<span data-ttu-id="45571-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="45571-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45571-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="45571-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="45571-112">int</span><span class="sxs-lookup"><span data-stu-id="45571-112">int</span></span>  <br/> |<span data-ttu-id="45571-113">Primary</span><span class="sxs-lookup"><span data-stu-id="45571-113">Primary</span></span>  <br/> |<span data-ttu-id="45571-114">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="45571-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="45571-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="45571-115">**ContentType**</span></span> <br/> |<span data-ttu-id="45571-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="45571-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="45571-117">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="45571-117">Content type name.</span></span>  <br/> |
   

