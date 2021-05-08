---
title: PSTN 使用报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
- Reporting
description: 新的Skype for Business管理中心报告"区域显示你的组织的呼叫和音频会议活动。 它使你能够钻取到报表，从而更细致地了解每个用户的活动。 例如，你可以使用 Skype for Business PSTN 使用详细信息报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 您可以查看音频会议 PSTN 使用详细信息，包括呼叫费用，以便了解使用情况和呼叫计费详细信息，以确定组织内部的使用情况。
ms.openlocfilehash: b806c0b3a471f862de6d69c6ed9b5220441c4257
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238200"
---
# <a name="pstn-usage-report"></a>PSTN 使用报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

新的"Skype for Business中心报告"区域显示组织中呼叫和音频会议活动。 它使你能够钻取到报表，从而更细致地了解每个用户的活动。 例如，你可以使用 **Skype for Business PSTN 使用详细信息** 报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 您可以查看音频会议 PSTN 使用详细信息，包括呼叫费用，以便了解使用情况和呼叫计费详细信息，以确定组织内部的使用情况。
  
有关更多 [可用报表，](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 请查看报表概述。
  
此报告以及其他Skype for Business一起提供有关活动的详细信息，包括在整个组织中呼叫使用情况。 当你为组织进行调查、规划和做出其他业务决策以及设置通信信用额度时，这些详细信息[非常有用。](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> 以管理员Skype for Business登录到管理中心时，可以看到所有Microsoft 365报表。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>如何获取 Skype for Business PSTN 使用详细信息报告

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

- 转到管理中心>**管理Skype for Business**  >  **报告**  >    >  **PSTN 使用情况详细信息**。
    
    > [!NOTE]
    > 根据你Microsoft 365或Office 365订阅，可能看不到此处显示的所有产品和报表。
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>解释 Skype for Business PSTN 使用情况报告

你可以通过查看显示的每一列了解用户的 Skype for Business PSTN 使用情况。
  
以下是此报告的外观。
  
[![Skype for Business PSTN 使用情况报告 ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![第一](../images/sfbcallout1.png)<br/>该表格显示了按用户细分的全部 PSTN 使用情况。 这会显示已分配给Skype for Business的所有用户及其 PSTN 使用情况。 你可以添加/删除表格的列。
*    **呼叫 ID** 是呼叫的呼叫 ID。 它是调用 Microsoft 服务支持时使用的调用标识符。
*    " **用户 ID**"是用户的登录名。
*    **电话号码** 是Skype for Business来电的号码或拨打的出站呼叫号码。
*    **用户** 位置是用户所在的国家/地区。
*    呼叫者 **ID** 是呼叫者的电话号码 (呼叫者 ID) ，即发起呼叫的号码或发起出站呼叫的 Skype for Business 号码。
*    **呼叫** 类型是呼叫是 PSTN 传出呼叫还是传入呼叫，以及呼叫类型，例如用户拨打的呼叫还是音频会议呼叫。 你可能会看到的调用类型包括： 

     **呼叫计划呼叫类型** 
     *    **user_in (** 收到入站 PSTN 呼叫)  
     *    **user_out (** 用户拨打了出站 PSTN 呼叫)  
     *    **user_out_conf (** 向呼叫添加了 2 个或多个 PSTN 参与者，例如 3 路电话会议)  
     *    **user_out_transfer (** 将呼叫转接到 PSTN 号码)  
     *    **user_out_forwarding (** 将呼叫转发到 PSTN 号码) 

     **音频会议呼叫类型**
     *    **conf_in (** 音频会议网桥的入站) 。 对于此呼叫类型的记录，在"用户 **ID"** 列中指定的用户对应于会议的组织者。
     *    **conf_out (** 音频会议网桥拨打出站呼叫，通常将 PSTN 号码添加到会议) 。 对于此呼叫类型的记录，在"用户 **ID"** 列中指定的用户对应于会议的组织者。

     **UCAP (统一通信)** 
     *    **ucap_in (** 向 UC 应用程序发送入站 PSTN 呼叫，例如自动助理或呼叫队列)  
     *    **ucap_out (** UC 应用程序（例如自动助理或呼叫队列）拨打出站 PSTN) 
         > [!NOTE]
         > 从 UC 应用程序（例如自动助理或呼叫队列）转接到用户的呼叫不会显示在 PSTN 使用情况报告中，因为这些呼叫段是对等的 (P2P) 音频呼叫。 您可以在 Skype for Business 管理中心的"工具 > Skype for Business 呼叫分析"下访问 P2P 调用，并按用户名或 SIP 地址搜索，该地址按日期/时间和/或发起 CLID (呼叫行 ID) 关联呼叫。 

     根据用户的位置，国内 **/** 国际会告知拨打的呼叫是国家/地区 (还是国家/地区)  (外部的) 国内呼叫。 
*    **"目的地"** 是拨打的国家/地区目的地的名称，例如法国、德国或美国 (美国) 。 
*    **"** 号码类型"是用户的电话号码、服务或免费电话号码中的电话号码类型。  
*    " **开始时间(UTC)**"是开始或拨打呼叫的时间。 
*    " **持续时间**"是接听呼叫的时间。  
*    **ConfID** 是音频会议的会议 ID。 
*    **"** 费用"是向帐户收取的通话费用或金额。 
*    **货币** 是用于计算调用成本的货币类型。 
*    **功能** 是用于调用的许可证。 可能看到的许可证类型包括： 
     *    **MCOPSTNPP** - 通信信用额度 <br/> **MCOPSTN1** - 国内呼叫 (3000 分钟美国/1200 分钟欧盟套餐)  
     *    **MCOPSTN2** - 国际呼叫计划 
     *    **MCOPSTN5** - 国内呼叫计划 (120 分钟呼叫计划)  
     *    **MCOPSTN6** - 国内呼叫 (240 分钟呼叫计划) 注意：有限可用性
     *    **MCOMEETADD** - 音频会议
     *    **MCOMEETACPEA** - 每分钟支付音频会议费用
     
> [!NOTE]
> 如果你希望运行报告以仅包括通话或会议订阅中不包括的每分钟付费呼叫，请筛选具有"MCOPSTNPP"功能的报告。 这样做将提供所有每分钟付费通话的项目。  对于按分钟付费的音频会议，按"MCOMEETACPEA"而不是"MCOPSTNPP"进行筛选。  

> [!NOTE]
> 在某些字段中，也可能看到"无数据"。 "无数据"表示字段不适用于调用类型或功能。 

> [!NOTE]
> 如果您有 Telstra 或 Softbank 呼叫计划，则 PSTN 使用报告中不会显示任何呼叫详细信息记录。 有关报告需求，请联系 Telstra 或 Softbank。 
***
![第二](../images/sfbcallout2.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。
 ***

## <a name="exporting-pstn-usage-report"></a>导出 PSTN 使用情况报告

单击或点击"**导出** 到Excel按钮可下载 PSTN 使用情况报告。 除非国家/地区特定的法规禁止将数据保留 12 个月，否则可以导出自当前日期起最多一年的数据。

此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。

导出过程可能需要几秒钟到几分钟才能完成，具体取决于数据量。 服务器完成导出后，将收到名为 **"Calls.Export.[ ] 的 zip 文件 `identifier` 。.zip"，** 标识符是导出的唯一 ID，可用于故障排除。

如果同时具有"呼叫计划"和"直接路由"，则导出的文件可能包含这两个产品的数据。 PSTN 使用情况报告文件将具有文件名 **"PSTN.calls.[ `UTC date` ].csv"。** 除 PSTN 和直接路由文件外，存档还包含文件 **"parameters.json"，** 以及选定的导出时间范围和功能 (（如果有) ）。

导出的文件是 CSV 文件 (逗号) 值，符合 [RFC 4180](https://tools.ietf.org/html/rfc4180) 标准。 可以在任何符合标准的编辑器中Excel文件，而无需任何转换。

CSV 的第一行包含列名称。

### <a name="fields-in-the-export"></a>导出中的字段

导出的文件包含联机报告中不可用的其他字段。 这些可用于故障排除和自动化工作流。

> [!div class="has-no-wrap"]  
> | #  | 名称 | [数据类型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 唯一调用标识符 |
> | 1 | 呼叫 ID | `nvarchar(64)` | 调用标识符。 不保证唯一 |
> | 2 | 会议 ID | `nvarchar(64)` | 音频会议的 ID |
> | 3 | 用户位置 | `nvarchar(2)` | 用户的国家/地区代码 [，ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中调用用户的 ID。<br/> 对于机器人调用类型，此信息和其他用户信息将为 null/空 (ucap_in ucap_out)  |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName () 登录Azure Active Directory。<br/>这通常与用户的 SIP 地址相同，并且可以与用户的电子邮件地址相同 |
> | 6 | 用户显示名称 | `nvarchar(128)` | 用户的显示名称 |
> | 7 | 来电显示 | `nvarchar(128)` | 接收入站呼叫呼叫的号码或为出站呼叫拨打的号码。 [E.164](https://en.wikipedia.org/wiki/E.164) 格式 |
> | 8 | 呼叫类型 | `nvarchar(32)` | 呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型，例如用户拨打的呼叫还是音频会议呼叫 |
> | 9 | 数字类型 | `nvarchar(16)` | 用户的电话号码类型，例如免费电话号码的服务 |
> | 10 | 国内/国际 | `nvarchar(16)` | 该呼叫是 (国家/地区) 还是 (国家/地区) 或区域外部的国内和国际呼叫。 |
> | 11 | 目标已拨号 | `nvarchar(64)` | 拨打的"国家/地区" |
> | 12 | 目标号码 | `nvarchar(32)` | 以 [E.164 格式拨打的](https://en.wikipedia.org/wiki/E.164) 号码 |
> | 13 | 开始时间 | `datetimeoffset` | 呼叫开始时间 ([UTC，ISO 8601](https://en.wikipedia.org/wiki/ISO_8601))  |
> | 14 | 结束时间 | `datetimeoffset` | 呼叫结束时间 (UTC、ISO [8601) ](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | 持续时间秒数 | `int` | 呼叫已连接多久 |
> | 16 | 连接费用 | `numeric(16, 2)` | 连接费用价格 |
> | 17 | 费用 | `numeric(16, 2)` | 向您的帐户收取的呼叫金额或费用 |
> | 18 | 货币 | `nvarchar(3)` | 用于计算调用 [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) (费用的货币)  |
> | 19 | 功能 | `nvarchar(32)` | 用于呼叫的许可证 |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype for Business活动报告](activity-report.md)你可以看到你的用户使用对等会议会话、组织会议会话和参与会议会话的用户数。
    
- [Skype for Business设备使用情况报告](device-usage-report.md)你可以查看设备，包括Windows操作系统和移动设备，这些设备已安装Skype for Business应用，并使用它进行即时消息和会议。
    
- [Skype for Business组织者活动报告](conference-organizer-activity-report.md)可以看到有多少用户正在组织使用即时消息、音频/视频、应用程序共享、Web、/拨出 - 第三方和 /dial out - Microsoft 的会议。
    
- [Skype for Business会议参与者活动报告](conference-participant-activity-report.md)可以看到正在参与多少个即时消息、音频/视频、应用程序共享、Web 和拨出音频会议。
    
- [Skype for Business对等活动报告](peer-to-peer-activity-report.md)可以看到有多少用户使用即时消息、音频/视频、应用程序共享和传输文件。
    
- [Skype for Business用户阻止的报告](users-blocked-report.md)可以看到组织中被阻止进行 PSTN 呼叫的用户。

- [Skype for Business PSTN 分钟](pstn-minute-pools-report.md)数池报告，可以看到组织内部当月使用的分钟数。

- [Skype for Business会话详细信息报告](session-details-report.md)可以看到有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
