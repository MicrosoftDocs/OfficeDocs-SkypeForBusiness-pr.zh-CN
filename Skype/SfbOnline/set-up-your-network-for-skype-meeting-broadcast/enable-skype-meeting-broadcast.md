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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: 您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。 若要执行此操作，您需要知道如何使用 Windows PowerShell。 如果你不了解 Windows PowerShell，请考虑聘用 Microsoft 合作伙伴为你执行此步骤。
ms.openlocfilehash: ba30af3285f7e66f46e771f66132c89d7513852d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850048"
---
# <a name="enable-skype-meeting-broadcast"></a>启用 Skype 会议直播

您的组织中的人员可以使用 Skype 会议广播之前，您需要启用它。 若要执行此操作，您需要知道如何使用 Windows PowerShell。 如果你不了解 Windows PowerShell，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>使用 Skype for Business 管理中心启用 Skype 会议直播

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**

1. 使用 Office 365 全局管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。
    
2. In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.
    
3. 在**Skype 业务管理中心的**中，转到**联机会议** > **广播会议**，并**启用 Skype 会议广播**然后选择。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>使用 PowerShell 启用 Skype 会议直播

1. 验证你运行的是 Windows PowerShell 的版本 3.0 或更高版本。
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
2. 从**开始菜单**中，选择**Windows PowerShell**。
    
3. 在" **Windows PowerShell**"窗口，通过运行以下命令连接到你的 Office 365 组织：
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. 通过运行以下命令确认当前的 Skype 会议广播配置：
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    验证参数  _EnableBroadcastMeeting_ 设置为 `False`。
    
     ![Skype 会议直播启用组织 cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. 通过运行以下命令为你的组织启用 Skype 会议广播：
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    您可以确认是否已设置启用通过运行`Get-CsBroadcastMeetingConfiguration`再次。
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > [!提示] 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。 
  
6. 现在，你的用户可以与贵企业中的其他用户举行直播会议。要让他们了解如何开始，请指示他们参考[什么是 Skype 会议直播？](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>配置网络以便让外部与会者参加直播会议

如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。 
  
如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。
  
要跳过此步骤，改为将其他企业添加为你的联盟企业，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>相关主题

[Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 