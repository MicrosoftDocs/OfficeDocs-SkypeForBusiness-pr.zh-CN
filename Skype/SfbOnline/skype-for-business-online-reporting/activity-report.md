---
title: 活动报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: d13ca7f70880d7ad0f3c6376e167c6222682887d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855572"
---
# <a name="activity-report"></a>活动报告

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 使您能够钻取到单个产品级别报表，以使您更精细了解每种产品中的活动。 例如，您可以使用**的业务活动的 Skype**报表来查看多少用户使用对等或组织会议会话，或多少它们您加入会议会话。 

签出[报告概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以了解详细信息。
  
此报告中的，以及其他 Skype 业务报告为您提供了详细信息活动在整个组织。 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。
  
> [!NOTE]
> 在 Office 365 管理中心中的管理员在登录时，您可以查看所有业务报告 Skype。 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>如何访问 Skype for Business 活动报告

1. 转到**Office 365 管理中心** > **报告** > **使用率**。
    
2. 在**使用率**页中，单击**业务活动的 Skype**上**选择报告列表**上的左侧，或单击**业务活动的 Skype**小部件。
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > 根据您具有的 Office 365 订阅，不可能会看到所有产品和报告如下所示。 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>解释 Skype for Business 活动报告

可通过查看" **活动**"和" **用户**"图表，了解用户的 Skype for Business 活动。
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![第一](../images/sfbcallout1.png)<br/>
**Skype 的业务活动**电子邮件活动报告可以在最近 7 天，30 天，90 天或 180 天内的趋势查看。 但是，如果您单击到报告中某一天，表 （请参阅 7 号） 将显示数据最多 28 天从当前日期 （不生成报告的日期）。

> [!NOTE]
> 如果您单击到特定日期的详细信息，表将仅显示报告生成的时间的日期最 30 天内的数据。

***
![第二](../images/sfbcallout2.png)<br/>
每个报表包含此报表的生成日期。 报表通常反映活动的时间从 24 到 48 小时延迟。 
***
![第三](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的会话活动数。它将显示在整个组织中" **对等会话**"、" **组织**"和" **参与**"会议会话的总数和类型。 
***
![第四](../images/sfbcallout4.png)<br/>
使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在举行的会议活动的唯一用户数。 它将显示您的**对等会话**、**有组织**和**Participated**类型以及用户总数会议会话中。
***
![第五](../images/sfbcallout5.png)<br/>
你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在**活动**图表中，单击或点击**对等会话**、**有组织**或**Participated**以查看仅与每个相关的信息。 更改此选择不会更改网格表中的信息。 
***
![第六](../images/sfbcallout6.png)<br/>
每个图表都具有"X"（水平）轴和"Y"（垂直）轴。
*    在**活动**图表中，Y 轴是-对等，组织，并且参与保留的会议会话的总数。
*    在**用户**活动图表中，Y 轴是参加中每种类型的点到点的唯一用户数组织，并且参加会议。

这两个图表的 X 轴都表示此特定报表的所选日期范围。 
***
![7 号](../images/sfbcallout7.png)<br/>
下表显示了每个用户的所有会议活动的细分。 此时将显示已分配给它们和其会议活动的业务的 Skype 的所有用户。 你可以向该表格中添加其他列。
*    **Username**是用户的名称。
*    " **已删除**"表示用户的许可证已删除。<br/><br/>
    > [!NOTE]
    > 只要他或她已授权的过程选定的时间段中的某个时间，已删除的用户的活动仍会显示在报表中。 The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.
     
*    **Deleted date** is the date on which the user's license was removed.
*    " **上次活动日期(UTC)**"是该用户最近参与对等会话、组织或参与会议的时间。
*    **对等**显示的用户使用的对等会议会话的总数。
*    " **组织会议**"显示该用户组织的会议的总数。
*    " **参与会议**"显示该用户参与的会议总数。
*    " **分配的产品**"表示分配给此用户的 Office 365 产品。<br/>

如果贵组织的策略阻止您查看报告可识别用户信息在哪里，您可以更改所有这些报告的隐私设置。 签出[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)中的**隐藏用户在报告的详细信息**一节。
***
![8 号](../images/sfbcallout8.png)<br/>
单击或点击中的任何列添加或从报表中删除列**列**图标。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![数字 9](../images/sfbcallout9.png)<br/>
你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> ![用于业务报告的 Skype 导出按钮。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果您有超过 2000年用户，您可以排序和筛选报告本身中的表中。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype 的业务设备使用情况报告](device-usage-report.md)您可以查看设备，包括基于 Windows 的操作系统和具有业务应用程序 Skype 的移动设备安装并使用其为 IM 和会议。
    
- [Skype 的业务会议组织者活动报告](conference-organizer-activity-report.md)您可以看到多少您的用户的组织使用 IM、 音频/视频、 应用程序共享、 Web、 电话拨入/出 — 第三方和电话拨入/出-Microsoft 的会议。
    
- [Skype 的业务对等活动报告](peer-to-peer-activity-report.md)您可以看到多少用户使用 IM、 音频/视频，应用程序共享和文件传输。
    
- [适用于业务用户的 Skype 阻止报告](users-blocked-report.md)您可以看到您的组织中被阻止发出 PSTN 呼叫的用户。
    
- [Skype 的业务 PSTN 使用率报告](pstn-usage-report.md)您可以看到所用的入站/出站呼叫和成本这些呼叫分钟数。

- [Skype 业务 PSTN minute 池报表](pstn-minute-pools-report.md)，您可以看到在组织内当前月份消耗的分钟数。

- [Skype 业务会话详细信息报表](session-details-report.md)您可以看到有关单个用户的呼叫体验的详细信息。

    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
