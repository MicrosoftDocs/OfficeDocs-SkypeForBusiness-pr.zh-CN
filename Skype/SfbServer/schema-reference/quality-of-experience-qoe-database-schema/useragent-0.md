---
title: UserAgent 视图
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800012"
---
# <a name="useragent-view"></a><span data-ttu-id="3212d-104">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="3212d-104">UserAgent view</span></span>
 
<span data-ttu-id="3212d-105">UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="3212d-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="3212d-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3212d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3212d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3212d-107">**Column**</span></span>|<span data-ttu-id="3212d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3212d-108">**Data Type**</span></span>|<span data-ttu-id="3212d-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="3212d-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3212d-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="3212d-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="3212d-111">int</span><span class="sxs-lookup"><span data-stu-id="3212d-111">int</span></span>  <br/> |<span data-ttu-id="3212d-112">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="3212d-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="3212d-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="3212d-113">UserAgent</span></span>  <br/> |<span data-ttu-id="3212d-114">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3212d-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3212d-115">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="3212d-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="3212d-116">UAType</span><span class="sxs-lookup"><span data-stu-id="3212d-116">UAType</span></span>  <br/> |<span data-ttu-id="3212d-117">smallint</span><span class="sxs-lookup"><span data-stu-id="3212d-117">smallint</span></span>  <br/> |<span data-ttu-id="3212d-118">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="3212d-118">Type of user agent.</span></span> <span data-ttu-id="3212d-119">有关详细信息， [请参阅 UserAgent](useragent.md) 表。</span><span class="sxs-lookup"><span data-stu-id="3212d-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="3212d-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="3212d-120">UACategory</span></span>  <br/> |<span data-ttu-id="3212d-121">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="3212d-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="3212d-p104">用户代理所属的类别。例如，用户代理 Conferencing_Attendant_1.0 属于 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="3212d-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

