---
title: "Outlook 网页版中的 Skype for Business Online 支持"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Office 365 中的 Outlook 网页版 (Outlook Web App) 在导航栏中提供基本 Skype for Business Web 客户端。 此基本客户端仅供联机用户的管理尚未配置 Office 365 组织的虚荣 URL。 只要用户帐户处于联机状态，并且没有一个虚荣的 URL，他们仍会看到体验，即使其组织内部部署穴的某些用户帐户。 具有用户帐户内部 （是否有虚荣 URL 或不） 或由 Microsoft 管理的用户会看到 Outlook web 应用程序中的 Lync 体验。"
ms.openlocfilehash: 153cf2599afdd6961126307ca2b5f88fcff3f6fd
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="dab73-106">Outlook 网页版中的 Skype for Business Online 支持</span><span class="sxs-lookup"><span data-stu-id="dab73-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="dab73-107">Office 365 中的 Outlook 网页版 (Outlook Web App) 在导航栏中提供基本 Skype for Business Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="dab73-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="dab73-108">此基本客户端仅供联机用户的管理尚未配置 Office 365 组织的虚荣 URL。</span><span class="sxs-lookup"><span data-stu-id="dab73-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="dab73-109">只要用户帐户处于联机状态，并且没有一个虚荣的 URL，他们仍会看到体验，即使其组织内部部署穴的某些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="dab73-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="dab73-110">具有用户帐户内部 （是否有虚荣 URL 或不） 或由 Microsoft 管理的用户会看到 Outlook web 应用程序中的 Lync 体验。</span><span class="sxs-lookup"><span data-stu-id="dab73-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="dab73-111">下表总结了不同的设置，可能会遇到和使用 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="dab73-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="dab73-112">**已定位用户帐户**</span><span class="sxs-lookup"><span data-stu-id="dab73-112">**User account is located**</span></span> <br/> |<span data-ttu-id="dab73-113">**已配置虚 URL 或存在专用组织**</span><span class="sxs-lookup"><span data-stu-id="dab73-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="dab73-114">**Skype for Business 还是 Lync 体验？**</span><span class="sxs-lookup"><span data-stu-id="dab73-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="dab73-115">Online</span><span class="sxs-lookup"><span data-stu-id="dab73-115">Online</span></span>  <br/> |<span data-ttu-id="dab73-116">否</span><span class="sxs-lookup"><span data-stu-id="dab73-116">No</span></span>  <br/> |<span data-ttu-id="dab73-117">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-118">Online</span><span class="sxs-lookup"><span data-stu-id="dab73-118">Online</span></span>  <br/> |<span data-ttu-id="dab73-119">是</span><span class="sxs-lookup"><span data-stu-id="dab73-119">Yes</span></span>  <br/> |<span data-ttu-id="dab73-120">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-121">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="dab73-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="dab73-122">否</span><span class="sxs-lookup"><span data-stu-id="dab73-122">No</span></span>  <br/> |<span data-ttu-id="dab73-123">Skype for Business Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-124">混合但联机托管</span><span class="sxs-lookup"><span data-stu-id="dab73-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="dab73-125">是</span><span class="sxs-lookup"><span data-stu-id="dab73-125">Yes</span></span>  <br/> |<span data-ttu-id="dab73-126">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-127">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="dab73-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="dab73-128">否</span><span class="sxs-lookup"><span data-stu-id="dab73-128">No</span></span>  <br/> |<span data-ttu-id="dab73-129">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-130">混合但本地托管</span><span class="sxs-lookup"><span data-stu-id="dab73-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="dab73-131">是</span><span class="sxs-lookup"><span data-stu-id="dab73-131">Yes</span></span>  <br/> |<span data-ttu-id="dab73-132">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-133">在 prem 纯</span><span class="sxs-lookup"><span data-stu-id="dab73-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="dab73-134">否</span><span class="sxs-lookup"><span data-stu-id="dab73-134">No</span></span>  <br/> |<span data-ttu-id="dab73-135">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="dab73-136">在 prem 纯</span><span class="sxs-lookup"><span data-stu-id="dab73-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="dab73-137">是</span><span class="sxs-lookup"><span data-stu-id="dab73-137">Yes</span></span>  <br/> |<span data-ttu-id="dab73-138">Lync Web 体验</span><span class="sxs-lookup"><span data-stu-id="dab73-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="dab73-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="dab73-139">Related topics</span></span>
[<span data-ttu-id="dab73-140">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dab73-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="dab73-141">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="dab73-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="dab73-142">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="dab73-142">Feedback?</span></span>
<span data-ttu-id="dab73-143">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="dab73-143">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>