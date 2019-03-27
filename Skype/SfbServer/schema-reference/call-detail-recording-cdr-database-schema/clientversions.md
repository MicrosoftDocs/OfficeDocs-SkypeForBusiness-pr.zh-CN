---
title: 请参阅 ClientVersions table 中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表是一个支持表，用于存储各种客户端类型的列表和已参与记录数据库中的会话的版本。 表中的每条记录代表一个客户端版本。
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898527"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b05e6-104">请参阅 ClientVersions table 中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="b05e6-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b05e6-105">ClientVersions 表是一个支持表，用于存储各种客户端类型的列表和已参与记录数据库中的会话的版本。</span><span class="sxs-lookup"><span data-stu-id="b05e6-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b05e6-106">表中的每条记录代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="b05e6-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="b05e6-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b05e6-107">**Column**</span></span>|<span data-ttu-id="b05e6-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b05e6-108">**Data Type**</span></span>|<span data-ttu-id="b05e6-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b05e6-109">**Key/Index**</span></span>|<span data-ttu-id="b05e6-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b05e6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b05e6-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="b05e6-111">**VersionId**</span></span> <br/> |<span data-ttu-id="b05e6-112">**int**</span><span class="sxs-lookup"><span data-stu-id="b05e6-112">**int**</span></span> <br/> |<span data-ttu-id="b05e6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b05e6-113">Primary</span></span>  <br/> |<span data-ttu-id="b05e6-114">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b05e6-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="b05e6-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="b05e6-115">**Version**</span></span> <br/> |<span data-ttu-id="b05e6-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="b05e6-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="b05e6-117">版本名称。</span><span class="sxs-lookup"><span data-stu-id="b05e6-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="b05e6-118">**客户端类型**</span><span class="sxs-lookup"><span data-stu-id="b05e6-118">**ClientType**</span></span> <br/> |<span data-ttu-id="b05e6-119">int</span><span class="sxs-lookup"><span data-stu-id="b05e6-119">int</span></span>  <br/> ||<span data-ttu-id="b05e6-120">指定客户端会话中使用的类型。</span><span class="sxs-lookup"><span data-stu-id="b05e6-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="b05e6-121">请参阅[UserAgentDef 表](useragentdef.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b05e6-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="b05e6-122">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="b05e6-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

