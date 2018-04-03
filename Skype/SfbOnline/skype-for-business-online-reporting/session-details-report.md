---
title: 会话详细信息报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 全新的 Office 365 报告仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。
ms.openlocfilehash: 3f33c08f271e638aa160319d39f2e66f97f61a1a
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="session-details-report"></a>会话详细信息报告

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。 例如， **Skype 业务会话详细信息**报表可用于单个用户的呼叫体验有关的详细信息，请参阅。
  
更多可用的报告，检查出[报告概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
  
本报告中的，以及其他 Skype 业务报告提供有关活动包括组织跨会话详细信息详细信息。 当您研究，规划和进行其他业务决策为您的组织和建立[通信信用](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)，这些细节就非常有用。
  
> [!NOTE]
> [!注释] 以管理员身份登录 Office 365 管理中心后，可以查看所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>如何获取对 Skype 业务会话详细信息报表

1. 请转到**Office 365 管理中心** > **的报告**
    
2. 从左侧的菜单中，选择**报表**，然后单击**使用情况**。
    
3. 在下**一个报告中选择**列表中，单击**Skype 业务会话的详细信息**。
    
    > [!TIP]
    > 如果没有看到列出此报告，请转到**业务管理中心的 Skype** > **报告** > **会话的详细信息**。 
  
    > [!IMPORTANT]
    > [!重要信息] 你可能无法看到此处所示的所有产品和报告，具体取决于你拥有的 Office 365 订阅。 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>解释 Skype 业务会话详细信息报表

可以通过查看每个要显示的列来获取到用户的 Skype 业务会话的详细信息图。
  
以下是此报告的外观。
  
![Skype 业务会话详细信息报告的仪表板。](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**搜索用户的别名**，您可以为单个用户搜索和下表中将显示所有用户的会话的详细信息。 
***
![2 号](../images/sfbcallout2.png)<br/>**输入开始日期时间**允许您放入的开始日期。 您可以使用日历选择日期或手动输入的日期。 必须填充此字段。
***
![数字 3](../images/sfbcallout3.png)<br/>**输入日期时间来**让您放入的结束日期。 您可以使用日历选择日期或手动输入的日期。 如果设置没有结束日期，则默认为从开始日期的 30 天。
***
![数字 4](../images/sfbcallout4.png)<br/>下表显示了每个用户的所有会话详细信息的分类。 这将显示所有已分配给他们和他们的会话信息业务的 Skype 的用户。 你可以添加/删除表格的列。 <br/><br/>为每个会话表包含以下列：
*    **对话框 ID**是 SIP 会话的唯一标识符的 ID。
*    **媒体类型说明**描述会话是否电话会议或 P2P 会话并使用的媒体类型 （音频/视频/应用程序共享）。
*    **开始时间**是在会话启动时的时间。
*    **结束时间**是会话的结束的时间。
*    **从 URI**是用户或启动会话的服务的 URI。 可能为空，如果用户启动从 PSTN 电话会话。
*    **对 URI**是目标的会话启动的服务的用户的 URI。 如果这是大会，这是组织者的 URI。 可能为空如果会话的目标是 PSTN 电话号码。
*    **从客户端版本**会告诉您的用户代理和用户或启动会话的服务所使用的客户端版本。
*    **到客户端的版本**会告诉您的用户代理和用户或服务的会话初始化的目标所使用的客户端版本。
*    如果会话是电话会议，**会议 URL**是大会，SIP URL。 相同的会议呼叫中的所有用户都将都具有相同的会议 URL。 
*    有可能的话，**从电话号码**是会话的目标电话号码。 电话号码的最后一位数字可能被替换为 x，为了保护用户的隐私。
*    有可能的话，**到电话号码**是会话的目标电话号码。 电话号码的最后一位数字可能被替换为 x，为了保护用户的隐私。
*    **从端点 Id**是从用户使用方终结点的唯一 GUID。 用于标识是否用户通信从相同的终结点的多个会话。 如果用户使用的 PSTN 电话，或从服务启动会话，则可能为空。
*    **对终结点 Id**是终结点到用户使用一个唯一的 GUID。 用于标识是否用户通信从相同的终结点的多个会话。 可能为空，如果用户正在使用的 PSTN 电话，如果会话已启动服务，或无法建立会话。
*    **Conf 实例**是会议使用的会议 URL 的实例的唯一 GUID。 定期会议将具有相同的会议 URL，而会议的每个实例都有不同配置实例。
*    **代表 URI**是代理者的名义建立会话的 URI。 <br/> **通过 URI 引用**是用户的引用建立会话的 URI。
*    **响应代码**是指示是否已成功建立该会话的会话建立的 SIP 响应代码。

对于每个会话中，在一定条件下没有子表使用不同的数据。 下面列出了发件人并给用户或服务在子表中可用的选项卡。
*    会话选项卡显示有关计算机和操作系统的数据。
*    MEDIALINES 选项卡显示网络连接信息和设备的信息。
*    AUDIOSTREAMS 选项卡将显示有关音频流会话中涉及的网络性能数据
*    AUDIOCLIENTEVENTS 选项卡显示客户端检测到问题会影响音频体验有关的数据。
*    AUDIOSIGNALS 选项卡显示有关会话处理音频信号的数据。
*    APPSHARINGSTREAMS 选项卡显示有关应用程序共享或桌面共享流的网络性能数据所涉及的会话。
*    VIDEOCLIENTEVENTS 选项卡显示客户端检测到问题会影响视频体验有关的数据。
*    VIDEOSTREAMS 选项卡将显示有关视频流会话中涉及的网络性能数据
*    路由追踪选项卡显示在会话期间通过路由追踪收集网络跃点计数。 用于会话的实际媒体路径可能有所不同，并且在没有音频会话中时，这些数据才可用。
*    FEEDBACKREPORTS 选项卡显示任何末尾调用会话中的用户所提供的调查数据。
***
![数字 5](../images/sfbcallout5.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。 
***
![数字 6](../images/sfbcallout6.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype 的业务活动报告](activity-report.md)您可以看到多少用户使用对等、 有组织和参与了会议会话。
    
- [Skype 的业务设备使用情况报告](device-usage-report.md)您可以查看包括基于 Windows 操作系统的设备，拥有 Skype 的业务应用程序的移动设备安装，并将其用于即时消息和会议。
    
- [Skype 业务会议组织者活动报告](conference-organizer-activity-report.md)您可以看到您的用户多少组织使用 IM，音频/视频、 应用程序共享，Web，拨入/出 — 第三方，并拨入/出-Microsoft 的会议。
    
- [Skype 业务会议参与者的活动报告](conference-participant-activity-report.md)您可以看到多少 IM，音频/视频、 应用程序共享、 Web 和拨入/出会议会议都要参加。
    
- [Skype 业务对等活动报告](peer-to-peer-activity-report.md)您可以看到您的用户使用 IM，音频/视频、 应用程序共享和文件传输的多少。
    
- [Skype 的业务 PSTN 使用情况报告](pstn-usage-report.md)您可以看到所花费的入站/出站呼叫和成本为这些调用的分钟数。

- [适用于业务用户的 Skype 阻塞报表](users-blocked-report.md)您可以查看组织中的用户进行 PSTN 呼叫已被阻止。

- [Skype 业务 PSTN 分钟池报告](pstn-minute-pools-report.md)您可以看到在本月组织内消耗的分钟数。
    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 