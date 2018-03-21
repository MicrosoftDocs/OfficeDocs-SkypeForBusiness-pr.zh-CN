---
title: "数据集合的做法"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: 
description: "Microsoft 收集人口普查、 用法和错误的数据，了解如何使用 Skype 业务和用户遇到问题的地方。 数据用于产品的改进计划。"
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype 业务和 Microsoft 小组数据集合做法

Skype 的业务服务器 2015年、 Skype 业务在线，Skype 业务和 Microsoft 小组应用程序以及收集数据以帮助 Microsoft 了解这些产品的使用方式和发生何种错误，例如登录错误。 此信息可以帮助我们了解使用模式、 规划新的功能，并排除和解决问题的区域。
  
虽然会自动收集一些有用的数据，可以只收集其他数据时管理和/或用户选择允许它。 数据收集落在这三个类别：
  
- 人口普查数据
    
- 使用率数据
    
- 错误报告数据
    
## <a name="census-data"></a>人口普查数据

人口普查数据获得只是为了提供、 支持和提高业务的 Skype。 Microsoft 的小组和 Skype 的在线业务。 它包括环境信息，如设备和操作系统版本以及区域和语言设置。 它还包括登录尝试和失败的计数器。 人口普查数据收集的特定示例如下：

|**数据类型**|**示例**|**说明**|
|:-----|:-----|:-----|
|应用程序名  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|用户 Id  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |ID 进行哈希计算两次： 一次客户端上，再次对遥测服务。 哈希可确保该 ID 不能链接到特定的用户。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |设备 ID 是随机生成一次设备上并发送到遥测服务的 GUID。  <br/> |
   
人口普查数据不包含任何信息可用于标识您的组织或用户。 [Skype 业务隐私声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的详细信息，请参阅。
  
人口普查数据默认是打开的并且不能由管理员或最终用户关闭。
  
## <a name="usage-data"></a>使用率数据

使用率数据包括调用次数、 发送或接收即时消息的数量、 加入会议的数量、 频率使用，功能和稳定性问题等信息。
  
使用率数据可能包含的信息可用于标识您的组织，如 contoso.com。下面是收集使用数据的一些特定示例：
  
|**数据类型**|**示例**|**说明**|
|:-----|:-----|:-----|
|发送即时消息  <br/> |12  <br/> ||
|收到的即时消息  <br/> |5  <br/> ||
|加入会议 （尝试）  <br/> |5  <br/> ||
|加入会议 （成功）  <br/> |4  <br/> ||
|调用/会议纪要  <br/> |30 分钟  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |这是在 Office 365 中注册的组织名称和传输以明文形式，这意味着它不进行模糊处理。  <br/> |
   
使用率数据不包含任何标识用户的信息。
  
使用率数据集在默认情况下，但内部部署的管理员可以将其关闭业务服务器 2015年在 Skype 上使用 DisableAutomaticSendTracing 组策略设置。 关闭此设置会影响组织中的所有用户。 有关更多信息，请参见[配置客户端中业务服务器 2015年的 Skype 的引导策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx)。
  
最终用户不能启用使用率数据集合打开或关闭。
  
Skype 会议应用程序和连接的启动器 web 页，控制遥测的方法是通过此策略：
  
一组 CsWebServiceConfiguration MeetingUxEnableTelemetry $True
  
此策略的默认为 false，因此遥测集合，默认情况下处于关闭状态。 此设置是每个池，并控制所有用户都使用 Skype 会议应用程序连接到该服务器上主持会议。
  
## <a name="error-reporting-data"></a>错误报告数据

错误报告数据可以包括性能和可靠性、 设备配置、 网络连接质量、 错误代码、 错误日志和异常有关的信息。 下面是错误的一些特定报告收集的数据示例：

|**数据类型**|**示例**|**说明**|
|:-----|:-----|:-----|
|消息传送方向  <br/> |传入  <br/> ||
|会话状态  <br/> |空闲  <br/> ||
|对话线程 ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|用户 Id  <br/> |amosmarble <br/> |该 ID 发送明文，遥测服务前将其进行哈希处理中  <br/> |
   
错误报告数据还可能包含个人身份信息，例如用户的 IP 地址和会话初始化协议统一资源标识符 (SIP URI)。 [Skype 业务隐私声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)的什么收集的详细说明，请参阅。
  
错误报告要求以下两点：
  
- 在服务器上或在租户管理中心 （这是默认状态），DisableAutomaticSendTracing 组策略设置被设置为 False。 有关更多信息，请参见[配置客户端中业务服务器 2015年的 Skype 的引导策略](https://technet.microsoft.com/EN-US/library/gg425941.aspx)。
    
- 最终用户分别选择使用从常规选项卡 （单击齿轮图标和选项对话框将打开并显示常规选项卡） 在 Skype 业务客户端。
    
     ![齿轮图标](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype 业务数据收集复选框，在选项 > 常规的对话框](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
对于 Skype 会议应用，MeetingUxEnableTelemetry 还控制错误报告，虽然对 Windows 的崩溃，Watson 设置控制上载的故障信息。 正如您在桌面客户端对话框中看到没有 Skype 会议应用程序的任何用户设置。
  
有关更多信息，请参见[在 Skype 为业务设置常规选项](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。
  
您可以查看[设置的 Skype 的在线业务网络](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)来设置您的网络。
  
如果您使用的 Office 365 的 21Vianet 在中国运行，请参阅[设置业务在线由 21Vianet Skype 的网络](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。
  
## <a name="related-topics"></a>相关主题
[客户体验改善计划](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
