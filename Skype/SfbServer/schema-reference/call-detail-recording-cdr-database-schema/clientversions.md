---
title: Skype for Business Server 2015 中的 ClientVersions 表
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表是一个支持表，用于存储已参与数据库中记录的会话的各种客户端类型和版本的列表。表中的每条记录都代表一个客户端版本。
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813312"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9bc58-104">Skype for Business Server 2015 中的 ClientVersions 表</span><span class="sxs-lookup"><span data-stu-id="9bc58-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9bc58-p102">ClientVersions 表是一个支持表，用于存储已参与数据库中记录的会话的各种客户端类型和版本的列表。表中的每条记录都代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="9bc58-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="9bc58-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9bc58-107">**Column**</span></span>|<span data-ttu-id="9bc58-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9bc58-108">**Data Type**</span></span>|<span data-ttu-id="9bc58-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9bc58-109">**Key/Index**</span></span>|<span data-ttu-id="9bc58-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="9bc58-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bc58-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="9bc58-111">**VersionId**</span></span> <br/> |<span data-ttu-id="9bc58-112">**int**</span><span class="sxs-lookup"><span data-stu-id="9bc58-112">**int**</span></span> <br/> |<span data-ttu-id="9bc58-113">主</span><span class="sxs-lookup"><span data-stu-id="9bc58-113">Primary</span></span>  <br/> |<span data-ttu-id="9bc58-114">标识此客户端类型和版本的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="9bc58-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="9bc58-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="9bc58-115">**Version**</span></span> <br/> |<span data-ttu-id="9bc58-116">**nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="9bc58-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="9bc58-117">版本名称。</span><span class="sxs-lookup"><span data-stu-id="9bc58-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="9bc58-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="9bc58-118">**ClientType**</span></span> <br/> |<span data-ttu-id="9bc58-119">int</span><span class="sxs-lookup"><span data-stu-id="9bc58-119">int</span></span>  <br/> ||<span data-ttu-id="9bc58-120">指定会话中使用的客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="9bc58-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="9bc58-121">有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。</span><span class="sxs-lookup"><span data-stu-id="9bc58-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="9bc58-122">此字段在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="9bc58-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

