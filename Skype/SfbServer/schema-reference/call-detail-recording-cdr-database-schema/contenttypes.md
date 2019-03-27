---
title: ContentTypes 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表，存储的对等会话和会议会话中使用的内容类型列表。 表中的每条记录代表一个内容类型。
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894984"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9bcb5-104">ContentTypes 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="9bcb5-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9bcb5-105">ContentTypes 表是一个支持表，存储的对等会话和会议会话中使用的内容类型列表。</span><span class="sxs-lookup"><span data-stu-id="9bcb5-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="9bcb5-106">表中的每条记录代表一个内容类型。</span><span class="sxs-lookup"><span data-stu-id="9bcb5-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="9bcb5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9bcb5-107">**Column**</span></span>|<span data-ttu-id="9bcb5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9bcb5-108">**Data Type**</span></span>|<span data-ttu-id="9bcb5-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9bcb5-109">**Key/Index**</span></span>|<span data-ttu-id="9bcb5-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9bcb5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bcb5-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="9bcb5-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="9bcb5-112">int</span><span class="sxs-lookup"><span data-stu-id="9bcb5-112">int</span></span>  <br/> |<span data-ttu-id="9bcb5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9bcb5-113">Primary</span></span>  <br/> |<span data-ttu-id="9bcb5-114">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="9bcb5-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="9bcb5-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="9bcb5-115">**ContentType**</span></span> <br/> |<span data-ttu-id="9bcb5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9bcb5-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9bcb5-117">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="9bcb5-117">Content type name.</span></span>  <br/> |
   

