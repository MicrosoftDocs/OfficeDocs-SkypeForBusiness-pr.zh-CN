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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 本文介绍如何设置和 Skype 疑难解答业务联机委派。 本文为您提供了有关安装程序建议、 最佳实践和故障排除步骤指南。
ms.openlocfilehash: 450aee07691a007b976aafffc05d34c3e7ef85f2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237294"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Skype for Business Online 委派设置和疑难解答

本文介绍如何设置和 Skype 疑难解答业务联机委派。 本文为您提供了有关安装程序建议、 最佳实践和故障排除步骤指南。
  
## <a name="guidelines-and-requirements"></a>准则和要求

### <a name="guidelines-for-delegation"></a>委派的指南

设置并获取正常工作的委派取决于您遵循以下准则：
  
- 您必须使用最新的更新业务 2015年完整客户端的 Skype 或 Skype for Business 2016 完整客户端。
    
- 您必须使用 Outlook 2013 客户端使用最新更新或 Outlook 2016 客户端。
    
- 请确保 delegator 和代理计算机上具有一个 Outlook 邮件配置文件的主或的默认配置文件。 该邮件配置文件应包含只有一个帐户。
    
- Skype for Business 的代理者和代理人应联机用户。 此外，每个帐户必须同时 Online 或同时为本地 Exchange 服务器邮箱。
    
- Delegator 和代理人都应使用相同的主要版本的 Outlook。
    
- **EnableExchangeDelegateSync**属性值应设置为**true**的客户端策略。 您可以通过运行中的业务 Online PowerShell 模块 Skype **Get-csclientpolicy** cmdlet 来验证此设置。
    
- Delegator 和代理人必须登录到 Skype 商业和 Outlook 同时在不同的工作站上。
    
- 共享的邮箱不支持 Skype 业务联机委派。 这是因为共享的邮箱不具有**sendonbehalf**访问控制列表 (ACL)。
    
### <a name="skype-for-business-client-version-support"></a>Skype 业务客户端版本支持

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype 业务基本客户端**| 不支持 |不支持
|**Skype for Business 2015**|支持| 支持|
|**Skype 业务 2016 年**|支持| 支持|

   
### <a name="licensing-requirements"></a>许可要求

**企业版 E3 授权方案**

|**许可证**|**客户端**|**注释**|
|:-----|:-----|:-----|
|企业版 E3  <br/> |用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)  <br/> 用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype  <br/> |Skype 业务基本客户端不支持委派。  <br/> Mac 客户端，您可以委派呼叫，但并非会议。  <br/> |
|与 Office 365 电话系统 + Office 365 xCalling 计划的企业版 E3  <br/> |用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)  <br/> 用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype  <br/> Lync for Mac 2011  <br/> |Skype 业务基本客户端不支持委派。  <br/> Mac 客户端，您可以委派呼叫，但并非会议。  <br/> |
   
**企业 E5 授权方案**

|**许可证**|**客户端**|**注释**|
|:-----|:-----|:-----|
|企业 E5  <br/> |用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)。  <br/> 用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype  <br/> |Skype 业务基本客户端不支持委派。  <br/> Mac 客户端，您可以委派呼叫，但并非会议。  <br/> |
|企业 E5 以及 Office 365 呼叫计划  <br/> |Skype for Mac 2016 年 Business  <br/> 用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)  <br/> 用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype  <br/> Lync for Mac 2011  <br/> |Skype 业务基本客户端不支持委派。  <br/> Mac 客户端，您可以委派呼叫，但并非会议。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>设置和验证委派

若要设置 Skype 业务联机委派，请按照下列步骤：
  
### <a name="for-windows-clients"></a>Windows 客户端

 **呼叫转接选项卡**
  
1. 选择**工具** > **选项** > **呼叫转接设置**。
    
2. 选择**编辑我的代理人成员**。
    
3. 选择**添加**，请选择您要添加的代理人，然后选择**确定**。
    
 **没有呼叫转移选项卡**
  
1. 在 Outlook 中，选择**文件** > **帐户设置** > **代理访问** > **添加**。
    
2. 找到并添加要委派的人员的名称。
    
3. 选择**日历**菜单，然后选择**编辑器 （可以读取、 创建和修改的项目）**。
    
### <a name="for-mac-clients---lync"></a>For Mac 客户端的 Lync

 **呼叫转接选项卡**
  
- 如果客户端没有**呼叫转接**选项卡，具有**编辑我的代理人成员**链接，并且 delegator 位于是 Mac 计算机，代理者必须登录到基于 Windows 的计算机才能设置委派。 这是因为 Mac 客户端无法发出 MAPI 连接，这是 Outlook 中的业务委派建立 Skype 的要求。
    
### <a name="verify-success"></a>验证成功

如果成功安装，代理人应该会看到**已将您添加为 < Name> 的代理人**消息并且还创建**我管理呼叫的人员**组中。 Delegator 应看到已创建**代理人**组。
  
> [!NOTE]
> 委派权限通常显示在安装过程的 30 分钟内。 但是，此过程可能需要 24 小时才能完成。 
  
## <a name="troubleshooting"></a>疑难解答

### <a name="common-issues"></a>常见问题

- > **问题 1**该委托条目继续 delegator 已从 Outlook 客户端删除代理人后，出现在**我管理呼叫的人员**组中。
    
  - > **解决方案 1**在业务客户端 Skype，右键单击**代理人**组中的委托，然后选择**从组中删除**。
    
- > **问题 2**代理访问授予通过 Outlook 客户端后，确认消息和**我管理呼叫的人员**组中都不显示该委托。
    
  - > **解决方案 2**从 Outlook 客户端中删除委派和等待 15 分钟的时间进行复制，然后再次添加代理。
    
### <a name="other-common-issues"></a>其他常见的问题

- 如果超过 25 委派人和 25 代理人的阈值，委派不起作用。
    
- 业务基本客户端 Skype 不受支持。
    
    > [!NOTE]
    > 如果您安装 Skype 业务基本客户端，它将删除和中断委派。 
  
- 如果**MAPI**状态值不是**确定**，请确保**SIP**和**SMTP**值匹配。
    
    > [!NOTE]
    > 可能需要几分钟，以便 MAPI 状态后业务和 Outlook 的首次启动 Skype 显示为**确定**。
  
- 创建安全组并添加委派权限的安全组不受支持。
    
- MAPI 不可用。 请参阅[Skype 业务 2016年客户端中的"MAPI 不可用"错误](https://support.microsoft.com/en-us/help/3147130)。
    
- Exchange Online 邮箱不能通过业务客户端 Skype 访问。 如果发生这种情况，运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它可以通过。
    
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
