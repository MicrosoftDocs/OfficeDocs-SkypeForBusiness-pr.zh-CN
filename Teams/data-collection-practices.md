---
title: 数据收集做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 了解 Microsoft 如何收集人口普查、使用率和错误数据，以了解 Teams 和 Skype for Business 的使用情况和问题，以便计划产品改进。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651222"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype for Business 和 Microsoft Teams 数据收集做法

Skype for Business Server 和 Skype for Business Online 以及 Skype for Business 和 Microsoft Teams 应用程序收集数据，帮助 Microsoft 了解这些产品的使用方式以及发生了哪些类型的错误，例如登录错误。 此信息可帮助我们了解使用模式、计划新功能，以及诊断和解决问题区域。

虽然某些使用率数据是自动收集的，但其他数据只能在管理员和/或用户选择允许时收集。 数据收集分为以下三类：

- 人口普查数据

- 使用率数据

- 错误报告数据

## <a name="census-data"></a>人口普查数据

获取人口普查数据完全是为了提供、支持和改进 Skype for Business。 Microsoft Teams 和 Skype for Business Online。 它包括环境信息，如设备和操作系统版本，以及区域和语言设置。 它还包括用于登录尝试和失败的计数器。 以下是收集的人口普查数据的一些具体示例：

|**数据类型**|**示例**|**注释**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |这个 ID 被散列两次：一次在客户端上，一次在遥测服务上。 散列可确保 ID 无法链接到特定用户。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |设备 ID 是在设备上随机生成一次并发送到遥测服务的 GUID。  <br/> |

人口普查数据不包含任何标识你的组织或用户的信息。 有关详细信息，请参阅 [Skype for Business 隐私声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。

人口普查数据在默认情况下处于打开状态，管理员或最终用户无法将其关闭。

## <a name="usage-data"></a>使用率数据

使用率数据包括诸如呼叫次数、发送或接收的即时消息数量、加入的会议数量、使用的功能的频率以及稳定性问题等信息。

使用率数据中可能包含标识你的组织的信息，如 contoso.com。 以下是收集的使用率数据的一些具体示例：

|**数据类型**|**示例**|**注释**|
|:-----|:-----|:-----|
|发送的即时消息  <br/> |12  <br/> ||
|已接收即时消息  <br/> |5  <br/> ||
|加入会议（尝试）  <br/> |5  <br/> ||
|加入会议（成功）  <br/> |4  <br/> ||
|通话/会议纪要  <br/> |30 分钟  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |这是在 Office 365 中注册的组织的名称，以明文形式传输，这意味着它没有被模糊处理。  <br/> |

使用率数据不包含任何标识用户的信息。

默认情况下，使用率数据收集处于打开状态，但本地管理员可以使用 Skype for Business Server 上的 DisableAutomaticSendTracing 组策略设置将其关闭。 关闭此设置将影响组织中的所有用户。 有关详细信息，请参阅[配置客户端引导策略](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。

最终用户无法启用或禁用使用率数据收集。

对于 Skype 会议应用程序和 Join Launcher 网页，控制遥测的方法是通过以下策略：

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

此策略默认为 false，因此默认情况下遥测收集处于关闭状态。 此设置为每个池，并控制将 Skype 会议应用程序连接到该服务器上主持的会议的所有用户。

## <a name="error-reporting-data"></a>错误报告数据

错误报告数据可包含有关性能和可靠性、设备配置、网络连接质量、错误代码、错误日志和异常的信息。 以下是收集的错误报告数据的一些具体示例：

|**数据类型**|**示例**|**注释**|
|:-----|:-----|:-----|
|消息方向  <br/> |传入  <br/> ||
|对话状态  <br/> |空闲  <br/> ||
|对话线程 ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |ID 以明文形式发送，遥测服务在存储它之前对其进行哈希处理  <br/> |

错误报告数据还可能包含个人身份信息，例如用户的 IP 地址和会话初始协议统一资源标识符 (SIP URI)。 有关所收集内容的详细说明，请参阅 [Skype for Business 隐私声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。

错误报告需要两个事项：

- 在服务器或租户管理中心中，DisableAutomaticSendTracing 组策略设置设置为False（这是默认状态）。 有关详细信息，请参阅[配置客户端引导策略](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。
    
- 最终用户从 Skype for Business 客户端的“常规”选项卡（单击齿轮图标![代表齿轮的图标](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)，然后“**选项**”对话框打开并显示“**常规**”选项卡）单独选择加入。
    
 
![“选项”对话框中“数据收集”复选框的屏幕截图](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
对于 Skype 会议应用，MeetingUxEnableTelemetry 还控制错误报告，不过对于 Windows 上崩溃，Watson 设置控制上传崩溃信息。 Skype 会议应用程序没有你在“桌面客户端”对话框中看到的用户设置。

有关详细信息，请参阅 [在 Skype for Business 中设置常规选项](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。

你可以参阅[为 Skype for Business Online 设置网络](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)以设置网络。

如果您在中国使用由世纪互联运营的 Microsoft 365 或 Office 365，请参阅[为世纪互联运营的 Skype for Business Online 设置网络](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。

## <a name="related-topics"></a>相关主题
[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
