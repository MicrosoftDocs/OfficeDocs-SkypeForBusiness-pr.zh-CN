---
title: ConferenceUris 视图
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
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris 视图存储参与会议会话的 Uri 的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 4f8b61628a3049086799b901d826834bf54c9a68
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815320"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="34fe7-104">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="34fe7-104">ConferenceUris view</span></span>
 
<span data-ttu-id="34fe7-105">ConfernceUris 视图存储参与会议会话的 Uri 的相关信息。</span><span class="sxs-lookup"><span data-stu-id="34fe7-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="34fe7-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="34fe7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="34fe7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="34fe7-107">**Column**</span></span>|<span data-ttu-id="34fe7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="34fe7-108">**Data Type**</span></span>|<span data-ttu-id="34fe7-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="34fe7-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34fe7-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="34fe7-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="34fe7-111">int</span><span class="sxs-lookup"><span data-stu-id="34fe7-111">int</span></span>  <br/> |<span data-ttu-id="34fe7-112">标识会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="34fe7-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="34fe7-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="34fe7-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="34fe7-114">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34fe7-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="34fe7-115">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="34fe7-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="34fe7-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="34fe7-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="34fe7-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34fe7-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="34fe7-118">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="34fe7-118">Type of conference URI.</span></span> <span data-ttu-id="34fe7-119">有关详细信息，请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="34fe7-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

