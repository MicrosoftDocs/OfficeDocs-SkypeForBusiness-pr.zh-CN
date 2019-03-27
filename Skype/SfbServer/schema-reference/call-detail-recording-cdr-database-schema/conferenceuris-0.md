---
title: ConferenceUris 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris 视图存储已参与会议会话的 Uri 的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 7b049abd4a843df4c7fbc0d4b314ce71203e2938
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895724"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="4e21b-104">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="4e21b-104">ConferenceUris view</span></span>
 
<span data-ttu-id="4e21b-105">ConfernceUris 视图存储已参与会议会话的 Uri 的信息。</span><span class="sxs-lookup"><span data-stu-id="4e21b-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="4e21b-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4e21b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4e21b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4e21b-107">**Column**</span></span>|<span data-ttu-id="4e21b-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4e21b-108">**Data Type**</span></span>|<span data-ttu-id="4e21b-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4e21b-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4e21b-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="4e21b-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="4e21b-111">int</span><span class="sxs-lookup"><span data-stu-id="4e21b-111">int</span></span>  <br/> |<span data-ttu-id="4e21b-112">标识此会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="4e21b-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="4e21b-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="4e21b-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="4e21b-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4e21b-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4e21b-115">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="4e21b-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="4e21b-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="4e21b-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="4e21b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4e21b-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4e21b-118">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="4e21b-118">Type of conference URI.</span></span> <span data-ttu-id="4e21b-119">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4e21b-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

