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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录表示一个客户端版本。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815410"
---
# <a name="clientversions-view"></a><span data-ttu-id="d0adb-105">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="d0adb-105">ClientVersions view</span></span>
 
<span data-ttu-id="d0adb-106">ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="d0adb-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d0adb-107">视图中的每条记录表示一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="d0adb-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="d0adb-108">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="d0adb-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0adb-109">某些列可能有多条记录。</span><span class="sxs-lookup"><span data-stu-id="d0adb-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="d0adb-110">**列**</span><span class="sxs-lookup"><span data-stu-id="d0adb-110">**Column**</span></span>|<span data-ttu-id="d0adb-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d0adb-111">**Data Type**</span></span>|<span data-ttu-id="d0adb-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d0adb-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0adb-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="d0adb-113">**VersionId**</span></span> <br/> |<span data-ttu-id="d0adb-114">int</span><span class="sxs-lookup"><span data-stu-id="d0adb-114">int</span></span>  <br/> |<span data-ttu-id="d0adb-115">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d0adb-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="d0adb-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="d0adb-116">**Version**</span></span> <br/> |<span data-ttu-id="d0adb-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d0adb-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d0adb-118">表示用户代理。</span><span class="sxs-lookup"><span data-stu-id="d0adb-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="d0adb-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="d0adb-119">**ClientType**</span></span> <br/> |<span data-ttu-id="d0adb-120">int</span><span class="sxs-lookup"><span data-stu-id="d0adb-120">int</span></span>  <br/> |<span data-ttu-id="d0adb-121">客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="d0adb-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="d0adb-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="d0adb-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="d0adb-123">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="d0adb-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="d0adb-124">客户端所属的类别。</span><span class="sxs-lookup"><span data-stu-id="d0adb-124">Category that the client belongs to.</span></span> <span data-ttu-id="d0adb-125">例如，客户端 Conferencing_Attendant_1 .0 属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="d0adb-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

