---
title: "活动报告"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: 507bb0b2634d25cf2f0b518fa79dcf453afa79a4
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="activity-report"></a>活动报告

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 它使您能够钻到各个产品级别报告，使您更精确地了解每种产品中的活动。 例如，您可以使用**Skype 业务活动**报告以查看您的用户使用对等的多少或组织会议会话或多少他们正在参与会议会话。 

检出[报告概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以了解详细信息。
  
本报告中的，以及其他 Skype 业务报表，提供您详细信息活动整个组织。 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。
  
> [!NOTE]
> 在 Office 365 管理中心管理员身份登录时，可以看到所有的业务报表 Skype。 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>如何访问 Skype for Business 活动报告

1. 请转到**Office 365 管理中心** > **报告** > **的使用**。
    
2. 在**使用**页上，单击**选择报表的列表**在左边，在**Skype 的业务活动**，或单击**Skype 业务活动**构件。
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > 这取决于您拥有 Office 365 订阅，您可能看不到所有产品和此处所示的报告。 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>解释 Skype for Business 活动报告

可通过查看" **活动**"和" **用户**"图表，了解用户的 Skype for Business 活动。
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>
可以查看" **Skype for Business 活动**"报告以了解过去 7 天、30 天、90 天或 180 天的趋势。

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![2 号](../images/sfbcallout2.png)<br/>
每个报表包含此报表的生成日期。 该报告通常反映活动的时间从 24 到 48 小时延迟。 
***
![数字 3](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的会话活动数。它将显示在整个组织中" **对等会话**"、" **组织**"和" **参与**"会议会话的总数和类型。 
***
![数字 4](../images/sfbcallout4.png)<br/>
使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在举行的会议活动的唯一用户数。 它将显示您的**对等会话**、**组织**和**Participated**的类型以及用户总数在讲座中。
***
![数字 5](../images/sfbcallout5.png)<br/>
你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在**活动**图中，单击或点击只与每个相关的信息，请参阅**对等会话**、**有组织**或**Participated** 。 更改此选择不会更改网格表中的信息。 
***
![数字 6](../images/sfbcallout6.png)<br/>
每个图表都具有"X"（水平）轴和"Y"（垂直）轴。
*    在**活动**图中，Y 轴是对等，组织，并参加了正在举办的讲座的总数。
*    **用户**活动图中，Y 轴为点到点的每个类型中参加的唯一用户数组织，并参加会议。

这两个图表的 X 轴都表示此特定报表的所选日期范围。 
***
![数字 7](../images/sfbcallout7.png)<br/>
下表显示了每个用户的所有会议活动的细目分类。 这将显示所有用户都有分配给他们和他们的会议活动的业务的 Skype。 你可以向该表格中添加其他列。
*    **用户名**是用户的名称。
*    " **已删除**"表示用户的许可证已删除。 <br/> <br/> **注意：**只要他或她被授权在所选的时间段的某些时候，报告中仍会显示已删除的用户的活动。 The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.<br/><br/>
*    **Deleted date** is the date on which the user's license was removed.
*    " **上次活动日期(UTC)**"是该用户最近参与对等会话、组织或参与会议的时间。
*    **对等**显示该用户所使用的对等会议会话的总数。
*    " **组织会议**"显示该用户组织的会议的总数。
*    " **参与会议**"显示该用户参与的会议总数。
*    " **分配的产品**"表示分配给此用户的 Office 365 产品。<br/>

如果您的组织策略阻止您查看报表可识别用户信息在哪里，您可以更改所有这些报告的隐私设置。 签出[在 Office 365 管理中心活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)中**隐藏报表中的用户详细信息**一节。
***
![数字 8](../images/sfbcallout8.png)<br/>
单击或点击任何要添加或删除报表中的列的列的**列**图标。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![数字 9](../images/sfbcallout9.png)<br/>
你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> ![Skype 业务报告的导出按钮。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果您有少于 2000年用户，您可以排序和筛选报告本身中的表内。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype 的业务设备使用情况报告](device-usage-report.md)您可以查看的设备，其中包括基于 Windows 的操作系统和 Skype 的业务应用程序的移动设备安装，并将其用于即时消息和会议。
    
- [Skype 业务会议组织者活动报告](conference-organizer-activity-report.md)您可以看到您的用户多少组织使用 IM，音频/视频、 应用程序共享，Web，拨入/出 — 第三方，并拨入/出-Microsoft 的会议。
    
- [Skype 业务对等活动报告](peer-to-peer-activity-report.md)您可以看到您的用户使用 IM，音频/视频、 应用程序共享和文件传输的多少。
    
- [适用于业务用户的 Skype 阻塞报表](users-blocked-report.md)您可以查看组织中的用户进行 PSTN 呼叫已被阻止。
    
- [Skype 的业务 PSTN 使用情况报告](pstn-usage-report.md)您可以看到所花费的入站/出站呼叫和成本为这些调用的分钟数。

- [Skype 业务 PSTN 分钟池报告](pstn-minute-pools-report.md)您可以看到在本月组织内消耗的分钟数。

- [Skype 的业务会话详细信息报告](session-details-report.md)您可以查看有关单个用户的呼叫体验的详细信息。

    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

## <a name="feedback"></a>反馈意见？
提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。