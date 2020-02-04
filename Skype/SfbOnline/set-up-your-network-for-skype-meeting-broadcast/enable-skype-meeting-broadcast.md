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
description: 在组织中的人员可以使用 Skype 会议直播之前，您需要启用它。若要执行此操作，您需要了解如何使用 Windows PowerShell。如果不知道 Windows PowerShell，请考虑聘用 Microsoft 合作伙伴来为你执行此步骤。
ms.openlocfilehash: 6ad681972bb62fa1790290a90d4281fe4ccd8571
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692627"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="85183-105">启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="85183-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="85183-p102">在组织中的人员可以使用 Skype 会议直播之前，您需要启用它。若要执行此操作，您需要了解如何使用 Windows PowerShell。如果不知道 Windows PowerShell，请考虑聘用[Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)来为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85183-p102">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it. To do this, you need to know how to use Windows PowerShell. If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="85183-109">使用 Skype for Business 管理中心启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="85183-109">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="85183-110">![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="85183-110">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="85183-111">在处[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)登录 Office 365 全局管理员帐户或 Skype for business 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="85183-111">Sign in with your Office 365 global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="85183-112">在管理中心，转到 "**管理中心** > "**团队**。</span><span class="sxs-lookup"><span data-stu-id="85183-112">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="85183-113">在 "**团队管理中心**" 中，转到 "**旧版门户** > "**联机会议** > "**广播会议**"，然后选择 "**启用 Skype 会议直播**"。</span><span class="sxs-lookup"><span data-stu-id="85183-113">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="85183-114">使用 PowerShell 启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="85183-114">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="85183-115">验证你运行的是 Windows PowerShell 的版本 3.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="85183-115">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="85183-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="85183-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="85183-117">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="85183-117">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="85183-118">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="85183-118">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="85183-119">请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="85183-119">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="85183-120">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="85183-120">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="85183-p104">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="85183-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="85183-124">从 "**开始" 菜单**中，选择 " **Windows PowerShell**"。</span><span class="sxs-lookup"><span data-stu-id="85183-124">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="85183-125">在" **Windows PowerShell**"窗口，通过运行以下命令连接到你的 Office 365 组织：</span><span class="sxs-lookup"><span data-stu-id="85183-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="85183-126">通过运行以下命令确认当前的 Skype 会议广播配置：</span><span class="sxs-lookup"><span data-stu-id="85183-126">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="85183-127">验证参数  _EnableBroadcastMeeting_ 设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="85183-127">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 会议直播启用组织 cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="85183-129">通过运行以下命令为你的组织启用 Skype 会议广播：</span><span class="sxs-lookup"><span data-stu-id="85183-129">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="85183-130">你可以通过再次运行`Get-CsBroadcastMeetingConfiguration`来确认是否启用了该设置。</span><span class="sxs-lookup"><span data-stu-id="85183-130">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="85183-132">[!提示] 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。</span><span class="sxs-lookup"><span data-stu-id="85183-132">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="85183-p105">现在，你的用户可以与贵企业中的其他用户举行直播会议。要让他们了解如何开始，请指示他们参考[什么是 Skype 会议直播？](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="85183-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="85183-135">配置网络以便让外部与会者参加直播会议</span><span class="sxs-lookup"><span data-stu-id="85183-135">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="85183-136">如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="85183-136">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="85183-137">如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85183-137">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="85183-138">要跳过此步骤，改为将其他企业添加为你的联盟企业，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="85183-138">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="85183-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="85183-139">Related topics</span></span>

[<span data-ttu-id="85183-140">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="85183-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="85183-141">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85183-141">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
