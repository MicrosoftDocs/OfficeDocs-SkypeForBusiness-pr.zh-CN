---
title: 启用 Skype 会议直播
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 在您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。 为此，你需要了解如何使用Windows PowerShell。 如果你不了解 Windows PowerShell，请考虑聘用 Microsoft 合作伙伴为你执行此步骤。
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237008"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="8da4b-105">启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="8da4b-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="8da4b-106">Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此时将结束对服务的访问。</span><span class="sxs-lookup"><span data-stu-id="8da4b-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="8da4b-107">我们鼓励客户开始升级到 Microsoft Teams（Microsoft 365 中通信和团队合作的核心Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8da4b-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="8da4b-108">在您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。</span><span class="sxs-lookup"><span data-stu-id="8da4b-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="8da4b-109">为此，你需要了解如何使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8da4b-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="8da4b-110">如果你不了解 Windows PowerShell，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="8da4b-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="8da4b-111">Microsoft Teams管理中心已Skype for Business旧版门户 (管理) 。</span><span class="sxs-lookup"><span data-stu-id="8da4b-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="8da4b-112">现在，管理Skype for Business的所有设置都位于Teams中心。</span><span class="sxs-lookup"><span data-stu-id="8da4b-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="8da4b-113">必须分配全局管理员或 Skype for Business 管理员的[Azure AD](/azure/active-directory/roles/permissions-reference)管理员角色Skype for Business管理中心Teams功能。</span><span class="sxs-lookup"><span data-stu-id="8da4b-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="8da4b-114">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="8da4b-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="8da4b-115">使用 Skype for Business 管理中心启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="8da4b-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="8da4b-116">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="8da4b-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="8da4b-117">使用全局管理员帐户登录，或Skype for Business管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="8da4b-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="8da4b-118">在管理中心中，转到"**管理中心**  >  **Teams"。**</span><span class="sxs-lookup"><span data-stu-id="8da4b-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="8da4b-119">在 Teams **管理** 中心，转到"旧门户""联机会议""直播会议"，然后选择"启用Skype 会议  >    >  **广播"。**</span><span class="sxs-lookup"><span data-stu-id="8da4b-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="8da4b-120">使用 PowerShell 启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="8da4b-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="8da4b-121">安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="8da4b-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="8da4b-122">打开Windows PowerShell命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8da4b-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="8da4b-123">通过运行以下命令确认当前的 Skype 会议广播配置：</span><span class="sxs-lookup"><span data-stu-id="8da4b-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="8da4b-124">验证参数  _EnableBroadcastMeeting_ 设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="8da4b-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 会议直播启用组织 cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="8da4b-126">通过运行以下命令为你的组织启用 Skype 会议广播：</span><span class="sxs-lookup"><span data-stu-id="8da4b-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="8da4b-127">可以通过再次运行 来确认设置  `Get-CsBroadcastMeetingConfiguration` 已启用。</span><span class="sxs-lookup"><span data-stu-id="8da4b-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="8da4b-129">[!提示] 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。</span><span class="sxs-lookup"><span data-stu-id="8da4b-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="8da4b-p105">现在，你的用户可以与贵企业中的其他用户举行直播会议。要让他们了解如何开始，请指示他们参考[什么是 Skype 会议直播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="8da4b-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="8da4b-132">配置网络以便让外部与会者参加直播会议</span><span class="sxs-lookup"><span data-stu-id="8da4b-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="8da4b-133">如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="8da4b-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="8da4b-134">如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="8da4b-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="8da4b-135">要跳过此步骤，改为将其他企业添加为你的联盟企业，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="8da4b-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="8da4b-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="8da4b-136">Related topics</span></span>

[<span data-ttu-id="8da4b-137">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="8da4b-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="8da4b-138">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8da4b-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
