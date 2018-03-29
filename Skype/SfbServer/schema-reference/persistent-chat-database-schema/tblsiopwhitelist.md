---
title: tblSiopWhiteList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是已注册的外接程序可与节点相关联的列表。
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="01c36-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="01c36-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="01c36-104">tblSiopWhiteList 是已注册的外接程序可与节点相关联的列表。</span><span class="sxs-lookup"><span data-stu-id="01c36-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="01c36-105">**列**</span><span class="sxs-lookup"><span data-stu-id="01c36-105">**Columns**</span></span>

|<span data-ttu-id="01c36-106">**列**</span><span class="sxs-lookup"><span data-stu-id="01c36-106">**Column**</span></span>|<span data-ttu-id="01c36-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="01c36-107">**Type**</span></span>|<span data-ttu-id="01c36-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="01c36-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="01c36-109">siopID</span><span class="sxs-lookup"><span data-stu-id="01c36-109">siopID</span></span>  <br/> |<span data-ttu-id="01c36-110">GUID，不为空</span><span class="sxs-lookup"><span data-stu-id="01c36-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="01c36-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="01c36-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="01c36-112">siopName</span><span class="sxs-lookup"><span data-stu-id="01c36-112">siopName</span></span>  <br/> |<span data-ttu-id="01c36-113">nvarchar (50) 不为空</span><span class="sxs-lookup"><span data-stu-id="01c36-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="01c36-114">外接程序的显示名称。</span><span class="sxs-lookup"><span data-stu-id="01c36-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="01c36-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="01c36-115">siopUrl</span></span>  <br/> |<span data-ttu-id="01c36-116">nvarchar (255) 不为空</span><span class="sxs-lookup"><span data-stu-id="01c36-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="01c36-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="01c36-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="01c36-118">**密钥**</span><span class="sxs-lookup"><span data-stu-id="01c36-118">**Key**</span></span>

|<span data-ttu-id="01c36-119">**列**</span><span class="sxs-lookup"><span data-stu-id="01c36-119">**Column**</span></span>|<span data-ttu-id="01c36-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="01c36-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="01c36-121">siopID</span><span class="sxs-lookup"><span data-stu-id="01c36-121">siopID</span></span>  <br/> |<span data-ttu-id="01c36-122">为主键。</span><span class="sxs-lookup"><span data-stu-id="01c36-122">Primary key.</span></span>  <br/> |
   

