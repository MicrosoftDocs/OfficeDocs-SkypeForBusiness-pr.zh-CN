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
ms.openlocfilehash: 20d3671beb608413c5d0d61f599f65a47b55732d
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753427"
---
# <a name="enable-skype-meeting-broadcast"></a>启用 Skype 会议直播

> [!IMPORTANT]
> Microsoft 团队管理中心已将 Skype for Business 管理中心替换 (旧版门户) 。 管理 Skype for Business 的所有设置现在均位于团队管理中心。 你必须分配有全局管理员或 Skype for Business 管理员的 [AZURE AD 管理员角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能在团队管理中心中管理 Skype for business 功能。 有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。

在组织中的人员可以使用 Skype 会议直播之前，您需要启用它。 若要执行此操作，您需要了解如何使用 Windows PowerShell。 如果你不了解 Windows PowerShell，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>使用 Skype for Business 管理中心启用 Skype 会议直播

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 在上用全局管理员帐户或 Skype for business 管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。
    
2. 在管理中心，转到 "**管理中心**"  >  **团队**。
    
3. 在 "**团队管理中心**" 中，转到 "**旧版门户**"  >  **联机会议**  >  "**广播会议**"，然后选择 "**启用 Skype 会议直播**"。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>使用 PowerShell 启用 Skype 会议直播

1. 验证你运行的是 Windows PowerShell 的版本 3.0 或更高版本。
    
2. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
3. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
4. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。 请参阅 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 windows PowerShell 并将其更新到版本4.0。 出现提示时，请重启计算机。
    
5. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
6. 从 " **开始" 菜单**中，选择 " **Windows PowerShell**"。
    
7. 在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 通过运行以下命令确认当前的 Skype 会议广播配置：
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    验证参数  _EnableBroadcastMeeting_ 设置为 `False`。
    
     ![Skype 会议直播启用组织 cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 通过运行以下命令为你的组织启用 Skype 会议广播：
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    你可以通过再次运行来确认是否启用了该设置  `Get-CsBroadcastMeetingConfiguration` 。
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > [!提示] 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。 
  
10. 现在，你的用户可以与贵企业中的其他用户举行直播会议。要让他们了解如何开始，请指示他们参考[什么是 Skype 会议直播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>配置网络以便让外部与会者参加直播会议

如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。 
  
如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。
  
要跳过此步骤，改为将其他企业添加为你的联盟企业，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>相关主题

[Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
