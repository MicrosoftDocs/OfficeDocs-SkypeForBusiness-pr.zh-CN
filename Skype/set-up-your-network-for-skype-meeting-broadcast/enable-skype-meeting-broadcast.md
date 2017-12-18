---
title: "启用 Skype 会议直播"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "在您的组织中的人员可以使用Skype 会议广播之前，您需要启用它。若要执行此操作，您需要知道如何使用 Windows PowerShell。如果您不知道 Windows PowerShell，请考虑招聘Microsoft 合作伙伴为您执行此步骤。"
---

# 启用 Skype 会议直播

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
在您的组织中的人员可以使用Skype 会议广播之前，您需要启用它。若要执行此操作，您需要知道如何使用 Windows PowerShell。如果您不知道 Windows PowerShell，请考虑招聘[Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为您执行此步骤。
  
> [!CAUTION]
> Skype 会议广播处于关闭状态默认情况下因为媒体内容的广播会议的通讯组使用 Microsoft Azure 内容交付网络 (CDN) 来实现支持数千个观看广播人员非常高缩放比例。 通过 CDN 分块的媒体内容已加密，并且 CDN 缓存有生命周期有限。 此外，Azure CDN 组件可能不尚未满足因欧盟数据保护指令欧盟模型子句中的所有元素。通过启用此功能，您同意本声明。 
  
## 使用 Skype for Business 管理中心启用 Skype 会议直播

1. 使用 Office 365 全局管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。
    
2. 在 Office 365 管理中心，转到" **管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**中，转到 **联机会议**> **广播会议**，并 **启用 Skype 会议直播**然后选择。
    
## 使用 PowerShell 启用 Skype 会议直播

1. 验证你运行的是 Windows PowerShell 的版本 3.0 或更高版本。
    
1. 要验证你运行的是否是版本 3.0 或更高版本： **"开始"菜单** >" **Windows PowerShell**"。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问 Microsoft 下载中心，从[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
2. 在 **开始菜单**中，选择 **Windows PowerShell**。
    
3. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
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

    您可以确认通过再次运行 `Get-CsBroadcastMeetingConfiguration`启用了设置。
    
     ![Skype 会议直播启用组织 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 更改后，可能需要长达一小时才能在 Skype 会议广播门户中生效。 
  
6. 您的用户现在可以在您的企业容纳直播的会议与其他用户。要获取它们开始，请指导他们到[什么是 Skype 会议直播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## 配置网络以便让外部与会者参加直播会议

如果你装有防火墙，并希望与贵企业外部的人员（不是来自联盟企业）召开直播会议，则需要按照以下说明配置你的网络：[设置 Skype 会议直播网络](set-up-your-network-for-skype-meeting-broadcast.md)。
  
如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。
  
若要跳过此步骤，并改为将另一个业务添加到您的联合身份验证，请参阅[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

