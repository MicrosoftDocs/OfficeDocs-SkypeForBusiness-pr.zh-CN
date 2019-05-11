---
title: CallType 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是一个静态表，用于存储可能的呼叫类型的列表。
ms.openlocfilehash: a75ae3e22d435241e6bf2eb81b8268a7f1bb5a40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924792"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ebc7f-103">CallType 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="ebc7f-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ebc7f-104">CallType 表是一个静态表，用于存储可能的呼叫类型的列表。</span><span class="sxs-lookup"><span data-stu-id="ebc7f-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="ebc7f-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ebc7f-105">**Column**</span></span>|<span data-ttu-id="ebc7f-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ebc7f-106">**Data Type**</span></span>|<span data-ttu-id="ebc7f-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ebc7f-107">**Key/Index**</span></span>|<span data-ttu-id="ebc7f-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ebc7f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ebc7f-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="ebc7f-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="ebc7f-110">int</span><span class="sxs-lookup"><span data-stu-id="ebc7f-110">int</span></span>  <br/> |<span data-ttu-id="ebc7f-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ebc7f-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ebc7f-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="ebc7f-112">**CallType**</span></span> <br/> |<span data-ttu-id="ebc7f-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="ebc7f-113">nvarchar</span></span>  <br/> || <span data-ttu-id="ebc7f-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="ebc7f-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ebc7f-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="ebc7f-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="ebc7f-116">1-即时消息</span><span class="sxs-lookup"><span data-stu-id="ebc7f-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="ebc7f-117">2--应用程序共享</span><span class="sxs-lookup"><span data-stu-id="ebc7f-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="ebc7f-118">3-音频</span><span class="sxs-lookup"><span data-stu-id="ebc7f-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="ebc7f-119">4-音频和视频</span><span class="sxs-lookup"><span data-stu-id="ebc7f-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="ebc7f-120">5-文件传输</span><span class="sxs-lookup"><span data-stu-id="ebc7f-120">5 - File Transfer</span></span> <br/> |
   

