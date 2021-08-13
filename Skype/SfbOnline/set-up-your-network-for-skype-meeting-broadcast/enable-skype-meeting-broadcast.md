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
ms.openlocfilehash: 99e5464ac092f30edf2667dbfd772b11c41ca4a795893e1e3415a54cf566ee44
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339260"
---
# <a name="enable-skype-meeting-broadcast"></a>启用 Skype 会议直播

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此时将结束对服务的访问。 我们鼓励客户开始升级到 Microsoft Teams（Microsoft 365 中通信和团队合作的核心Microsoft 365。

在您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。 为此，你需要了解如何使用Windows PowerShell。 如果你不了解 Windows PowerShell，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。



> [!NOTE]
> Microsoft Teams管理中心已Skype for Business旧版门户 (管理) 。 现在，管理Skype for Business的所有设置都位于Teams中心。 必须分配全局管理员或 Skype for Business 管理员的[Azure AD](/azure/active-directory/roles/permissions-reference)管理员角色Skype for Business管理中心Teams功能。 有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>使用 Skype for Business 管理中心启用 Skype 会议直播

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 使用全局管理员帐户登录，或Skype for Business管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。
    
2. 在管理中心中，转到"**管理中心**  >  **Teams"。**
    
3. 在 Teams **管理** 中心，转到"旧门户""联机会议""直播会议"，然后选择"启用Skype 会议  >    >  **广播"。**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>使用 PowerShell 启用 Skype 会议直播

1. 安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell命令提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. 通过运行以下命令确认当前的 Skype 会议广播配置：
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    验证参数  _EnableBroadcastMeeting_ 设置为 `False`。
    
     ![Skype 会议直播启用组织 cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 通过运行以下命令为你的组织启用 Skype 会议广播：
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    可以通过再次运行 来确认设置  `Get-CsBroadcastMeetingConfiguration` 已启用。
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > [!提示] 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。 
  
10. 现在，你的用户可以与贵企业中的其他用户举行直播会议。要让他们了解如何开始，请指示他们参考[什么是 Skype 会议直播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>配置网络以便让外部与会者参加直播会议

如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。 
  
如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。
  
要跳过此步骤，改为将其他企业添加为你的联盟企业，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>相关主题

[Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
