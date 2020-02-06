---
title: UserAgent 视图
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805080"
---
# <a name="useragent-view"></a><span data-ttu-id="8b7b0-104">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="8b7b0-104">UserAgent view</span></span>
 
<span data-ttu-id="8b7b0-105">UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="8b7b0-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8b7b0-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8b7b0-107">**Column**</span></span>|<span data-ttu-id="8b7b0-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8b7b0-108">**Data Type**</span></span>|<span data-ttu-id="8b7b0-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8b7b0-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b7b0-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="8b7b0-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="8b7b0-111">int</span><span class="sxs-lookup"><span data-stu-id="8b7b0-111">int</span></span>  <br/> |<span data-ttu-id="8b7b0-112">标识此用户代理的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="8b7b0-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="8b7b0-113">UserAgent</span></span>  <br/> |<span data-ttu-id="8b7b0-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b7b0-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8b7b0-115">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="8b7b0-116">UAType</span><span class="sxs-lookup"><span data-stu-id="8b7b0-116">UAType</span></span>  <br/> |<span data-ttu-id="8b7b0-117">smallint</span><span class="sxs-lookup"><span data-stu-id="8b7b0-117">smallint</span></span>  <br/> |<span data-ttu-id="8b7b0-118">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-118">Type of user agent.</span></span> <span data-ttu-id="8b7b0-119">有关详细信息，请参阅[UserAgent 表](useragent.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="8b7b0-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="8b7b0-120">UACategory</span></span>  <br/> |<span data-ttu-id="8b7b0-121">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="8b7b0-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="8b7b0-122">用户代理所属的类别。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="8b7b0-123">例如，Conferencing_Attendant_1 .0 的用户代理属于 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="8b7b0-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

