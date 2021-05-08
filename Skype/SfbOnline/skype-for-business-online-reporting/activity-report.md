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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 094d947088b1a1fea4a8585e09bdedfa6ffe2a2b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238308"
---
# <a name="activity-report"></a>活动报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

"**报表**"仪表板显示组织中Microsoft 365或Office 365活动概述。 它使你能够深入到各个产品级报告，从而更细致地了解每个产品内的活动。 例如，可以使用 Skype for Business 活动报告来查看使用对等或组织的会议会话的用户数量，或者他们参与会议会话的量。 

有关详细信息 [，请查看报表](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 概述。
  
此报表以及其他Skype for Business一起提供有关整个组织活动的详细信息。 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。
  
> [!NOTE]
> 在管理中心以管理员Skype for Business登录时，可以看到所有Microsoft 365报表。 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>如何访问 Skype for Business 活动报告

1. 转到管理中心，>**报告**  >  **使用情况"。**
    
2. 在"**使用情况"** 页上Skype for Business选择"选择报表"列表上的"活动"，或单击"Skype for Business  >  **活动小** 组件"。 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>解释 Skype for Business 活动报告

可通过查看" **活动**"和" **用户**"图表，了解用户的 Skype for Business 活动。
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![第一](../images/sfbcallout1.png)<br/>
可以查看 **Skype for Business** 活动电子邮件活动报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果单击报告中的某一天，则表 (请参阅数字 7) 将显示从当前日期开始最多 28 天的数据 (而不是报告生成日期) 。

> [!NOTE]
> 如果单击特定日期的详细信息，该表将只显示报告生成日期之前 30 天的数据。

***
![第二](../images/sfbcallout2.png)<br/>
每个报表包含此报表的生成日期。 报告通常反映从活动时间到 24 到 48 小时的延迟。 
***
![第三](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的会话活动数。它将显示在整个组织中" **对等会话**"、" **组织**"和" **参与**"会议会话的总数和类型。 
***
![第四](../images/sfbcallout4.png)<br/>
使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在举行的会议活动的唯一用户数。 它将显示用户总数以及对等会话、组织的会议会话和已 **参与会议** 会话的类型。  
***
![第五](../images/sfbcallout5.png)<br/>
你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在"活动 **"** 图表上，单击或点击"对等会话、已组织"或"参与"，仅查看与每个会话相关的信息。  更改此选择不会更改网格表中的信息。 
***
![第六](../images/sfbcallout6.png)<br/>
每个图表都具有"X"（水平）轴和"Y"（垂直）轴。
*    在 **"活动** "图表中，Y 轴表示点对点、组织并参与已召开的会议会话的总数。
*    在 **"用户** "活动图表中，Y 轴表示参与每种类型的对等会议、组织会议以及参与会议的唯一用户数。

这两个图表的 X 轴都表示此特定报表的所选日期范围。 
***
![数字 7](../images/sfbcallout7.png)<br/>
下表显示了每个用户的所有会议活动的细分。 这会显示分配Skype for Business的所有用户及其会议活动。 你可以向该表格中添加其他列。
* **用户名** 是用户的名称。
* " **已删除**"表示用户的许可证已删除。<br/><br/>
  > [!NOTE]
  > 只要已删除用户在所选时段的某个时间获得许可，该用户的活动仍会显示在报告中。 The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.
     
* **Deleted date** is the date on which the user's license was removed.
* " **上次活动日期(UTC)**"是该用户最近参与对等会话、组织或参与会议的时间。
* **对等显示** 用户使用的对等会议会话总数。
* " **组织会议**"显示该用户组织的会议的总数。
* " **参与会议**"显示该用户参与的会议总数。
* **分配的产品** 是Microsoft 365 Office 365用户的产品。<br/>

如果您的组织策略阻止您查看可识别用户信息的报表，您可以更改所有这些报表的隐私设置。 查看管理 **中心中的活动报告** 中的"在报表中 [隐藏用户详细信息"部分](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
***
![数字 8](../images/sfbcallout8.png)<br/>
单击或点击任何 **列中** 的"列"图标，在报表中添加或删除列。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![数字 9](../images/sfbcallout9.png)<br/>
你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> ![Skype for Business"报告导出"按钮。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果用户数少于 2000，可以在报表本身的表中进行排序和筛选。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype for Business设备使用情况报告](device-usage-report.md)你可以查看安装了 Windows 应用并用于即时消息和会议的Skype for Business，包括基于操作系统和移动设备的设备。
    
- [Skype for Business组织者活动报告](conference-organizer-activity-report.md)可以看到有多少用户正在组织使用即时消息、音频/视频、应用程序共享、Web、拨入/拨出 - 第三方和拨入/拨出 -Microsoft 的会议。
    
- [Skype for Business对等活动报告](peer-to-peer-activity-report.md)可以看到有多少用户使用即时消息、音频/视频、应用程序共享和传输文件。
    
- [Skype for Business用户阻止的报告](users-blocked-report.md)可以看到组织中被阻止进行 PSTN 呼叫的用户。
    
- [Skype for Business PSTN 使用情况报告](pstn-usage-report.md)可以看到入站/出站呼叫花费的时间以及这些调用的成本。

- [Skype for Business PSTN 分钟](pstn-minute-pools-report.md)数池报告，可以看到组织内部当月使用的分钟数。

- [Skype for Business会话详细信息报告](session-details-report.md)可以看到有关单个用户的呼叫体验的详细信息。

    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
