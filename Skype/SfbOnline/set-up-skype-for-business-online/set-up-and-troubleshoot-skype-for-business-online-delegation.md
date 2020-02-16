---
title: Skype for Business Online 委派设置和疑难解答
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
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
- Setup
description: 本文介绍如何设置 Skype for Business Online 委派和疑难解答。 本文提供了有关设置建议、最佳做法和疑难解答步骤的指南。
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010795"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Skype for Business Online 委派设置和疑难解答

本文介绍如何设置 Skype for Business Online 委派和疑难解答。 本文提供了有关设置建议、最佳做法和疑难解答步骤的指南。
  
## <a name="guidelines-and-requirements"></a>指南和要求

### <a name="guidelines-for-delegation"></a>委派指南

设置并让委派正常工作取决于您遵循以下指南：
  
- 您必须使用 Skype for Business 2015 完全客户端和 "最新更新" 或 "Skype for Business 2016 完全客户端"。
    
- 您必须将 Outlook 2013 客户端与最新更新或 Outlook 2016 客户端配合使用。
    
- 确保委托人进行通话和代理人计算机具有一个作为主要或默认配置文件的 Outlook 邮件配置文件。 该邮件配置文件应仅包含一个帐户。
    
- 委托人进行通话的 Skype for business 和代理人应为联机用户。 此外，每个帐户的 Exchange 服务器邮箱都必须同时联机或都是本地的。
    
- 委托人进行通话和代理人应使用相同的 Outlook 主要版本。
    
- 在客户端策略中， **EnableExchangeDelegateSync**属性值应设置为**true** 。 你可以通过在 Skype for Business Online PowerShell 模块中运行**set-csclientpolicy** cmdlet 来验证此设置。
    
- 在不同工作站上，委托人进行通话和代理人必须同时登录到 Skype for Business 和 Outlook。
    
- Skype for Business Online 委派不支持共享邮箱。 这是因为共享邮箱没有**sendonbehalf**访问控制列表（ACL）。
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business 客户端版本支持

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Basic 客户端**| 不支持 |不支持
|**Skype for Business 2015**|支持| 支持|
|**Skype for Business 2016**|支持| 支持|

   
### <a name="licensing-requirements"></a>许可要求

**企业版 E3 许可方案**

|**许可证**|**客户端**|**注释**|
|:-----|:-----|:-----|
|企业版 E3  <br/> |适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 （Skype for Business 2015）  <br/> Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
|企业版 E3 与 Office 365 Phone System + Office 365 xCalling 计划  <br/> |适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 （Skype for Business 2015）  <br/> Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016  <br/> Lync for Mac 2011  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
   
**企业版 E5 许可方案**

|**许可证**|**客户端**|**注释**|
|:-----|:-----|:-----|
|企业版 E5  <br/> |适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 （Skype for Business 2015）。  <br/> Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
|企业版 E5 + Office 365 通话计划  <br/> |Mac 版 Skype for Business 2016  <br/> 适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 （Skype for Business 2015）  <br/> Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016  <br/> Lync for Mac 2011  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>设置和验证委派

若要设置 Skype for Business Online 委派，请按照下列步骤操作：
  
### <a name="for-windows-clients"></a>对于 Windows 客户端

 **"呼叫转接" 选项卡**
  
1. 选择 "**工具** > "**选项** > "**呼叫转接设置**"。
    
2. 选择 **"编辑我的代理人成员"**。
    
3. 选择 "**添加**"，选择要添加的代理人，然后选择 **"确定"**。
    
 **"无呼叫转接" 选项卡**
  
1. 在 Outlook 中，选择 "**文件** > **帐户设置** > "。 "**委派 Access** > **添加**"。
    
2. 找到并添加将成为代理人的人员的姓名。
    
3. 选择 "**日历**" 菜单，然后选择 "**编辑" （可以阅读、创建和修改项目）**。
    
### <a name="for-mac-clients---lync"></a>对于 Mac 客户端-Lync

 **"呼叫转接" 选项卡**
  
- 如果客户端没有 "**呼叫转接**" 选项卡具有 "**编辑我的代理人成员**" 链接，并且委托人进行通话位于 Mac 计算机上，则委托人进行通话必须登录到基于 Windows 的计算机才能设置委派。 这是因为 Mac 客户端无法建立 MAPI 连接，这是建立来自 Outlook 的 Skype for Business 委派的必要条件。
    
### <a name="verify-success"></a>验证成功

如果设置成功，则代理人会看到**你已添加为 < 名称>** 消息的代理人，还会创建 "**我管理的用户组调用**"。 委托人进行通话应看到 "**委派**" 组已创建。
  
> [!NOTE]
> 委派权限通常在安装过程的30分钟内出现。 但是，此过程可能需要长达24小时才能完成。 
  
## <a name="troubleshooting"></a>疑难解答

### <a name="common-issues"></a>常见问题

- > **问题 1**委托人进行通话删除了 Outlook 客户端中的代理人后，该代理人条目会继续出现在 "**管理呼叫**" 组中。
    
  - > **解决方案 1**在 Skype for Business 客户端上，右键单击 "**代理人**" 组中的代理人，然后选择 "**从组中删除**"。
    
- > **问题 2**通过 Outlook 客户端授予代理访问权限后，将不会为代理人显示确认消息和**我管理**的组调用的人员。
    
  - > **解决方案 2**从 Outlook 客户端删除委派，等待大约15分钟进行复制，然后再次添加代理人。
    
### <a name="other-common-issues"></a>其他常见问题

- 如果超过25个代理和25个委托的阈值，则委派将不起作用。
    
- 不支持 Skype for Business 基本客户端。
    
    > [!NOTE]
    > 如果您安装了 Skype for Business 基本客户端，它将删除并中断委派。 
  
- 如果**MAPI 状态**值不**正常**，请确保**SIP**和**SMTP**值匹配。
    
    > [!NOTE]
    > 第一次启动 Skype for Business 和 Outlook 后，MAPI 状态可能需要几分钟才能显示为 **"正常"** 。
  
- 不支持创建安全组和为该安全组添加委派权限。
    
- MAPI 不可用。 请参阅[Skype For business 2016 客户端中的 "MAPI 不可用" 错误](https://support.microsoft.com/help/3147130)。
    
- 无法通过 Skype for Business 客户端访问 Exchange Online 邮箱。 如果出现这种情况，请运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它通过。
    
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
