---
title: ClientVersions 视图
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储已参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录都代表一个客户端版本。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813352"
---
# <a name="clientversions-view"></a><span data-ttu-id="92486-105">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="92486-105">ClientVersions view</span></span>
 
<span data-ttu-id="92486-106">ClientVersions 视图存储已参与数据库中记录的会话的各种客户端类型和版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="92486-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="92486-107">视图中的每条记录都代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="92486-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="92486-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="92486-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92486-109">某些列可能有多条记录。</span><span class="sxs-lookup"><span data-stu-id="92486-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="92486-110">**列**</span><span class="sxs-lookup"><span data-stu-id="92486-110">**Column**</span></span>|<span data-ttu-id="92486-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="92486-111">**Data Type**</span></span>|<span data-ttu-id="92486-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="92486-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92486-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="92486-113">**VersionId**</span></span> <br/> |<span data-ttu-id="92486-114">int</span><span class="sxs-lookup"><span data-stu-id="92486-114">int</span></span>  <br/> |<span data-ttu-id="92486-115">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="92486-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="92486-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="92486-116">**Version**</span></span> <br/> |<span data-ttu-id="92486-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="92486-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="92486-118">代表用户代理。</span><span class="sxs-lookup"><span data-stu-id="92486-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="92486-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="92486-119">**ClientType**</span></span> <br/> |<span data-ttu-id="92486-120">int</span><span class="sxs-lookup"><span data-stu-id="92486-120">int</span></span>  <br/> |<span data-ttu-id="92486-121">客户端类型。</span><span class="sxs-lookup"><span data-stu-id="92486-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="92486-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="92486-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="92486-123">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="92486-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="92486-p103">客户端所属的类别。例如，客户端 Conferencing_Attendant_1.0 属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="92486-p103">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

