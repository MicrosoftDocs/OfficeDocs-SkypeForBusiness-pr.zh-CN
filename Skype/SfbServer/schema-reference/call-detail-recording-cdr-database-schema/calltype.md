---
title: Skype for Business Server 2015 中的 CallType 表
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是存储可能的呼叫类型列表的静态表。
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813362"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="31e75-103">Skype for Business Server 2015 中的 CallType 表</span><span class="sxs-lookup"><span data-stu-id="31e75-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="31e75-104">CallType 表是存储可能的呼叫类型列表的静态表。</span><span class="sxs-lookup"><span data-stu-id="31e75-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="31e75-105">**列**</span><span class="sxs-lookup"><span data-stu-id="31e75-105">**Column**</span></span>|<span data-ttu-id="31e75-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="31e75-106">**Data Type**</span></span>|<span data-ttu-id="31e75-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="31e75-107">**Key/Index**</span></span>|<span data-ttu-id="31e75-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="31e75-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="31e75-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="31e75-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="31e75-110">int</span><span class="sxs-lookup"><span data-stu-id="31e75-110">int</span></span>  <br/> |<span data-ttu-id="31e75-111">主</span><span class="sxs-lookup"><span data-stu-id="31e75-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="31e75-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="31e75-112">**CallType**</span></span> <br/> |<span data-ttu-id="31e75-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="31e75-113">nvarchar</span></span>  <br/> || <span data-ttu-id="31e75-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="31e75-114">Allowed values:</span></span> <br/>  <span data-ttu-id="31e75-115">0 -- 未知</span><span class="sxs-lookup"><span data-stu-id="31e75-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="31e75-116">1 - 即时消息</span><span class="sxs-lookup"><span data-stu-id="31e75-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="31e75-117">2 -- 应用程序共享</span><span class="sxs-lookup"><span data-stu-id="31e75-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="31e75-118">3 -- 音频</span><span class="sxs-lookup"><span data-stu-id="31e75-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="31e75-119">4 - 音频和视频</span><span class="sxs-lookup"><span data-stu-id="31e75-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="31e75-120">5 - 文件传输</span><span class="sxs-lookup"><span data-stu-id="31e75-120">5 - File Transfer</span></span> <br/> |
   

