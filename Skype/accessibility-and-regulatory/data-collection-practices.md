---
title: "Skype for Business 和 Microsoft 团队数据收集实践"
ms.author: tonysmit
author: tonysmit
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
description: "Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements."
---

# Skype for Business 和 Microsoft 团队数据收集实践

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](c17e8ea6-b83b-4345-9401-47a6c8b13aad.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/c17e8ea6-b83b-4345-9401-47a6c8b13aad) 中查找本文的英文版本以便参考。
  
Skype for Business Server 2015、 Skype for Business Online和Skype for Business客户端收集数据来帮助了解如何使用这些产品和发生了哪些类型的错误，请登录错误，例如 Microsoft。此信息可以帮助我们了解使用模式、 计划新功能，和故障排除和解决问题的区域。
  
一些使用情况数据是自动收集的，而其他数据只在管理员和/或用户选择允许的情况下收集。 数据收集分为以下三个类别： 
  
- 人口普查数据
    
- 使用情况数据
    
- 错误报告数据
    
## 人口普查数据

人口数据收购只是为了提供、 支持和改进Skype for Business和Skype for Business Online。包括环境的信息，如设备和操作系统版本以及区域和语言设置。它还包括计数器登录尝试和失败。下面是收集的人口数据的一些特定示例：
  
|
|
|****数据类型****|****示例****|****说明****|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |对 ID 执行哈希操作两次：客户端上一次，遥测服务上一次。 哈希操作可确保 ID 不会链接到特定用户。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |设备 ID 是随机生成一次在设备上并发送到遥测服务 GUID。  <br/> |
   
人口数据不包含任何标识您组织或多个用户的信息。请参阅[Skype for Business 隐私声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的详细信息。
  
人口普查数据默认情况下处于启用状态，管理员或最终用户无法关闭。
  
## 使用情况数据

使用情况数据包括进行的呼叫数、已发送或接收的即时消息数、加入的会议数、使用功能的频率和稳定性问题等信息。
  
使用情况数据可能包含可识别你的组织的信息，例如 contoso.com。 以下是收集的使用情况数据的一些具体示例：
  
|
|
|****数据类型****|****示例****|****说明****|
|:-----|:-----|:-----|
|发送即时消息  <br/> |12  <br/> ||
|接收即时消息  <br/> |5  <br/> ||
|加入会议（尝试）  <br/> |5  <br/> ||
|加入会议（成功）  <br/> |4  <br/> ||
|呼叫/会议分钟数  <br/> |30 分钟  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |这是在 Office 365 中注册的组织的名称，以明文方式传输，这意味着不会产生混淆。  <br/> |
   
使用情况数据不包含任何可识别用户的身份的信息。
  
使用率数据集默认情况下，但本地管理员可以将其关闭上Skype for Business Server 2015使用 DisableAutomaticSendTracing 组策略设置。关闭此设置将影响组织中的所有用户。有关详细信息，请参阅[在 Skype for Business Server 2015 配置引导的客户端策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx) 。
  
打开或关闭，最终用户不能启用使用率数据集。
  
有关 Skype 会议应用程序和加入启动器网页，控制遥测的方法是通过此策略：
  
设置 CsWebServiceConfiguration MeetingUxEnableTelemetry $True
  
此策略的默认为 false，以便遥测集默认已关闭。 此设置为每个池和控件的所有用户使用 Skype 会议应用程序连接到该服务器上承载会议。
  
## 错误报告数据

错误报告数据可以包括有关性能和可靠性、设备配置、网络连接质量、错误代码、错误日志和异常的信息。 以下是收集的错误报告数据的一些具体示例：
  
|
|
|****数据类型****|****示例****||
|:-----|:-----|:-----|
|消息方向  <br/> |传入  <br/> ||
|对话状态  <br/> |空闲  <br/> ||
|对话线程 ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> ||ID 以明文形式发送，遥测服务会在存储它之前对其执行哈希操作  <br/> |
   
错误报告数据可能还包含个人身份信息，如用户的 IP 地址和会话初始协议统一资源标识符 (SIP URI)。请参阅[Skype for Business 隐私声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)有关收集哪些信息的详细说明。
  
错误报告需要两个操作： 
  
- DisableAutomaticSendTracing组策略设置将设置为False在服务器上或在租户管理中心 （这是默认状态）。有关详细信息，请参阅[在 Skype for Business Server 2015 配置引导的客户端策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx) 。
    
- 最终用户分别选择常规选项卡 （单击齿轮图标和选项对话框将打开，其中显示常规选项卡） 从Skype for Business客户端中。
    
     ![齿轮图标](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Skype 会议应用程序，MeetingUxEnableTelemetry 还控制错误报告，虽然 Watson 设置为在 Windows 上崩溃，控制上载崩溃信息。 像您看到桌面客户端对话框中，则没有 Skype 会议应用程序的用户设置。
  
有关详细信息，请参阅[在 Skype for Business 中设置"常规"选项](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。
  
你可以查看[为 Skype for Business Online 设置网络](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)以设置你的网络。
  
如果你正在中国使用由世纪互联运营的 Office 365，请参阅[为由世纪互联运营的 Skype for Business Online 设置网络](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。
  
## 相关主题

[客户体验改善计划](https://www.microsoft.com/products/ceip/en-US/default.mspx)
  
[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

