---
title: ContentTypes 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表，存储的对等会话和会议会话中使用的内容类型列表。 表中的每条记录代表一个内容类型。
ms.openlocfilehash: e30f5f142b9b1e166266cf8d45fe7657fee1b1b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901078"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="91515-104">ContentTypes 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="91515-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="91515-105">ContentTypes 表是一个支持表，存储的对等会话和会议会话中使用的内容类型列表。</span><span class="sxs-lookup"><span data-stu-id="91515-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="91515-106">表中的每条记录代表一个内容类型。</span><span class="sxs-lookup"><span data-stu-id="91515-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="91515-107">**列**</span><span class="sxs-lookup"><span data-stu-id="91515-107">**Column**</span></span>|<span data-ttu-id="91515-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="91515-108">**Data Type**</span></span>|<span data-ttu-id="91515-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="91515-109">**Key/Index**</span></span>|<span data-ttu-id="91515-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="91515-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91515-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="91515-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="91515-112">int</span><span class="sxs-lookup"><span data-stu-id="91515-112">int</span></span>  <br/> |<span data-ttu-id="91515-113">Primary</span><span class="sxs-lookup"><span data-stu-id="91515-113">Primary</span></span>  <br/> |<span data-ttu-id="91515-114">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="91515-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="91515-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="91515-115">**ContentType**</span></span> <br/> |<span data-ttu-id="91515-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91515-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="91515-117">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="91515-117">Content type name.</span></span>  <br/> |
   

