---
title: 用户代理视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: 用户代理视图存储在数据库中具有记录的会话中涉及的用户代理信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a><span data-ttu-id="9b21b-104">用户代理视图</span><span class="sxs-lookup"><span data-stu-id="9b21b-104">UserAgent view</span></span>
 
<span data-ttu-id="9b21b-105">用户代理视图存储在数据库中具有记录的会话中涉及的用户代理信息。</span><span class="sxs-lookup"><span data-stu-id="9b21b-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="9b21b-106">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="9b21b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9b21b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9b21b-107">**Column**</span></span>|<span data-ttu-id="9b21b-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9b21b-108">**Data Type**</span></span>|<span data-ttu-id="9b21b-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9b21b-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b21b-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="9b21b-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="9b21b-111">int</span><span class="sxs-lookup"><span data-stu-id="9b21b-111">int</span></span>  <br/> |<span data-ttu-id="9b21b-112">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="9b21b-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="9b21b-113">用户代理</span><span class="sxs-lookup"><span data-stu-id="9b21b-113">UserAgent</span></span>  <br/> |<span data-ttu-id="9b21b-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9b21b-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9b21b-115">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="9b21b-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="9b21b-116">UAType</span><span class="sxs-lookup"><span data-stu-id="9b21b-116">UAType</span></span>  <br/> |<span data-ttu-id="9b21b-117">smallint</span><span class="sxs-lookup"><span data-stu-id="9b21b-117">smallint</span></span>  <br/> |<span data-ttu-id="9b21b-118">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="9b21b-118">Type of user agent.</span></span> <span data-ttu-id="9b21b-119">[用户代理表](useragent.md)的更多详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="9b21b-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="9b21b-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="9b21b-120">UACategory</span></span>  <br/> |<span data-ttu-id="9b21b-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="9b21b-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="9b21b-122">用户代理所属的类别。</span><span class="sxs-lookup"><span data-stu-id="9b21b-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="9b21b-123">例如，Conferencing_Attendant_1.0 的用户代理都属于 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="9b21b-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

