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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Office 365 中的 Outlook 网页版 (Outlook Web App) 在导航栏中提供基本 Skype for Business Web 客户端。 此基本客户端是可供联机用户其管理员尚未配置其 Office 365 组织的虚拟 URL。 只要用户的帐户处于联机状态并且没有虚拟 URL，他们仍会看到体验，即使其组织有一些都驻留在内部部署的用户帐户。 具有用户帐户的本地 （无论他们已虚拟 URL 或不） 或由 Microsoft 托管的用户将看到 Outlook web app 中的 Lync 体验。
ms.openlocfilehash: 0d98d2490510b54ec0aabd4fefb7ed4137b449b7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237228"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="fe309-106">Outlook 网页版中的 Skype for Business Online 支持</span><span class="sxs-lookup"><span data-stu-id="fe309-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="fe309-107">Office 365 中的 Outlook 网页版 (Outlook Web App) 在导航栏中提供基本 Skype for Business Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="fe309-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="fe309-108">此基本客户端是可供联机用户其管理员尚未配置其 Office 365 组织的虚拟 URL。</span><span class="sxs-lookup"><span data-stu-id="fe309-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="fe309-109">只要用户的帐户处于联机状态并且没有虚拟 URL，他们仍会看到体验，即使其组织有一些都驻留在内部部署的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fe309-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="fe309-110">具有用户帐户的本地 （无论他们已虚拟 URL 或不） 或由 Microsoft 托管的用户将看到 Outlook web app 中的 Lync 体验。</span><span class="sxs-lookup"><span data-stu-id="fe309-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="fe309-111">下表汇总了您可能遇到的不同设置和 web 客户端使用。</span><span class="sxs-lookup"><span data-stu-id="fe309-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="fe309-112">**已定位用户帐户**</span><span class="sxs-lookup"><span data-stu-id="fe309-112">**User account is located**</span></span> <br/> |<span data-ttu-id="fe309-113">**已配置虚 URL 或存在专用组织**</span><span class="sxs-lookup"><span data-stu-id="fe309-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="fe309-114">**Skype for Business 还是 Lync 体验？**</span><span class="sxs-lookup"><span data-stu-id="fe309-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="fe309-115">Online</span><span class="sxs-lookup"><span data-stu-id="fe309-115">Online</span></span>  <br/> |<span data-ttu-id="fe309-116">否</span><span class="sxs-lookup"><span data-stu-id="fe309-116">No</span></span>  <br/> |<span data-ttu-id="fe309-117">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-118">Online</span><span class="sxs-lookup"><span data-stu-id="fe309-118">Online</span></span>  <br/> |<span data-ttu-id="fe309-119">是</span><span class="sxs-lookup"><span data-stu-id="fe309-119">Yes</span></span>  <br/> |<span data-ttu-id="fe309-120">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-121">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="fe309-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="fe309-122">否</span><span class="sxs-lookup"><span data-stu-id="fe309-122">No</span></span>  <br/> |<span data-ttu-id="fe309-123">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-124">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="fe309-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="fe309-125">是</span><span class="sxs-lookup"><span data-stu-id="fe309-125">Yes</span></span>  <br/> |<span data-ttu-id="fe309-126">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-127">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="fe309-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="fe309-128">否</span><span class="sxs-lookup"><span data-stu-id="fe309-128">No</span></span>  <br/> |<span data-ttu-id="fe309-129">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-130">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="fe309-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="fe309-131">是</span><span class="sxs-lookup"><span data-stu-id="fe309-131">Yes</span></span>  <br/> |<span data-ttu-id="fe309-132">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-133">纯 prem 上</span><span class="sxs-lookup"><span data-stu-id="fe309-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="fe309-134">否</span><span class="sxs-lookup"><span data-stu-id="fe309-134">No</span></span>  <br/> |<span data-ttu-id="fe309-135">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="fe309-136">纯 prem 上</span><span class="sxs-lookup"><span data-stu-id="fe309-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="fe309-137">是</span><span class="sxs-lookup"><span data-stu-id="fe309-137">Yes</span></span>  <br/> |<span data-ttu-id="fe309-138">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="fe309-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="fe309-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="fe309-139">Related topics</span></span>
[<span data-ttu-id="fe309-140">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fe309-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fe309-141">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="fe309-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
