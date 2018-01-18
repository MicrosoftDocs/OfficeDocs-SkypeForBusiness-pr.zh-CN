---
title: "Outlook 网页版中的 Skype for Business Online 支持"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "在 Office 365 (Outlook Web App) 网站上的 outlook 从导航栏提供基本 Skype 业务 web 客户端。 此基本客户端仅供联机用户的管理尚未配置 Office 365 组织的虚荣 URL。 只要用户帐户处于联机状态，并且没有一个虚荣的 URL，他们仍会看到体验，即使其组织内部部署穴的某些用户帐户。 具有用户帐户内部 （是否有虚荣 URL 或不） 或由 Microsoft 管理的用户会看到 Outlook web 应用程序中的 Lync 体验。"
ms.openlocfilehash: 8688123f0e19a648dae7706dc346a647ecd99211
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="d9f24-106">Outlook 网页版中的 Skype for Business Online 支持</span><span class="sxs-lookup"><span data-stu-id="d9f24-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="d9f24-107">在 Office 365 (Outlook Web App) 网站上的 outlook 从导航栏提供基本 Skype 业务 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="d9f24-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="d9f24-108">此基本客户端仅供联机用户的管理尚未配置 Office 365 组织的虚荣 URL。</span><span class="sxs-lookup"><span data-stu-id="d9f24-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="d9f24-109">只要用户帐户处于联机状态，并且没有一个虚荣的 URL，他们仍会看到体验，即使其组织内部部署穴的某些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d9f24-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="d9f24-110">具有用户帐户内部 （是否有虚荣 URL 或不） 或由 Microsoft 管理的用户会看到 Outlook web 应用程序中的 Lync 体验。</span><span class="sxs-lookup"><span data-stu-id="d9f24-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="d9f24-111">下表总结了不同的设置，可能会遇到和使用 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="d9f24-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d9f24-112">**已定位用户帐户**</span><span class="sxs-lookup"><span data-stu-id="d9f24-112">**User account is located**</span></span> <br/> |<span data-ttu-id="d9f24-113">**已配置虚 URL 或存在专用组织**</span><span class="sxs-lookup"><span data-stu-id="d9f24-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="d9f24-114">**Skype for Business 还是 Lync 体验？**</span><span class="sxs-lookup"><span data-stu-id="d9f24-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="d9f24-115">Online</span><span class="sxs-lookup"><span data-stu-id="d9f24-115">Online</span></span>  <br/> |<span data-ttu-id="d9f24-116">否</span><span class="sxs-lookup"><span data-stu-id="d9f24-116">No</span></span>  <br/> |<span data-ttu-id="d9f24-117">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-118">Online</span><span class="sxs-lookup"><span data-stu-id="d9f24-118">Online</span></span>  <br/> |<span data-ttu-id="d9f24-119">是</span><span class="sxs-lookup"><span data-stu-id="d9f24-119">Yes</span></span>  <br/> |<span data-ttu-id="d9f24-120">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-121">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="d9f24-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d9f24-122">否</span><span class="sxs-lookup"><span data-stu-id="d9f24-122">No</span></span>  <br/> |<span data-ttu-id="d9f24-123">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-124">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="d9f24-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d9f24-125">是</span><span class="sxs-lookup"><span data-stu-id="d9f24-125">Yes</span></span>  <br/> |<span data-ttu-id="d9f24-126">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-127">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="d9f24-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d9f24-128">否</span><span class="sxs-lookup"><span data-stu-id="d9f24-128">No</span></span>  <br/> |<span data-ttu-id="d9f24-129">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-130">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="d9f24-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d9f24-131">是</span><span class="sxs-lookup"><span data-stu-id="d9f24-131">Yes</span></span>  <br/> |<span data-ttu-id="d9f24-132">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-133">在 prem 纯</span><span class="sxs-lookup"><span data-stu-id="d9f24-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="d9f24-134">否</span><span class="sxs-lookup"><span data-stu-id="d9f24-134">No</span></span>  <br/> |<span data-ttu-id="d9f24-135">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d9f24-136">在 prem 纯</span><span class="sxs-lookup"><span data-stu-id="d9f24-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="d9f24-137">是</span><span class="sxs-lookup"><span data-stu-id="d9f24-137">Yes</span></span>  <br/> |<span data-ttu-id="d9f24-138">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="d9f24-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="d9f24-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="d9f24-139">Related topics</span></span>
[<span data-ttu-id="d9f24-140">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d9f24-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d9f24-141">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="d9f24-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)