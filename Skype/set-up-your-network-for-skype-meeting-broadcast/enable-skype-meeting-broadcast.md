---
title: "启用 Skype 会议直播"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: "您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。 若要执行此操作，您需要了解如何使用 Windows PowerShell。 如果你不了解 Windows PowerShell，请考虑聘用 Microsoft 合作伙伴为你执行此步骤。"
ms.openlocfilehash: 3748ca75efcaed479e27fe253c5b3a8399e381d6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="7a37a-105">启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="7a37a-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="7a37a-106">您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。</span><span class="sxs-lookup"><span data-stu-id="7a37a-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="7a37a-107">若要执行此操作，您需要了解如何使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7a37a-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="7a37a-108">如果你不了解 Windows PowerShell，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="7a37a-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7a37a-p103">因为广播会议的媒体内容分发使用 Microsoft Azure 内容传递网络 (CDN)，以达到非常高的比例，支持数千个用户观看广播，Skype 会议广播默认情况下已关闭中。通过 CDN 的分块的媒体内容进行加密，然后 CDN 缓存具有有限的寿命。此外，Azure CDN 组件可能不尚未满足欧盟模型子句而造成的欧盟数据保护指令中的所有元素。启用此功能后，您同意本声明。</span><span class="sxs-lookup"><span data-stu-id="7a37a-p103">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast. The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime. Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive. By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="7a37a-113">使用 Skype for Business 管理中心启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="7a37a-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="7a37a-114">使用 Office 365 全局管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="7a37a-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="7a37a-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="7a37a-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7a37a-116">在**Skype 的业务管理中心**，转到**联机会议** > **广播会议**，然后选择**启用 Skype 会议广播**。</span><span class="sxs-lookup"><span data-stu-id="7a37a-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="7a37a-117">使用 PowerShell 启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="7a37a-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="7a37a-118">验证你运行的是 Windows PowerShell 的版本 3.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7a37a-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="7a37a-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a37a-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="7a37a-120">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="7a37a-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="7a37a-p104">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="7a37a-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="7a37a-p105">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="7a37a-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="7a37a-127">从**开始菜单**中，选择**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="7a37a-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="7a37a-128">在" **Windows PowerShell**"窗口，通过运行以下命令连接到你的 Office 365 组织：</span><span class="sxs-lookup"><span data-stu-id="7a37a-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="7a37a-129">通过运行以下命令确认当前的 Skype 会议广播配置：</span><span class="sxs-lookup"><span data-stu-id="7a37a-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="7a37a-130">验证参数  _EnableBroadcastMeeting_ 设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="7a37a-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 会议直播启用组织 cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="7a37a-132">通过运行以下命令为你的组织启用 Skype 会议广播：</span><span class="sxs-lookup"><span data-stu-id="7a37a-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="7a37a-133">您可以确认该设置是否启用了通过运行`Get-CsBroadcastMeetingConfiguration`再次。</span><span class="sxs-lookup"><span data-stu-id="7a37a-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="7a37a-135">[!提示] 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。</span><span class="sxs-lookup"><span data-stu-id="7a37a-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="7a37a-p106">现在，你的用户可以与贵企业中的其他用户举行直播会议。要让他们了解如何开始，请指示他们参考[什么是 Skype 会议直播？](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="7a37a-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="7a37a-138">配置网络以便让外部与会者参加直播会议</span><span class="sxs-lookup"><span data-stu-id="7a37a-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="7a37a-139">如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="7a37a-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="7a37a-140">如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="7a37a-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="7a37a-141">要跳过此步骤，改为将其他企业添加为你的联盟企业，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7a37a-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7a37a-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="7a37a-142">Related topics</span></span>

[<span data-ttu-id="7a37a-143">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="7a37a-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="7a37a-144">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a37a-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

