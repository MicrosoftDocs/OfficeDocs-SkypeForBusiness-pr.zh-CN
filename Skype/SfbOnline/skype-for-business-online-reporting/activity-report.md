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
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: df46f6a8fa029936911d8cafd463e683d25b4551
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298015"
---
# <a name="activity-report"></a>活动报告

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 它使您能够深入查看各个产品级别的报表, 让您更细致地了解每个产品内的活动。 例如, 你可以使用**Skype For business 活动**报表查看你的用户使用的是对等会议会话还是组织的会议会话的数量, 或者他们参与会议会话的数量。 

查看[报表概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以了解详细信息。
  
此报告以及其他 Skype for Business 报表提供了有关组织内活动的详细信息。 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。
  
> [!NOTE]
> 在 Office 365 管理中心中以管理员身份登录时, 你可以看到所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>如何访问 Skype for Business 活动报告

1. 转到**Office 365 管理中心** > **报告** > **使用率**。
    
2. 在 "**使用情况**" 页面上, 单击左侧的 "**选择报表" 列表**中的 " **Skype for business 活动**", 或单击 " **skype for business 活动**" 小组件。
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > 根据你拥有的 Office 365 订阅, 你可能无法看到此处所示的所有产品和报告。 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>解释 Skype for Business 活动报告

可通过查看" **活动**"和" **用户**"图表，了解用户的 Skype for Business 活动。
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![第一](../images/sfbcallout1.png)<br/>
可以查看 " **Skype For Business 活动**电子邮件活动" 报表, 了解过去7天、30天、90天或180天的趋势。 但是, 如果你单击报表中的某一特定日, 则该表 (请参阅数字 7) 将显示当前日期最多28天 (而不是报告生成日期) 的数据。

> [!NOTE]
> 如果单击某一特定日的详细信息, 则该表将仅显示生成报表的日期之前30天内的数据。

***
![第二](../images/sfbcallout2.png)<br/>
每个报表包含此报表的生成日期。 报告通常反映来自活动时间的24至48小时延迟。 
***
![第三](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的会话活动数。它将显示在整个组织中" **对等会话**"、" **组织**"和" **参与**"会议会话的总数和类型。 
***
![第四](../images/sfbcallout4.png)<br/>
使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在举行的会议活动的唯一用户数。 它将向你显示用户总数以及**对等会话**的类型、**组织**的和**参与**会议会话的用户数。
***
![第五](../images/sfbcallout5.png)<br/>
你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如, 在 "**活动**" 图表上, 单击或点击 "**对等会话**"、"已**组织**" 或 "已**参与**", 以仅查看与每个会话相关的信息。 更改此选择不会更改网格表中的信息。 
***
![第六](../images/sfbcallout6.png)<br/>
每个图表都具有"X"（水平）轴和"Y"（垂直）轴。
*    在 "**活动**" 图表上, Y 轴表示已举行的会议会话的对等、组织和参与的总数。
*    在 "**用户**" 活动图表上, Y 轴是参与每种类型的对等、组织和参与会议的唯一用户数。

这两个图表的 X 轴都表示此特定报表的所选日期范围。 
***
![数字7](../images/sfbcallout7.png)<br/>
此表显示了每个用户的所有会议活动细目。 此图显示了分配有 Skype for Business 的所有用户及其会议活动。 你可以向该表格中添加其他列。
* **用户名**是用户的名称。
* " **已删除**"表示用户的许可证已删除。<br/><br/>
  > [!NOTE]
  > 只要在所选时间段内有一段时间的许可, 已删除用户的活动仍将显示在报表中。 The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.
     
* **Deleted date** is the date on which the user's license was removed.
* " **上次活动日期(UTC)**"是该用户最近参与对等会话、组织或参与会议的时间。
* **对等**显示用户使用的对等会议会话的总数。
* " **组织会议**"显示该用户组织的会议的总数。
* " **参与会议**"显示该用户参与的会议总数。
* " **分配的产品**"表示分配给此用户的 Office 365 产品。<br/>

如果你的组织的策略阻止你查看用户信息可标识的报表, 你可以更改所有这些报表的隐私设置。 查看[Office 365 管理中心的活动报表](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)中 "报表" 部分中的 "**隐藏用户详细信息**"。
***
![数字8](../images/sfbcallout8.png)<br/>
单击或点击任何列中的 "**列**" 图标, 在报表中添加或删除列。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![数字9](../images/sfbcallout9.png)<br/>
你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> !["Skype for business 报告导出" 按钮。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果您的用户少于 2000, 则可以在报表本身的表中对其进行排序和筛选。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype For business 设备使用情况报告](device-usage-report.md)你可以查看安装了 Skype for Business 应用并将其用于即时消息和会议的设备, 包括基于 Windows 的操作系统和移动设备。
    
- [Skype for business 会议组织者活动报告](conference-organizer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享、Web、拨入/拨出和拨入/拨出的方式组织会议的程度。
    
- [Skype For business 对等活动报告](peer-to-peer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享和传输文件的量。
    
- 已[阻止的 Skype for business 用户报告](users-blocked-report.md)你可以查看组织中已阻止进行 PSTN 呼叫的用户。
    
- [Skype for BUSINESS PSTN 使用报告](pstn-usage-report.md)您可以查看入站/出站通话所用的分钟数和这些通话的费用。

- [Skype For BUSINESS PSTN 分钟池报告](pstn-minute-pools-report.md)您可以查看在您的组织内的当前月份内消耗的分钟数。

- [Skype For business 会话详细信息报告](session-details-report.md)你可以查看有关单个用户的呼叫体验的详细信息。

    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
