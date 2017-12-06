---
title: "设置和疑难解答 Skype for Business Online 委派"
ms.author: tonysmit
author: tonysmit
ms.date: 11/23/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
description: "本文介绍如何设置和疑难解答 Skype for Business Online 委派。本文提供了指南设置建议、 最佳做法和疑难解答步骤。"
---

# 设置和疑难解答 Skype for Business Online 委派

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](e676b911-5f82-41d8-b4ce-3d0d45c3cd04.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/e676b911-5f82-41d8-b4ce-3d0d45c3cd04) 中查找本文的英文版本以便参考。
  
本文介绍如何设置和疑难解答 Skype for Business Online 委派。本文提供了指南设置建议、 最佳做法和疑难解答步骤。
  
## 准则和要求

### 委派的准则

设置和获取委派才能正常取决于您遵循这些准则：
  
- 您必须使用 Skype for Business 2015 及最新更新的完整客户端或 Skype for Business 2016 完整客户端。
    
- 您必须使用 Outlook 2013 客户端使用最新更新或 Outlook 2016 客户端。
    
- 请确保在代理者和代理计算机有一个 Outlook 邮件配置文件的主或默认配置文件。该邮件配置文件应包含只有一个帐户。
    
- Skype for Business 代理者和代理应联机用户。此外，每个帐户必须同时为联机或都是内部部署的 Exchange Server 邮箱。
    
- 代理者和代理人应使用相同的主要版本的 Outlook。
    
- 应将 **EnableExchangeDelegateSync** 属性值设置为 **true** 的客户端策略中。您可以通过在 Skype for Business Online PowerShell 模块中运行 **获取 CSClientPolicy** cmdlet 来验证此设置。
    
- 代理者和代理人必须登录到 Skype for Business 和 Outlook，同时在不同工作站上。
    
- 共享的邮箱不支持 Skype for Business Online 委派。这是因为共享的邮箱没有 **sendonbehalf** 访问控制列表 (ACL)。
    
### Skype for Business 客户端版本支持

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business 基本客户端**|
|:-----|
|**Skype for Business 2015**|
|:-----|
|**Skype for Business 2016**|
|:-----|
   
### 许可要求

**企业版 E3 许可方案**

|****许可证****|****客户端****|****注释****|
|:-----|:-----|:-----|
|企业版 E3  <br/> |Outlook 2013 或 Outlook 2016 与使用 Lync 2013 (Skype for Business 2015)  <br/> Skype for Business 2016 与 Outlook 2013 或 Outlook 2016 使用  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不是会议。  <br/> |
|通过 Office 365 电话系统 + Office 365 xCalling 计划的企业版 E3  <br/> |Outlook 2013 或 Outlook 2016 与使用 Lync 2013 (Skype for Business 2015)  <br/> Skype for Business 2016 与 Outlook 2013 或 Outlook 2016 使用  <br/> Lync for Mac 2011  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不是会议。  <br/> |
   
**企业 E5 许可方案**

|****许可证****|****客户端****|****注释****|
|:-----|:-----|:-----|
|企业版 E5  <br/> |Outlook 2013 或 Outlook 2016 与使用 Lync 2013 (Skype for Business 2015)。  <br/> Skype for Business 2016 与 Outlook 2013 或 Outlook 2016 使用  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不是会议。  <br/> |
|企业 E5 以及 Office 365 呼叫计划  <br/> |Skype for Business for Mac 2016  <br/> Outlook 2013 或 Outlook 2016 与使用 Lync 2013 (Skype for Business 2015)  <br/> Skype for Business 2016 与 Outlook 2013 或 Outlook 2016 使用  <br/> Lync for Mac 2011  <br/> |Skype for Business 基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不是会议。  <br/> |
   
## 设置和验证委派

若要设置 Skype for Business Online 委派，请按照下列步骤：
  
### 适用于 Windows 客户端

 **呼叫转接选项卡**
  
1. 选择 **工具**> **选项**> **呼叫转接设置**。
    
2. 选择 **编辑我的代理人成员**。
    
3. 选择 **添加**，选择代理人您想要添加，然后选择 **确定**。
    
 **没有呼叫转接选项卡**
  
1. 在 Outlook 中，选择 **文件**> **帐户设置**> **代理访问**> **添加**。
    
2. 找到并添加将成为代理人的人员的名称。
    
3. 选择 **日历** 菜单，然后选择 **编辑器 （可以阅读、 创建和修改项目）**。
    
### 适用于 Mac 客户端-Lync

 **呼叫转接选项卡**
  
- 如果客户端中没有 **呼叫转接**选项卡，包含 **编辑我的代理人成员**链接，并且代理者位于 Mac 计算机上，代理者必须登录到基于 Windows 的计算机以设置委派。这是因为 Mac 客户端无法发出 MAPI 连接，这是建立 Skype for Business 委派从 Outlook 的要求。
    
### 验证成功

如果设置成功，代理应看到 **您已被添加为代理人 < 名称 >** **我管理呼叫的人**组中创建邮件，并显示。 代理者应看到 **代理人**组中创建的。
  
> [!NOTE]
> 委派权限通常出现在安装过程的 30 分钟内。但是，此过程可能需要多达 24 小时才能完成。 
  
## 疑难解答

### 常见问题

> **问题 1** 继续之后代理者已从 Outlook 客户端中删除代理显示在 **我管理呼叫的人** 组中的代理的条目。
    
    **解决方法 1** 在 Skype for Business 客户端，请右键单击代理的 **代理人**组中，，然后选择 **从组中删除**。
    
> **问题 2** 通过 Outlook 客户端，授予代理访问后，确认消息和 **我管理呼叫的人** 组中都不将显示为代理人。
    
    **解决方案 2** 从 Outlook 客户端删除委派，等待大约 15 分钟复制，然后再次添加代理人。
    
### 其他常见的问题

- 如果超出 25 委派人和 25 代理人阈值，委派不起作用。
    
- Skype for Business 基本客户端不支持。
    
    > [!NOTE]
    > 如果您安装 Skype for Business 基本客户端，它将删除，并断开委派。 
  
- 如果 **MAPI 状态** 值不是 **确定** ，请确保 **SIP** 和 **SMTP** 值匹配。
    
    > [!NOTE]
    > 可能需要几分钟时间，MAPI 状态后您首次启动 Skype for Business 和 Outlook 显示为 **确定** 。
  
- 创建安全组和添加委派该安全组的权限不受支持。
    
- MAPI 不可用。请参阅[Skype for Business 2016 客户端中的"MAPI 不可用"错误](https://support.microsoft.com/en-us/help/3147130)。
    
- Exchange Online 邮箱不能通过 Skype for Business 客户端访问。如果发生这种情况，运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它可以通过。
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

