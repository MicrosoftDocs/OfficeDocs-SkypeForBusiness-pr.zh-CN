---
title: ClientVersions 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录表示一个客户端版本。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296537"
---
# <a name="clientversions-view"></a><span data-ttu-id="277f8-105">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="277f8-105">ClientVersions view</span></span>
 
<span data-ttu-id="277f8-106">ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="277f8-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="277f8-107">视图中的每条记录表示一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="277f8-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="277f8-108">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="277f8-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="277f8-109">某些列可能有多条记录。</span><span class="sxs-lookup"><span data-stu-id="277f8-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="277f8-110">**列**</span><span class="sxs-lookup"><span data-stu-id="277f8-110">**Column**</span></span>|<span data-ttu-id="277f8-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="277f8-111">**Data Type**</span></span>|<span data-ttu-id="277f8-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="277f8-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="277f8-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="277f8-113">**VersionId**</span></span> <br/> |<span data-ttu-id="277f8-114">int</span><span class="sxs-lookup"><span data-stu-id="277f8-114">int</span></span>  <br/> |<span data-ttu-id="277f8-115">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="277f8-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="277f8-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="277f8-116">**Version**</span></span> <br/> |<span data-ttu-id="277f8-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277f8-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="277f8-118">表示用户代理。</span><span class="sxs-lookup"><span data-stu-id="277f8-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="277f8-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="277f8-119">**ClientType**</span></span> <br/> |<span data-ttu-id="277f8-120">int</span><span class="sxs-lookup"><span data-stu-id="277f8-120">int</span></span>  <br/> |<span data-ttu-id="277f8-121">客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="277f8-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="277f8-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="277f8-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="277f8-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="277f8-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="277f8-124">客户端所属的类别。</span><span class="sxs-lookup"><span data-stu-id="277f8-124">Category that the client belongs to.</span></span> <span data-ttu-id="277f8-125">例如, 客户端 Conferencing_Attendant_ 1.0 属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="277f8-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

