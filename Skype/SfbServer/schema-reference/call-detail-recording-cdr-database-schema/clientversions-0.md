---
title: ClientVersions 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储不同的客户端类型和参加会话记录在数据库中的版本信息。 每个视图中的记录表示某个客户端版本。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a><span data-ttu-id="e11ed-105">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="e11ed-105">ClientVersions view</span></span>
 
<span data-ttu-id="e11ed-106">ClientVersions 视图存储不同的客户端类型和参加会话记录在数据库中的版本信息。</span><span class="sxs-lookup"><span data-stu-id="e11ed-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e11ed-107">每个视图中的记录表示某个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="e11ed-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="e11ed-108">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="e11ed-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e11ed-109">可能有多个记录的某些列。</span><span class="sxs-lookup"><span data-stu-id="e11ed-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="e11ed-110">**列**</span><span class="sxs-lookup"><span data-stu-id="e11ed-110">**Column**</span></span>|<span data-ttu-id="e11ed-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e11ed-111">**Data Type**</span></span>|<span data-ttu-id="e11ed-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e11ed-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e11ed-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="e11ed-113">**VersionId**</span></span> <br/> |<span data-ttu-id="e11ed-114">int</span><span class="sxs-lookup"><span data-stu-id="e11ed-114">int</span></span>  <br/> |<span data-ttu-id="e11ed-115">标识此客户端的类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e11ed-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="e11ed-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="e11ed-116">**Version**</span></span> <br/> |<span data-ttu-id="e11ed-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e11ed-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e11ed-118">表示用户代理。</span><span class="sxs-lookup"><span data-stu-id="e11ed-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="e11ed-119">**客户端类型**</span><span class="sxs-lookup"><span data-stu-id="e11ed-119">**ClientType**</span></span> <br/> |<span data-ttu-id="e11ed-120">int</span><span class="sxs-lookup"><span data-stu-id="e11ed-120">int</span></span>  <br/> |<span data-ttu-id="e11ed-121">客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="e11ed-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="e11ed-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="e11ed-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="e11ed-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="e11ed-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="e11ed-124">客户端所属的类别。</span><span class="sxs-lookup"><span data-stu-id="e11ed-124">Category that the client belongs to.</span></span> <span data-ttu-id="e11ed-125">例如，客户端 Conferencing_Attendant_1.0 就属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="e11ed-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

