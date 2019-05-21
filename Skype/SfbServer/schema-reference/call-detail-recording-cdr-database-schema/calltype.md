---
title: Skype for Business Server 2015 中的 CallType 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是一个静态表, 用于存储可能的调用类型的列表。
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296558"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="db896-103">Skype for Business Server 2015 中的 CallType 表</span><span class="sxs-lookup"><span data-stu-id="db896-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="db896-104">CallType 表是一个静态表, 用于存储可能的调用类型的列表。</span><span class="sxs-lookup"><span data-stu-id="db896-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="db896-105">**列**</span><span class="sxs-lookup"><span data-stu-id="db896-105">**Column**</span></span>|<span data-ttu-id="db896-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="db896-106">**Data Type**</span></span>|<span data-ttu-id="db896-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="db896-107">**Key/Index**</span></span>|<span data-ttu-id="db896-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="db896-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="db896-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="db896-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="db896-110">int</span><span class="sxs-lookup"><span data-stu-id="db896-110">int</span></span>  <br/> |<span data-ttu-id="db896-111">Primary</span><span class="sxs-lookup"><span data-stu-id="db896-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="db896-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="db896-112">**CallType**</span></span> <br/> |<span data-ttu-id="db896-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="db896-113">nvarchar</span></span>  <br/> || <span data-ttu-id="db896-114">允许的值:</span><span class="sxs-lookup"><span data-stu-id="db896-114">Allowed values:</span></span> <br/>  <span data-ttu-id="db896-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="db896-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="db896-116">1-即时消息</span><span class="sxs-lookup"><span data-stu-id="db896-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="db896-117">2--应用程序共享</span><span class="sxs-lookup"><span data-stu-id="db896-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="db896-118">3--音频</span><span class="sxs-lookup"><span data-stu-id="db896-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="db896-119">4-音频和视频</span><span class="sxs-lookup"><span data-stu-id="db896-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="db896-120">5-文件传输</span><span class="sxs-lookup"><span data-stu-id="db896-120">5 - File Transfer</span></span> <br/> |
   

