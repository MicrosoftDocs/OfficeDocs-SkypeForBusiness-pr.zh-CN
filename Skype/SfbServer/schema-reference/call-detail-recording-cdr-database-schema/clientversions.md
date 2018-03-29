---
title: 在业务服务器 2015年的 Skype 的 ClientVersions 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 是一个支持的表来存储各种客户端类型的列表和参加会话记录在数据库中的版本。 每个表中的记录表示某个客户端版本。
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="87436-104">在业务服务器 2015年的 Skype 的 ClientVersions 表</span><span class="sxs-lookup"><span data-stu-id="87436-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="87436-105">ClientVersions 是一个支持的表来存储各种客户端类型的列表和参加会话记录在数据库中的版本。</span><span class="sxs-lookup"><span data-stu-id="87436-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="87436-106">每个表中的记录表示某个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="87436-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="87436-107">**列**</span><span class="sxs-lookup"><span data-stu-id="87436-107">**Column**</span></span>|<span data-ttu-id="87436-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="87436-108">**Data Type**</span></span>|<span data-ttu-id="87436-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="87436-109">**Key/Index**</span></span>|<span data-ttu-id="87436-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="87436-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="87436-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="87436-111">**VersionId**</span></span> <br/> |<span data-ttu-id="87436-112">**int**</span><span class="sxs-lookup"><span data-stu-id="87436-112">**int**</span></span> <br/> |<span data-ttu-id="87436-113">Primary</span><span class="sxs-lookup"><span data-stu-id="87436-113">Primary</span></span>  <br/> |<span data-ttu-id="87436-114">标识此客户端的类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="87436-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="87436-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="87436-115">**Version**</span></span> <br/> |<span data-ttu-id="87436-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="87436-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="87436-117">版本名称。</span><span class="sxs-lookup"><span data-stu-id="87436-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="87436-118">**客户端类型**</span><span class="sxs-lookup"><span data-stu-id="87436-118">**ClientType**</span></span> <br/> |<span data-ttu-id="87436-119">int</span><span class="sxs-lookup"><span data-stu-id="87436-119">int</span></span>  <br/> ||<span data-ttu-id="87436-120">指定客户端会话中使用的类型。</span><span class="sxs-lookup"><span data-stu-id="87436-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="87436-121">[UserAgentDef 表](useragentdef.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="87436-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="87436-122">在 Microsoft Lync Server 2013 引入了此字段。</span><span class="sxs-lookup"><span data-stu-id="87436-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

