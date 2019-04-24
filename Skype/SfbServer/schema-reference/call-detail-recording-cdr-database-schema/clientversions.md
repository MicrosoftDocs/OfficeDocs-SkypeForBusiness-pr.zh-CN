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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213380"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a305a-104">请参阅 ClientVersions table 中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="a305a-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a305a-105">ClientVersions 表是一个支持表，用于存储各种客户端类型的列表和已参与记录数据库中的会话的版本。</span><span class="sxs-lookup"><span data-stu-id="a305a-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a305a-106">表中的每条记录代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="a305a-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="a305a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a305a-107">**Column**</span></span>|<span data-ttu-id="a305a-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a305a-108">**Data Type**</span></span>|<span data-ttu-id="a305a-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a305a-109">**Key/Index**</span></span>|<span data-ttu-id="a305a-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a305a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a305a-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="a305a-111">**VersionId**</span></span> <br/> |<span data-ttu-id="a305a-112">**int**</span><span class="sxs-lookup"><span data-stu-id="a305a-112">**int**</span></span> <br/> |<span data-ttu-id="a305a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a305a-113">Primary</span></span>  <br/> |<span data-ttu-id="a305a-114">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a305a-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="a305a-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="a305a-115">**Version**</span></span> <br/> |<span data-ttu-id="a305a-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="a305a-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="a305a-117">版本名称。</span><span class="sxs-lookup"><span data-stu-id="a305a-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="a305a-118">**客户端类型**</span><span class="sxs-lookup"><span data-stu-id="a305a-118">**ClientType**</span></span> <br/> |<span data-ttu-id="a305a-119">int</span><span class="sxs-lookup"><span data-stu-id="a305a-119">int</span></span>  <br/> ||<span data-ttu-id="a305a-120">指定客户端会话中使用的类型。</span><span class="sxs-lookup"><span data-stu-id="a305a-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="a305a-121">请参阅[UserAgentDef 表](useragentdef.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a305a-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="a305a-122">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a305a-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

