---
title: Outlook 网页版中的 Skype for Business Online 支持
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Office 365 中的 Outlook 网页版 (Outlook Web App) 在导航栏中提供基本 Skype for Business Web 客户端。 此基本客户端适用于其管理员尚未为其 Office 365 组织配置虚 URL 的联机用户。 只要用户的帐户处于联机状态, 并且没有虚 URL, 即使其组织拥有某些在本地托管的用户帐户, 他们仍将看到体验。 拥有本地用户帐户 (无论他们是否有虚 URL) 或由 Microsoft 托管的用户将在 Outlook web app 中看到 Lync 体验。
ms.openlocfilehash: 3a985bd8ad0a04198501ca8d1ec780496c59f561
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285081"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="8c82e-106">Outlook 网页版中的 Skype for Business Online 支持</span><span class="sxs-lookup"><span data-stu-id="8c82e-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="8c82e-107">Office 365 中的 Outlook 网页版 (Outlook Web App) 在导航栏中提供基本 Skype for Business Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="8c82e-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="8c82e-108">此基本客户端适用于其管理员尚未为其 Office 365 组织配置虚 URL 的联机用户。</span><span class="sxs-lookup"><span data-stu-id="8c82e-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="8c82e-109">只要用户的帐户处于联机状态, 并且没有虚 URL, 即使其组织拥有某些在本地托管的用户帐户, 他们仍将看到体验。</span><span class="sxs-lookup"><span data-stu-id="8c82e-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="8c82e-110">拥有本地用户帐户 (无论他们是否有虚 URL) 或由 Microsoft 托管的用户将在 Outlook web app 中看到 Lync 体验。</span><span class="sxs-lookup"><span data-stu-id="8c82e-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="8c82e-111">下表汇总了您可能拥有的不同设置以及所使用的 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="8c82e-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="8c82e-112">**已定位用户帐户**</span><span class="sxs-lookup"><span data-stu-id="8c82e-112">**User account is located**</span></span> <br/> |<span data-ttu-id="8c82e-113">**已配置虚 URL 或存在专用组织**</span><span class="sxs-lookup"><span data-stu-id="8c82e-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="8c82e-114">**Skype for Business 还是 Lync 体验？**</span><span class="sxs-lookup"><span data-stu-id="8c82e-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="8c82e-115">Online</span><span class="sxs-lookup"><span data-stu-id="8c82e-115">Online</span></span>  <br/> |<span data-ttu-id="8c82e-116">否</span><span class="sxs-lookup"><span data-stu-id="8c82e-116">No</span></span>  <br/> |<span data-ttu-id="8c82e-117">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-118">Online</span><span class="sxs-lookup"><span data-stu-id="8c82e-118">Online</span></span>  <br/> |<span data-ttu-id="8c82e-119">是</span><span class="sxs-lookup"><span data-stu-id="8c82e-119">Yes</span></span>  <br/> |<span data-ttu-id="8c82e-120">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-121">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="8c82e-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="8c82e-122">否</span><span class="sxs-lookup"><span data-stu-id="8c82e-122">No</span></span>  <br/> |<span data-ttu-id="8c82e-123">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-124">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="8c82e-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="8c82e-125">是</span><span class="sxs-lookup"><span data-stu-id="8c82e-125">Yes</span></span>  <br/> |<span data-ttu-id="8c82e-126">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-127">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="8c82e-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="8c82e-128">否</span><span class="sxs-lookup"><span data-stu-id="8c82e-128">No</span></span>  <br/> |<span data-ttu-id="8c82e-129">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-130">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="8c82e-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="8c82e-131">是</span><span class="sxs-lookup"><span data-stu-id="8c82e-131">Yes</span></span>  <br/> |<span data-ttu-id="8c82e-132">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-133">纯本地</span><span class="sxs-lookup"><span data-stu-id="8c82e-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="8c82e-134">否</span><span class="sxs-lookup"><span data-stu-id="8c82e-134">No</span></span>  <br/> |<span data-ttu-id="8c82e-135">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="8c82e-136">纯本地</span><span class="sxs-lookup"><span data-stu-id="8c82e-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="8c82e-137">是</span><span class="sxs-lookup"><span data-stu-id="8c82e-137">Yes</span></span>  <br/> |<span data-ttu-id="8c82e-138">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="8c82e-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="8c82e-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="8c82e-139">Related topics</span></span>
[<span data-ttu-id="8c82e-140">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8c82e-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8c82e-141">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="8c82e-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
