---
title: Skype for Business Server 2015 中的 ContentTypes 表
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型列表。 表中的每条记录表示一种内容类型。
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816082"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5d156-104">Skype for Business Server 2015 中的 ContentTypes 表</span><span class="sxs-lookup"><span data-stu-id="5d156-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d156-105">ContentTypes 表是一个支持表，用于存储对等会话和会议会话中使用的内容类型列表。</span><span class="sxs-lookup"><span data-stu-id="5d156-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="5d156-106">表中的每条记录表示一种内容类型。</span><span class="sxs-lookup"><span data-stu-id="5d156-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="5d156-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5d156-107">**Column**</span></span>|<span data-ttu-id="5d156-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5d156-108">**Data Type**</span></span>|<span data-ttu-id="5d156-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5d156-109">**Key/Index**</span></span>|<span data-ttu-id="5d156-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="5d156-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d156-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="5d156-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="5d156-112">int</span><span class="sxs-lookup"><span data-stu-id="5d156-112">int</span></span>  <br/> |<span data-ttu-id="5d156-113">主</span><span class="sxs-lookup"><span data-stu-id="5d156-113">Primary</span></span>  <br/> |<span data-ttu-id="5d156-114">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="5d156-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="5d156-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="5d156-115">**ContentType**</span></span> <br/> |<span data-ttu-id="5d156-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5d156-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="5d156-117">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="5d156-117">Content type name.</span></span>  <br/> |
   

