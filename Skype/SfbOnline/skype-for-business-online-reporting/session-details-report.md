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
description: "\"报表\"仪表板显示组织中Microsoft 365或Office 365活动概述。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。"
ms.openlocfilehash: 522a82bf9b93a590f8f319d59e805b23ba34d4665b34eb05541aa18d1b9ba89e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308013"
---
# <a name="session-details-report"></a>会话详细信息报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

"**报表**"仪表板显示组织中Microsoft 365或Office 365活动概述。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。 例如，可以使用"Skype for Business **详细信息**"报表查看有关单个用户的呼叫体验的详细信息。
  
有关更多 [可用报表](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) ，请查看报表概述。
  
此报告以及其他活动Skype for Business提供有关活动的详细信息，包括整个组织的会话详细信息。 当你为组织进行调查、规划和做出其他业务决策以及设置通信信用额度时，这些详细信息[非常有用。](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> 以管理员角色登录到 Skype for Business时，可以看到所有 Microsoft 365 管理中心。 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>如何访问"Skype for Business会话详细信息"报表

1. 转到管理中心> **报表**
    
2. 从 **左侧菜单中** 选择"报表"，然后单击"使用情况 **"。**
    
3. 在"选择报表 **"下的列表中，** 单击 **"Skype for Business详细信息"。**
    
    > [!TIP]
    > 如果未列出此报告，请转到管理 **Skype for Business**  >  **报告**  >  **会话详细信息。** 
  
    > [!IMPORTANT]
    > 根据你Microsoft 365或Office 365订阅，可能看不到此处显示的所有产品和报表。 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>解释Skype for Business会话详细信息报告

通过查看显示的每个列，Skype for Business查看用户的会话详细信息。
  
以下是此报告的外观。
  
![Skype for Business会话详细信息报表仪表板。](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**通过"按别名** 搜索用户"，可以搜索单个用户，并显示下表中该用户的所有会话详细信息。 
***
![第二](../images/sfbcallout2.png)<br/>**输入"从日期** 时间"可输入开始日期。 您可以使用日历选择日期或手动输入日期。 必须填充此字段。
***
![第三](../images/sfbcallout3.png)<br/>**输入"日期时间** "可输入结束日期。 您可以使用日历选择日期或手动输入日期。 如果未设置结束日期，则默认值为自开始日期起 30 天。
***
![第四](../images/sfbcallout4.png)<br/>下表显示了每个用户的所有会话详细信息的细分。 这会显示已分配Skype for Business的所有用户及其会话信息。 你可以添加/删除表格的列。 <br/><br/>该表包含每个会话的以下列：
*    **对话 ID** 是 SIP 会话的唯一标识符的 ID。
*    **媒体类型说明** 描述会话是电话会议还是 P2P 会话，以及用于音频/ (/应用程序共享的媒体) 。
*    **开始时间** 是会话开始时的时间。
*    **结束时间** 是会话结束的时间。
*    **"从 URI"** 是发起会话的用户或服务的 URI。 如果用户从 PSTN 电话启动了会话，则它可能为空。
*    To URI 是作为会话启动目标的用户或服务的 **URI。** 对于会议，这是组织者的 URI。 如果会话的目标是 PSTN 电话号码，则它可能为空。
*    **从客户端** 版本告知启动会话的用户或服务使用的用户代理和客户端版本。
*    **客户端版本** 会告知用户代理，以及作为会话启动目标的用户或服务使用的客户端版本。
*    **会议 URL** 是会议的 SIP URL（如果会话是电话会议）。 同一电话会议中的所有用户将具有相同的会议 URL。 
*    **"从** 电话号码"是作为会话目标的电话号码（如果适用）。 电话号码的最后一个数字可能替换为"x"，以保护用户隐私。
*    **"呼叫** 号码"是作为会话目标的电话号码（如果适用）。 电话号码的最后一个数字可能替换为"x"，以保护用户隐私。
*    **"从终结点 ID"** 是"来自"用户使用的终结点的唯一 GUID。 用于标识用户是否正在从同一终结点通信多个会话。 如果用户使用的是 PSTN 电话，或者会话从服务启动，则可能是空白的。
*    **"到终结点 ID"** 是"到"用户使用的终结点的唯一 GUID。 用于标识用户是否正在从同一终结点通信多个会话。 如果用户使用的是 PSTN 电话、从服务启动会话或无法建立会话，则可能会为空。
*    **Conf** 实例是使用会议 URL 的会议实例的唯一 GUID。 定期会议将具有相同的会议 URL，但会议的每个实例将有所不同"合并实例"。
*    代表 URI 是代表建立会话的委派器的 **URI。** <br/> **"引用者 URI"** 是指引用建立会话的用户的 URI。
*    **响应代码** 是建立会话的 SIP 响应代码，用于指示会话是否成功建立。

对于每个会话，有一个子表，该表根据方案提供不同的数据。 下面列出了"从"和"到"用户或服务在子表中可用的选项卡。
*    "会话"选项卡显示有关计算机和操作系统的数据。
*    MEDIALINES 选项卡显示网络连接信息和设备信息。
*    AUDIOSTREAMS 选项卡显示有关会话中涉及的音频流的网络性能数据。
*    AUDIOCLIENTEVENTS 选项卡显示有关客户端检测到影响音频体验的问题的数据。
*    AUDIOSIGNALS 选项卡显示有关会话的音频信号处理的数据。
*    APPSHARINGSTREAMS 选项卡显示有关会话中涉及的应用程序共享或桌面共享流的网络性能数据。
*    VIDEOCLIENTEVENTS 选项卡显示有关客户端检测到影响视频体验的问题的数据。
*    VIDEOSTREAMS 选项卡显示有关会话中涉及的视频流的网络性能数据。
*    TRACEROUTES 选项卡显示会话期间通过 traceroute 收集的网络跃点。 用于会话的实际媒体路径可能有所不同，并且此数据仅在会话中有音频时可用。
*    FEEDBACKREPORTS 选项卡显示会话中用户提供的任何呼叫调查结束数据。
***
![第五](../images/sfbcallout5.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。 
***
![第六](../images/sfbcallout6.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他Skype for Business报表？

- [Skype for Business活动报告](activity-report.md)你可以看到你的用户使用对等会议会话、组织会议会话和参与会议会话的用户数。
    
- [Skype for Business设备使用情况报告](device-usage-report.md)你可以查看设备，包括Windows操作系统和移动设备，这些设备已安装Skype for Business应用，并使用它进行即时消息和会议。
    
- [Skype for Business组织者活动报告](conference-organizer-activity-report.md)可以看到有多少用户正在组织使用即时消息、音频/视频、应用程序共享、Web、拨入/拨出 - 第三方和拨入/拨出 -Microsoft 的会议。
    
- [Skype for Business会议参与者活动报告](conference-participant-activity-report.md)你可以看到正在参与多少个即时消息、音频/视频、应用程序共享、Web 和电话拨入/拨出式会议。
    
- [Skype for Business对等活动报告](peer-to-peer-activity-report.md)可以看到有多少用户使用即时消息、音频/视频、应用程序共享和传输文件。
    
- [Skype for Business PSTN 使用情况报告](pstn-usage-report.md)可以看到入站/出站呼叫花费的时间以及这些调用的成本。

- [Skype for Business用户阻止的报告](users-blocked-report.md)可以看到组织中被阻止进行 PSTN 呼叫的用户。

- [Skype for Business PSTN 分钟](pstn-minute-pools-report.md)数池报告，可以看到组织内部当月使用的分钟数。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
