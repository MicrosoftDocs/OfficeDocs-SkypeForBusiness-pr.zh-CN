---
title: ClientVersions 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储有关各种客户端类型和已参与记录数据库中的会话的版本信息。 在视图中的每条记录代表一个客户端版本。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213394"
---
# <a name="clientversions-view"></a><span data-ttu-id="4c61d-105">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="4c61d-105">ClientVersions view</span></span>
 
<span data-ttu-id="4c61d-106">ClientVersions 视图存储有关各种客户端类型和已参与记录数据库中的会话的版本信息。</span><span class="sxs-lookup"><span data-stu-id="4c61d-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4c61d-107">在视图中的每条记录代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="4c61d-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="4c61d-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4c61d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c61d-109">可能有多个记录的某些列。</span><span class="sxs-lookup"><span data-stu-id="4c61d-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="4c61d-110">**列**</span><span class="sxs-lookup"><span data-stu-id="4c61d-110">**Column**</span></span>|<span data-ttu-id="4c61d-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4c61d-111">**Data Type**</span></span>|<span data-ttu-id="4c61d-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4c61d-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c61d-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="4c61d-113">**VersionId**</span></span> <br/> |<span data-ttu-id="4c61d-114">int</span><span class="sxs-lookup"><span data-stu-id="4c61d-114">int</span></span>  <br/> |<span data-ttu-id="4c61d-115">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="4c61d-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="4c61d-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="4c61d-116">**Version**</span></span> <br/> |<span data-ttu-id="4c61d-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4c61d-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4c61d-118">代表用户代理。</span><span class="sxs-lookup"><span data-stu-id="4c61d-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="4c61d-119">**客户端类型**</span><span class="sxs-lookup"><span data-stu-id="4c61d-119">**ClientType**</span></span> <br/> |<span data-ttu-id="4c61d-120">int</span><span class="sxs-lookup"><span data-stu-id="4c61d-120">int</span></span>  <br/> |<span data-ttu-id="4c61d-121">客户端类型。</span><span class="sxs-lookup"><span data-stu-id="4c61d-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="4c61d-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="4c61d-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="4c61d-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="4c61d-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="4c61d-124">客户端所属的类别。</span><span class="sxs-lookup"><span data-stu-id="4c61d-124">Category that the client belongs to.</span></span> <span data-ttu-id="4c61d-125">例如，客户端 Conferencing_Attendant_1.0 所属 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="4c61d-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

