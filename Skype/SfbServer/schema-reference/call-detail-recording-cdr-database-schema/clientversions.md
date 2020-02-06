---
title: Skype for Business Server 2015 中的 ClientVersions 表
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表是一个支持表，用于存储参与数据库中记录的会话的各种客户端类型和版本的列表。 表中的每条记录表示一个客户端版本。
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815400"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="77b59-104">Skype for Business Server 2015 中的 ClientVersions 表</span><span class="sxs-lookup"><span data-stu-id="77b59-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="77b59-105">ClientVersions 表是一个支持表，用于存储参与数据库中记录的会话的各种客户端类型和版本的列表。</span><span class="sxs-lookup"><span data-stu-id="77b59-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="77b59-106">表中的每条记录表示一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="77b59-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="77b59-107">**列**</span><span class="sxs-lookup"><span data-stu-id="77b59-107">**Column**</span></span>|<span data-ttu-id="77b59-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="77b59-108">**Data Type**</span></span>|<span data-ttu-id="77b59-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="77b59-109">**Key/Index**</span></span>|<span data-ttu-id="77b59-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="77b59-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77b59-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="77b59-111">**VersionId**</span></span> <br/> |<span data-ttu-id="77b59-112">**int**</span><span class="sxs-lookup"><span data-stu-id="77b59-112">**int**</span></span> <br/> |<span data-ttu-id="77b59-113">Primary</span><span class="sxs-lookup"><span data-stu-id="77b59-113">Primary</span></span>  <br/> |<span data-ttu-id="77b59-114">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="77b59-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="77b59-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="77b59-115">**Version**</span></span> <br/> |<span data-ttu-id="77b59-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="77b59-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="77b59-117">版本名称。</span><span class="sxs-lookup"><span data-stu-id="77b59-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="77b59-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="77b59-118">**ClientType**</span></span> <br/> |<span data-ttu-id="77b59-119">int</span><span class="sxs-lookup"><span data-stu-id="77b59-119">int</span></span>  <br/> ||<span data-ttu-id="77b59-120">指定会话中使用的客户端类型。</span><span class="sxs-lookup"><span data-stu-id="77b59-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="77b59-121">有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。</span><span class="sxs-lookup"><span data-stu-id="77b59-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="77b59-122">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77b59-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

