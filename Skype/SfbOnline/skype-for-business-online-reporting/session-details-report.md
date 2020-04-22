---
title: 会话详细信息报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
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
description: 新的 Microsoft 365 "报表" 仪表板显示你的组织中的 Office 365 产品的活动概述。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。
ms.openlocfilehash: b10e68e46b8865579692594ded33e89558f4fdc2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776277"
---
# <a name="session-details-report"></a>会话详细信息报告

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。 例如，您可以使用**Skype For business "会话详细信息**" 报表查看有关单个用户的呼叫体验的详细信息。
  
查看[报表概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以了解更多可用报表。
  
此报告以及其他 Skype for Business 报表提供有关活动的详细信息，包括组织内的会话详细信息。 在调查、规划和为组织制定其他业务决策以及设置[通信信用点数](/microsoftteams/what-are-communications-credits)时，这些详细信息非常有用。
  
> [!NOTE]
> 当您以管理员身份登录到 Microsoft 365 管理中心时，您可以看到所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>如何访问 Skype for Business 会话详细信息报告

1. 转到管理中心 >**报表**
    
2. 从左侧菜单中选择 "**报表**"，然后单击 "**使用情况**"。
    
3. 在 "**选择报表**" 下的列表中，单击 " **Skype for business 会话详细信息**"。
    
    > [!TIP]
    > 如果未看到此报告列出，请转到**Skype for business 管理中心** > **报告** > **会话详细信息**。 
  
    > [!IMPORTANT]
    > 你可能无法看到此处所示的所有产品和报告，具体取决于你拥有的 Microsoft 365 或 Office 365 订阅。 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>解释 Skype for Business 会话详细信息报告

通过查看显示的每一列，可以查看用户的 Skype for Business 会话详细信息。
  
以下是此报告的外观。
  
![Skype for Business 会话详细信息报告仪表板。](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**按别名搜索用户**允许您搜索单个用户并在下表中显示用户的所有会话详细信息。 
***
![第二](../images/sfbcallout2.png)<br/>**输入**开始日期时间可让你投入到开始日期。 可以使用日历选择日期或手动输入日期。 必须填写此字段。
***
![第三](../images/sfbcallout3.png)<br/>**输入结束日期时间**可使你投入到结束日期。 可以使用日历选择日期或手动输入日期。 如果未设置结束日期，则默认值为从开始日期起30天。
***
![第四](../images/sfbcallout4.png)<br/>此表显示了每个用户的所有会话详细信息的细目。 此示例显示分配有 Skype for Business 及其会话信息的所有用户。 你可以添加/删除表格的列。 <br/><br/>该表包含每个会话的以下列：
*    **对话框 id**是 SIP 会话的唯一标识符的 ID。
*    **媒体类型说明**描述会话是电话会议还是 P2P 会话以及所使用的媒体类型（音频/视频/应用程序共享）。
*    "**开始时间**" 是启动会话的时间。
*    "**结束时间**" 是会话结束的时间。
*    **从 URI**是启动会话的用户或服务的 uri。 如果用户从 PSTN 手机启动会话，则可能为空白。
*    **TO uri**是会话启动目标的用户或服务的 uri。 在会议的情况下，这是组织者的 URI。 如果会话的目标是 PSTN 电话号码，则可能为空。
*    **从客户端版本**告诉你启动会话的用户或服务所使用的客户端代理和版本。
*    对于**客户端版本**，告知你由会话启动的目标用户或服务使用的用户代理和版本。
*    如果会话是电话会议，则**会议 url**是会议的 SIP url。 同一电话会议中的所有用户将具有相同的会议 URL。 
*    "**电话号码**" 是指会话目标的电话号码（如果适用）。 电话号码的最后一位数可能被替换为 "x" 以保护用户隐私。
*    "**电话号码**" 是指会话目标的电话号码（如果适用）。 电话号码的最后一位数可能被替换为 "x" 以保护用户隐私。
*    **从终结点 Id**是由 From 用户使用的终结点的唯一 GUID。 用于标识用户是否从同一终结点通信多个会话。 如果用户使用 PSTN 手机或者会话是从服务启动的，则可以为空。
*    **To 终结点 Id**是与用户一起使用的终结点的唯一 GUID。 用于标识用户是否从同一终结点通信多个会话。 如果用户使用 PSTN 电话，或者会话是通过服务启动的，或者会话无法建立，则可能为空白。
*    会议**实例**是使用会议 URL 的会议实例的唯一 GUID。 定期会议将具有相同的会议 URL，但会议的每个实例都将有一个区别的会议实例。
*    **代表 uri**是代表正在建立会话的委托人进行通话的 uri。 <br/> **引用者 uri**是指引用会话建立的用户的 URI。
*    **响应代码**是用于建立会话的 SIP 响应代码，用于指示会话是否已成功建立。

对于每个会话，有一个子表，其中包含不同的可用数据，具体取决于方案。 下表列出了 "发件用户" 和 "收件人" 和 "服务" 子表中可用的选项卡。
*    "会话" 选项卡显示有关计算机和操作系统的数据。
*    MEDIALINES 选项卡显示网络连接信息和设备信息。
*    AUDIOSTREAMS 选项卡显示有关会话中涉及的音频流的网络性能数据。
*    AUDIOCLIENTEVENTS 选项卡显示了影响音频体验的客户端检测到的问题的相关数据。
*    AUDIOSIGNALS 选项卡显示有关会话的音频信号处理的数据。
*    APPSHARINGSTREAMS 选项卡显示有关会话中涉及的应用程序共享或桌面共享流的网络性能数据。
*    VIDEOCLIENTEVENTS 选项卡显示了影响视频体验的客户端检测到的问题的相关数据。
*    VIDEOSTREAMS 选项卡显示有关会话中涉及的视频流的网络性能数据。
*    TRACEROUTES 选项卡显示在会话期间通过 traceroute 收集的网络跃点。 用于会话的实际媒体路径可能会有所不同，并且此数据仅在会话中有音频时才可用。
*    FEEDBACKREPORTS 选项卡显示由会话中的用户提供的呼叫调查数据的任何结束时间。
***
![第五](../images/sfbcallout5.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。 
***
![第六](../images/sfbcallout6.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype For business 活动报告](activity-report.md)你可以查看你的用户使用对等、组织和参与会议会话的数量。
    
- [Skype For business 设备使用情况报告](device-usage-report.md)你可以查看设备，包括安装了 Skype for Business 应用的基于 Windows 的操作系统和移动设备并将其用于即时消息和会议。
    
- [Skype for business 会议组织者活动报告](conference-organizer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享、Web、拨入/拨出和拨入/拨出的方式组织会议的程度。
    
- [Skype for business 会议参与者活动报告](conference-participant-activity-report.md)你可以查看参与的即时消息、音频/视频、应用程序共享、Web 和电话拨入/拨出式会议会议的数量。
    
- [Skype For business 对等活动报告](peer-to-peer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享和传输文件的数量。
    
- [Skype for BUSINESS PSTN 使用报告](pstn-usage-report.md)您可以查看入站/出站通话所用的分钟数和这些通话的费用。

- 已[阻止的 Skype for business 用户报告](users-blocked-report.md)你可以查看组织中已阻止进行 PSTN 呼叫的用户。

- [Skype For BUSINESS PSTN 分钟池报告](pstn-minute-pools-report.md)您可以查看在您的组织内的当前月份内消耗的分钟数。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报表](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 