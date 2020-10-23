---
title: 打开或关闭移动电话通知
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 2de47013-4f09-493c-abc5-372f56ad69e3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.OrgMobileNotification
description: 了解如何打开或关闭移动电话通知，以便你的用户可以接收有关传入、语音邮件和错过的即时消息的通知。
ms.openlocfilehash: f508c106d2ce2e95d8c7763e3360960beccfc958
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739210"
---
# <a name="turn-on-or-off-mobile-phone-notifications"></a><span data-ttu-id="18550-103">打开或关闭移动电话通知</span><span class="sxs-lookup"><span data-stu-id="18550-103">Turn on or off mobile phone notifications</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18550-104">Microsoft 团队管理中心已将 Skype for Business 管理中心替换 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="18550-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="18550-105">管理 Skype for Business 的所有设置现在均位于团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="18550-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="18550-106">若要了解详细信息，请参阅 [在 Microsoft 团队管理中心中管理 Skype For business 设置](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="18550-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="18550-107">作为你的组织的 **[Microsoft 365 应用中的 "分配管理员" 角色](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** ，你可以选择 Skype for business 用户在其移动电话或平板电脑上时是否收到有关传入和错过的即时消息的通知。</span><span class="sxs-lookup"><span data-stu-id="18550-107">As the **[Assign admin roles in Microsoft 365 Apps for business](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for your organization, you can choose whether your Skype for Business users receive alerts about incoming and missed instant messages when they are on their mobile phones or tablets.</span></span>
  
<span data-ttu-id="18550-p102">在 Android 和 Windows Phone 上，将实时弹出 Skype for Business 通知。但是，在 Windows Phone、iPhone 和 iPad 设备上，当你没有在手机或平板电脑上主动使用 Skype for Business 时，则使用推送通知来显示通知。</span><span class="sxs-lookup"><span data-stu-id="18550-p102">On Android and Windows Phones, Skype for Business notifications pop up in real time. For Windows Phone, iPhone, and iPad devices, however, push notification is used to show the alerts whenever you're not actively using Skype for Business on your phone or tablet.</span></span>
  
## <a name="turn-push-notifications-off-for-all-the-windows-phone-or-apple-devices-in-your-organization"></a><span data-ttu-id="18550-110">在您组织中所有的 Windows Phone 或 Apple 设备上禁用推送通知</span><span class="sxs-lookup"><span data-stu-id="18550-110">Turn push notifications off for all the Windows Phone or Apple devices in your organization</span></span>
<span data-ttu-id="18550-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="18550-111"><a name="__top"> </a></span></span>

<span data-ttu-id="18550-112">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="18550-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="18550-113">登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="18550-113">Sign in to Microsoft 365.</span></span>
    
2. <span data-ttu-id="18550-114">转到 "管理中心" > " **Skype For business**"。</span><span class="sxs-lookup"><span data-stu-id="18550-114">Go to admin center > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18550-115">Go to **Organization** > **General**.</span><span class="sxs-lookup"><span data-stu-id="18550-115">Go to **Organization** > **General**.</span></span> 
    
4. <span data-ttu-id="18550-116">在" **移动电话通知**"下，取消选中要禁用的通知服务旁边的框，然后单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="18550-116">Under **Mobile phone notifications**, clear the box next to the notification service you want to disable, and then click **Save**.</span></span>
    
<span data-ttu-id="18550-117">请注意：</span><span class="sxs-lookup"><span data-stu-id="18550-117">Keep in mind:</span></span> 
  
- <span data-ttu-id="18550-118">如果你关闭推送通知，则当用户在移动设备上重新启动 Skype for Business 时，仍会收到所有通知。</span><span class="sxs-lookup"><span data-stu-id="18550-118">If you turn off push notifications, users still receive all alerts when they start up Skype for Business again on their mobile device.</span></span>
    
- <span data-ttu-id="18550-p103">推送通知在默认情况下处于打开状态。个人用户可通过在其移动设备上选择相应的 Skype for Business 选项来将其关闭。</span><span class="sxs-lookup"><span data-stu-id="18550-p103">Push notifications are turned on by default. Individual users can turn them off by choosing the appropriate Skype for Business option on their mobile device.</span></span>
    
- <span data-ttu-id="18550-121">当关闭推送通知时，用户将无法再打开推送通知。</span><span class="sxs-lookup"><span data-stu-id="18550-121">When you turn off push notifications, users can't turn them back on.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="18550-122">[!重要信息] Microsoft 通过其他公司为 Windows Phone、iPhone 和 iPad 用户提供实时的 Skype for Business 移动电话通知。</span><span class="sxs-lookup"><span data-stu-id="18550-122">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="18550-123">请参阅 [Microsoft Skype For Business 产品的隐私声明](https://go.microsoft.com/fwlink/p/?linkid=247732)。</span><span class="sxs-lookup"><span data-stu-id="18550-123">See the [Privacy Statement for Microsoft Skype for Business Products](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="18550-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="18550-124">Related topics</span></span>

[<span data-ttu-id="18550-125">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="18550-125">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
