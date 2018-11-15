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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 全新的 Office 365 报告仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。
ms.openlocfilehash: 33aa42ea7acd2f28ab0e27da85421071f948ca99
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530547"
---
# <a name="session-details-report"></a>会话详细信息报告

全新的 Office 365 **报告**仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。 例如，可以使用**Skype 的业务会话详细信息**报表以查看有关单个用户的呼叫体验的详细信息。
  
查看[报告概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)可用的详细报告。
  
此报告中的，以及其他 Skype 业务报告提供有关在整个组织，包括会话详细信息的活动详细信息。 您调查，规划，以及使其他业务决策为您的组织和设置[Communications 字幕式](/microsoftteams/what-are-communications-credits)时，这些详细信息是非常有用。
  
> [!NOTE]
> [!注释] 以管理员身份登录 Office 365 管理中心后，可以查看所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>如何获取到 Skype 业务会话详细信息报表

1. 转到**Office 365 管理中心** > **报告**
    
2. 左侧的菜单中，选择**报告**，然后单击**使用率**。
    
3. 在**选择报表**下列表中，单击**Skype 的业务会话详细信息**。
    
    > [!TIP]
    > 如果您看不到列出此报告，请转到**业务管理中心的 Skype** > **报告** > **会话详细信息**。 
  
    > [!IMPORTANT]
    > [!重要信息] 你可能无法看到此处所示的所有产品和报告，具体取决于你拥有的 Office 365 订阅。 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>解释业务会话详细信息报表 Skype

您可以通过查看每个显示的列到业务会话详细信息的用户的 Skype 获取视图。
  
以下是此报告的外观。
  
![业务会话详细信息报表的仪表板的的 Skype。](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**由别名的搜索用户**允许您搜索单个用户，并在下表中显示所有用户的会话详细信息。 
***
![第二](../images/sfbcallout2.png)<br/>**从日期时间 Enter**允许放入的开始日期。 您可以使用日历选择的日期或手动输入的日期。 必须填充此字段。
***
![第三](../images/sfbcallout3.png)<br/>**输入的日期时间来**使可以放入的结束日期。 您可以使用日历选择的日期或手动输入的日期。 如果设置无结束日期，则默认值为 30 天从开始日期。
***
![第四](../images/sfbcallout4.png)<br/>下表显示了每个用户的所有会话详细信息的细分。 此时将显示已分配给它们和其会话信息的业务的 Skype 的所有用户。 你可以添加/删除表格的列。 <br/><br/>表具有为每个会话以下列：
*    **对话 ID**是 SIP 会话的唯一标识符的 ID。
*    **媒体类型说明**介绍会话是否是在电话会议或的 P2P 会话和使用的媒体类型 （音频/视频/应用程序共享）。
*    **开始时间**是时启动会话的时间。
*    **结束时间**是会话结束的时间。
*    **发件人 URI**是启动会话的服务的用户的 URI。 可能为空，如果用户启动从 PSTN 电话会话。
*    **对 URI**是目标的会话初始的服务的用户的 URI。 对于会议，这是组织者的 URI。 可能为空，如果会话的目标 PSTN 电话号码。
*    **从客户端版本**告诉您的用户代理和服务的启动会话的用户使用的客户端版本。
*    **为客户端版本**告诉您的用户代理和目标的会话初始的服务的用户使用的客户端版本。
*    如果会话的电话会议，则**会议 URL**是会议，SIP URL。 在同一会议呼叫中的所有用户将都具有相同的会议 URL。 
*    如果适用，则**从电话号码**是会话的目标电话号码。 最后一个电话号码的数字可能被替换为 x 保护用户隐私。
*    如果适用，则**到电话号码**是会话的目标电话号码。 最后一个电话号码的数字可能被替换为 x 保护用户隐私。
*    **从终结点 Id**是使用从用户的终结点的唯一 GUID。 用于确定是否用户进行通信从同一个终结点的多个会话。 如果用户正在使用 PSTN 电话或从服务启动会话，则可能为空。
*    **为终结点 Id**是使用目标用户的终结点的唯一 GUID。 用于确定是否用户进行通信从同一个终结点的多个会话。 可能为空，如果用户正在使用 PSTN 电话，如果会话启动服务，或未能建立的会话。
*    **会议实例**是会议，通过使用会议 URL 的实例的唯一 GUID。 定期会议将具有相同的会议 URL，但每个会议实例将具有会议实例到任何区别。
*    **代表 URI**是在会话建立的名义 delegator 的 URI。 <br/> **引用由 URI**是用户的引用建立会话的 URI。
*    **响应代码**的会话，该值指示是否已成功建立会话建立的 SIP 响应代码。

为每个会话，具体取决于情况没有具有不同的数据的 sub 表。 下面列出了子表中可用的选项卡，发件人和用户或服务。
*    会话选项卡显示有关机和操作系统的数据。
*    MEDIALINES 选项卡显示网络连接信息和设备的信息。
*    AUDIOSTREAMS 选项卡将显示有关音频流会话所涉及网络性能数据
*    AUDIOCLIENTEVENTS 选项卡显示会影响音频体验的客户端检测到问题有关的数据。
*    AUDIOSIGNALS 选项卡显示有关音频信号会话处理数据。
*    APPSHARINGSTREAMS 选项卡显示有关应用程序共享或桌面共享流的网络性能数据会话所涉及。
*    VIDEOCLIENTEVENTS 选项卡显示会影响视频体验客户端检测到问题有关的数据。
*    VIDEOSTREAMS 选项卡将显示有关的视频流会话所涉及网络性能数据
*    路由追踪选项卡显示在会话过程中 traceroute 通过收集网络跃点数。 用于会话的实际的媒体路径可能有所不同，并且没有音频会话时，此数据才可用。
*    FEEDBACKREPORTS 选项卡显示用户在会话中所提供的呼叫调查数据任何结尾。
***
![第五](../images/sfbcallout5.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。 
***
![第六](../images/sfbcallout6.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype 的业务活动报告](activity-report.md)您可以看到多少您的用户将对等、 组织，和参加会议会话。
    
- [Skype 的业务设备使用情况报告](device-usage-report.md)您可以查看设备包括基于 Windows 的操作系统和移动设备具有业务应用程序 Skype 的安装和使用它的 IM 和会议。
    
- [Skype 的业务会议组织者活动报告](conference-organizer-activity-report.md)您可以看到多少您的用户的组织使用 IM、 音频/视频、 应用程序共享、 Web、 电话拨入/出 — 第三方和电话拨入/出-Microsoft 的会议。
    
- [Skype 的业务会议参与者活动报告](conference-participant-activity-report.md)您可以看到多少 IM、 音频/视频，应用程序共享、 Web 和电话拨入/出会议会议正在参与。
    
- [Skype 的业务对等活动报告](peer-to-peer-activity-report.md)您可以看到多少用户使用 IM、 音频/视频、 应用程序共享和文件传输。
    
- [Skype 的业务 PSTN 使用率报告](pstn-usage-report.md)您可以看到所用的入站/出站呼叫和成本这些呼叫分钟数。

- [适用于业务用户的 Skype 阻止报告](users-blocked-report.md)您可以看到您的组织中被阻止发出 PSTN 呼叫的用户。

- [Skype 业务 PSTN minute 池报表](pstn-minute-pools-report.md)，您可以看到在组织内当前月份消耗的分钟数。
    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 