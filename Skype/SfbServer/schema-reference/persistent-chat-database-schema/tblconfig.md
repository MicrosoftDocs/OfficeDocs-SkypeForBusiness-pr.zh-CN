---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些不支持持久聊天服务器的配置（一行）。
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809732"
---
# <a name="tblconfig"></a><span data-ttu-id="c9721-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="c9721-103">tblConfig</span></span>
 
<span data-ttu-id="c9721-104">tblConfig 包含一些不支持持久聊天服务器的配置（一行）。</span><span class="sxs-lookup"><span data-stu-id="c9721-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="c9721-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c9721-105">**Columns**</span></span>

|<span data-ttu-id="c9721-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c9721-106">**Column**</span></span>|<span data-ttu-id="c9721-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="c9721-107">**Type**</span></span>|<span data-ttu-id="c9721-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c9721-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9721-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="c9721-109">configLabel</span></span>  <br/> |<span data-ttu-id="c9721-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="c9721-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="c9721-111">包含“池”。</span><span class="sxs-lookup"><span data-stu-id="c9721-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="c9721-112">configContent</span><span class="sxs-lookup"><span data-stu-id="c9721-112">configContent</span></span>  <br/> |<span data-ttu-id="c9721-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c9721-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="c9721-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="c9721-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="c9721-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="c9721-115">configPoolID</span></span>  <br/> |<span data-ttu-id="c9721-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="c9721-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="c9721-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c9721-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="c9721-118">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="c9721-118">**Key**</span></span>

|<span data-ttu-id="c9721-119">**列**</span><span class="sxs-lookup"><span data-stu-id="c9721-119">**Column**</span></span>|<span data-ttu-id="c9721-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="c9721-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9721-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="c9721-121">configLabel</span></span>  <br/> |<span data-ttu-id="c9721-122">主键。</span><span class="sxs-lookup"><span data-stu-id="c9721-122">Primary key.</span></span>  <br/> |
   

