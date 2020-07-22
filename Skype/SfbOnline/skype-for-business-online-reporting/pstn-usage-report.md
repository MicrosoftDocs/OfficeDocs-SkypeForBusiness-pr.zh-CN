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
description: 新的 Skype for Business 管理中心报告区域显示你的组织中的通话和音频会议活动。 它使您能够深入查看报表，让您更细致地了解每个用户的活动。 例如，你可以使用 Skype for Business PSTN 使用详细信息报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 你可以查看音频会议 PSTN 使用详细信息，包括通话费用，以便你可以了解你的使用情况并拨打帐单详细信息以确定你的组织中的使用情况。
ms.openlocfilehash: 09d372f6526d14a65e878271a1b277fc19d7d3e4
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201166"
---
# <a name="pstn-usage-report"></a>PSTN 使用报告

新的 Skype for Business 管理中心**报告**区域显示你的组织中的通话和音频会议活动。 它使您能够深入查看报表，让您更细致地了解每个用户的活动。 例如，你可以使用 **Skype for Business PSTN 使用详细信息**报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 你可以查看音频会议 PSTN 使用详细信息，包括通话费用，以便你可以了解你的使用情况并拨打帐单详细信息以确定你的组织中的使用情况。
  
有关可用报表的详细信息，请查看[报表概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
  
此报告以及其他 Skype for Business 报告提供了有关活动的详细信息，包括您的组织内的通话使用情况。 在调查、规划和为组织制定其他业务决策以及设置[通信信用点数](/microsoftteams/what-are-communications-credits)时，这些详细信息非常有用。
  
> [!NOTE]
> 当您以管理员身份登录到 Microsoft 365 管理中心时，您可以看到所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>如何获取 Skype for Business PSTN 使用详细信息报告

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

- 转到管理中心 >**管理中心**  >  **Skype for business 管理中心**  >  **报告**  >  **PSTN 使用详细信息**。
    
    > [!NOTE]
    > 你可能无法看到此处所示的所有产品和报告，具体取决于你拥有的 Microsoft 365 或 Office 365 订阅。
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>解释 Skype for Business PSTN 使用情况报告

你可以通过查看显示的每一列了解用户的 Skype for Business PSTN 使用情况。
  
以下是此报告的外观。
  
[![Skype for BUSINESS PSTN 使用报告 ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![第一](../images/sfbcallout1.png)<br/>该表格显示了按用户细分的全部 PSTN 使用情况。 此示例显示分配有 Skype for Business 的所有用户及其 PSTN 使用情况。 你可以添加/删除表格的列。
*    通话**id**是呼叫的呼叫 id。 它是呼叫 Microsoft 服务支持时使用的呼叫的标识符。
*    " **用户 ID**"是用户的登录名。
*    "**电话号码**" 是接收入站通话呼叫或拨出拨出电话的号码的 Skype for business 电话号码。
*    **用户位置**是用户所在的国家/地区。
*    呼叫**方 ID**是呼叫者的电话号码（来电显示），用于拨入呼叫、呼叫发出的号码或 Skype for business 号码，呼叫来自该电话拨出的电话。
*    **呼叫类型**指示呼叫是 PSTN 传出还是传入呼叫，以及呼叫类型，例如由用户或音频会议发出的呼叫。 您可能看到的呼叫类型如下： 

     **通话计划呼叫类型** 
     *    **user_in** （用户收到入站 PSTN 呼叫） 
     *    **user_out** （用户发出出站 PSTN 呼叫） 
     *    **user_out_conf** （用户向呼叫添加2个或更多 PSTN 参与者，如 "3 路会议呼叫"） 
     *    **user_out_transfer** （用户已将呼叫转移到 PSTN 号码） 
     *    **user_out_forwarding** （用户将呼叫转接到 PSTN 号码）

     **音频会议呼叫类型**
     *    **conf_in** （对音频会议桥的入站呼叫）。 对于此呼叫类型的记录，"**用户 ID** " 列中指定的用户对应于会议的组织者。
     *    **conf_out** （来自音频会议网桥的出站呼叫，通常用于向会议添加 PSTN 号码）。 对于此呼叫类型的记录，"**用户 ID** " 列中指定的用户对应于会议的组织者。

     **统一通信应用程序（UCAP）** 
     *    **ucap_in** （对 UC 应用程序（如自动助理或呼叫队列）的入站 PSTN 呼叫 
     *    **ucap_out** （来自 UC 应用程序的出站 PSTN 呼叫，如自动助理或呼叫队列）
         > [!NOTE]
         > 从 UC 应用程序（如自动助理或呼叫队列）转移到用户的呼叫不会显示在 PSTN 使用报告中，因为这些呼叫条是对等（P2P）音频呼叫。 你可以在 "工具 > Skype for business 呼叫分析" 下访问 Skype for Business 管理中心中的 P2P 呼叫，并按用户名或 SIP 地址进行搜索，按日期/时间和/或始发 CLID （呼叫行 ID）将呼叫关联起来。 

     "**国内/国际**" 告诉您所拨的电话是否被视为国内（在国家/地区内）还是国际（国家/地区外）的电话（基于用户的位置）。 
*    "**目的地已拨**" 表示拨打的国家/地区目的地的名称，如法国、德国或美国（美国）。 
*    **Number type**指由用户电话号码、服务或免费电话号码组成的电话号码类型。  
*    " **开始时间(UTC)**"是开始或拨打呼叫的时间。 
*    " **持续时间**"是接听呼叫的时间。  
*    **ConfID**是音频会议的会议 ID。 
*    "**费用**" 表示支付给您的帐户的通话的金额或费用。 
*    **货币**是用于计算通话费用的货币类型。 
*    **功能**是用于通话的许可证。 你可能会看到的许可证类型如下： 
     *    **MCOPSTNPP** -通讯信用点数 <br/> **MCOPSTN1** -国内通话计划（3000，美国/1200 最少欧盟计划） 
     *    **MCOPSTN2** -国际通话计划 
     *    **MCOPSTN5** -国内通话计划（120分钟通话计划） 
     *    **MCOPSTN6** -国内通话计划（240 min 通话计划）注意：可用性有限
     *    **MCOMEETADD** -音频会议
     *    **MCOMEETACPEA** -每分钟支付的音频会议
     
> [!NOTE]
> 如果您想要运行报告以仅包括您的通话或会议订阅中未包括的每分钟费率通话，请使用 "MCOPSTNPP" 功能筛选报告。 这样做将提供所有按分钟付费通话的明细。  对于每分钟支付的音频会议，请按 "MCOMEETACPEA" 而不是 "MCOPSTNPP" 进行筛选。  

> [!NOTE]
> 在某些字段中，您可能还会看到 "无数据"。 "无数据" 表示该字段不适用于通话类型或功能。 

> [!NOTE]
> 如果您有 Telstra 或 Softbank 通话计划，则在 PSTN 使用报告中将看不到任何通话详细记录。 请联系 Telstra 或 Softbank，以满足你的报告需求。 
***
![第二](../images/sfbcallout2.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。
 ***

## <a name="exporting-pstn-usage-report"></a>导出 PSTN 使用情况报告

单击或点击 "**导出到 Excel** " 按钮可下载 PSTN 使用情况报告。 您可以从当前日期导出一年的数据，除非特定国家/地区的法规禁止将数据保留12个月。

此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。

导出过程可能需要几秒钟到几分钟才能完成，具体取决于数据的数量。 当服务器完成导出时，你将收到名为 "**Calls. []" 的 zip 文件 `identifier` 。zip**"，其中标识符是导出的唯一 ID，可用于故障排除。

如果既有通话计划又有直接路由，则导出的文件可能包含两个产品的数据。 PSTN 使用报告文件将具有文件名 "**PSTN. []" `UTC date` 。csv**"。 除了 PSTN 和直接路由文件，存档中还包含 "**parameters.js**" 文件，并具有所选的导出时间范围和功能（如果有）。

导出的文件是一个逗号分隔值（CSV）文件，符合[RFC 4180](https://tools.ietf.org/html/rfc4180)标准。 该文件可以在 Excel 或任何其他符合标准的编辑器中打开，无需任何转换。

CSV 的第一行包含列名称。

### <a name="fields-in-the-export"></a>导出中的字段

导出的文件包含在联机报表中不可用的其他字段。 这些可用于疑难解答和自动化工作流。

> [!div class="has-no-wrap"]  
> | #  | 名称 | [数据类型（SQL Server）](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 唯一的呼叫标识符 |
> | 1 | 通话 ID | `nvarchar(64)` | 通话标识符。 不保证唯一性 |
> | 2 | 会议 ID | `nvarchar(64)` | 音频会议的 ID |
> | 3 | 用户位置 | `nvarchar(2)` | 用户的国家/地区代码， [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中调用用户的 ID。<br/> 对于 bot 呼叫类型（ucap_in，ucap_out），此和其他用户信息将为 null/空 |
> | 5 | UPN | `nvarchar(128)` | Azure Active Directory 中的 UserPrincipalName （登录名称）。<br/>这通常与用户的 SIP 地址相同，并且可以与用户的电子邮件地址相同 |
> | 6 | 用户显示名称 | `nvarchar(128)` | 用户的显示名称 |
> | 7 | 来电显示 | `nvarchar(128)` | 为拨入电话或拨出电话拨出的电话号码接收呼叫的号码。 [E. 164](https://en.wikipedia.org/wiki/E.164)格式 |
> | 个 | 呼叫类型 | `nvarchar(32)` | 呼叫是 PSTN 出站通话还是入站呼叫以及呼叫类型，例如由用户或音频会议发出的呼叫 |
> | db-9 | 号码类型 | `nvarchar(16)` | 用户的电话号码类型，例如免费号码的服务 |
> | 10 | 国内/国际 | `nvarchar(16)` | 呼叫是国内的（在国家或地区内）还是国际（在国家或地区之外）基于用户的位置 |
> | 11 | 已拨目标 | `nvarchar(64)` | 拨打的国家或地区 |
> | 至 | 目标号码 | `nvarchar(32)` | 以[164](https://en.wikipedia.org/wiki/E.164)格式拨打的号码 |
> | 13 | 开始时间 | `datetimeoffset` | 调用开始时间（UTC， [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)） |
> | 14 | 结束时间 | `datetimeoffset` | 通话结束时间（UTC， [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)） |
> | 岁 | 持续秒数 | `int` | 通话的连接时间 |
> | utf-16 | 连接费 | `numeric(16, 2)` | 连接费价格 |
> | 日 | 收费 | `numeric(16, 2)` | 为您的帐户收取的通话金额或通话费用 |
> | 18 | 货币 | `nvarchar(3)` | 用于计算通话费用的货币类型（[ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)） |
> | 19 | 功能 | `nvarchar(32)` | 用于通话的许可证 |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype For business 活动报告](activity-report.md)你可以查看你的用户使用对等、组织和参与会议会话的数量。
    
- [Skype For business 设备使用情况报告](device-usage-report.md)你可以查看设备，包括安装了 Skype for Business 应用的基于 Windows 的操作系统和移动设备并将其用于即时消息和会议。
    
- [Skype for business 会议组织者活动报告](conference-organizer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享、Web、/dial 外接程序和/dial 注销的方式组织的会议量。
    
- [Skype for business 会议参与者活动报告](conference-participant-activity-report.md)你可以查看正在参与的 IM、音频/视频、应用程序共享、Web 和拨出音频会议的数量。
    
- [Skype For business 对等活动报告](peer-to-peer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享和传输文件的数量。
    
- 已[阻止的 Skype for business 用户报告](users-blocked-report.md)你可以查看组织中已阻止进行 PSTN 呼叫的用户。

- [Skype For BUSINESS PSTN 分钟池报告](pstn-minute-pools-report.md)您可以查看在您的组织内的当前月份内消耗的分钟数。

- [Skype For business 会话详细信息报告](session-details-report.md)你可以查看有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报表](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
