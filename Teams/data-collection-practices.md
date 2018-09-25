---
title: 数据收集做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft 收集统计、 使用和错误的数据，以了解如何使用 for Business 的 Skype 和其中用户遇到问题。 使用的数据来规划产品改进。
ms.openlocfilehash: 198c78b2c6b484d3d68c7d001de4d0db12658a2c
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012838"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype 的业务和 Microsoft 团队数据集做法

Skype 的业务服务器 2015年、 业务 online，以及应用程序业务和 Microsoft 团队的 Skype Skype 收集数据以帮助 Microsoft 了解如何使用这些产品以及哪些类型的错误，例如，登录错误发生。 此信息可以帮助我们了解使用模式、 规划新功能，并排除和修复问题的区域。

时自动收集的某些使用率数据，可以仅收集其他数据时的管理和/或用户选择允许它。 数据收集分为以下三个类别：

- 统计数据

- 使用率数据

- 错误报告数据

## <a name="census-data"></a>统计数据

获取统计数据只是为了提供、 支持，以及改进业务的 Skype。 Microsoft 团队和 Skype for Business 联机。 它包括环境的信息，如设备和操作系统版本和区域和语言设置。 它还包括尝试登录时和失败的计数器。 下面是一些特定收集的统计数据的示例：

|**数据类型**|**示例**|**说明**|
|:-----|:-----|:-----|
|应用程序名称  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|用户 Id  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |ID 哈希处理两次： 客户端上一次并再次遥测服务。 哈希值计算可确保不能链接到特定用户的 ID。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |设备 ID 是随机生成一次在设备上并发送到遥测服务的 GUID。  <br/> |

统计数据不包含任何标识您的组织或用户的信息。 请参阅[业务隐私声明的 Skype](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)的详细信息。

统计数据位于默认情况下，不能通过 admins 凭据或最终用户关闭。

## <a name="usage-data"></a>使用率数据

使用率数据包括如进行的呼叫数、 发送或接收 Im 数、 加入的会议数、 的功能使用，频率和稳定性问题的信息。

使用率数据可能包含标识您的组织，例如，contoso.com 的信息。 下面是一些特定收集使用率数据的示例：

|**数据类型**|**示例**|**说明**|
|:-----|:-----|:-----|
|发送的 IM  <br/> |12  <br/> ||
|接收 IM  <br/> |5  <br/> ||
|加入会议 （尝试）  <br/> |5  <br/> ||
|加入会议 （成功）  <br/> |4  <br/> ||
|会议呼叫/分钟  <br/> |30 分钟  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |这是在 Office 365 中注册的组织的名称，以明文，这意味着不经过模糊处理传输。  <br/> |

使用率数据不包含任何标识用户的信息。

使用率数据集默认情况下，但本地管理员可以将其关闭业务服务器 2015 Skype 上使用 DisableAutomaticSendTracing 组策略设置。 关闭此设置将影响组织中的所有用户。 有关详细信息，请参阅[中的业务服务器 2015 Skype 的配置客户端引导策略](https://technet.microsoft.com/library/gg425941.aspx)。

打开或关闭，最终用户无法启用使用率数据集。

Skype 会议应用程序和联接启动器网页，控制遥测的方法是通过此策略：

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

此策略默认为 false，因此默认情况下关闭为遥测集合。 此设置是每个池，并控制与 Skype 会议应用程序连接到该服务器上承载会议的所有用户。

## <a name="error-reporting-data"></a>错误报告数据

错误报告数据可以包括有关性能和可靠性、 设备配置、 网络连接质量，错误代码、 错误日志和异常的信息。 下面是一些特定错误报告收集的数据的示例：

|**数据类型**|**示例**|**说明**|
|:-----|:-----|:-----|
|消息方向  <br/> |传入  <br/> ||
|会话状态  <br/> |空闲时间  <br/> ||
|对话线程 ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|用户 Id  <br/> |amosmarble <br/> |ID 是以明文形式，其之前将其存储遥测服务进行哈希处理发送  <br/> |

错误报告数据可能还包含个人身份信息，例如用户的 IP 地址和会话初始协议统一资源标识符 (SIP URI)。 请参阅[业务隐私声明的 Skype](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)的什么收集的详细说明。

错误报告需要以下两项：

- 在服务器上或租户管理员中心 （这是默认状态） DisableAutomaticSendTracing 组策略设置设置为 False。 有关详细信息，请参阅[中的业务服务器 2015 Skype 的配置客户端引导策略](https://technet.microsoft.com/library/gg425941.aspx)。
    
- 最终用户单独常规选项卡中加入 (单击齿轮图标![齿轮图标](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)，然后将**选项**对话框打开与显示**常规**选项卡) 中的商业客户端 Skype。
    
 
![Skype 选项中的业务数据集复选框 > 常规对话框](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
对于 Skype 会议应用程序，MeetingUxEnableTelemetry 还将控制错误报告，但对 Windows 上崩溃，Watson 设置控制上载崩溃信息。 在桌面客户端对话框中看到如 Skype 会议应用程序没有用户设置。

有关详细信息，请参阅[Skype for Business 中的常规设置选项](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。

您可以看到[设置业务 online Skype 的网络](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)设置您的网络。

如果您使用的 Office 365 21Vianet 在中国由操作，请参阅[设置您的业务 online 由 21Vianet Skype 的网络](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。

## <a name="related-topics"></a>相关主题
[客户体验改善计划](https://www.microsoft.com/products/ceip/default.mspx)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
