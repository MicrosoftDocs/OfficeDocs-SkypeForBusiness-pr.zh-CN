---
title: 对等活动报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.custom:
- Reporting
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: 6564c57cee0821aa0e9204692f160b154ee5513b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792647"
---
# <a name="peer-to-peer-activity-report"></a>对等活动报告

全新的 Office 365" **报告**"仪表板会为你显示组织中不同 Office 365 产品上所发生活动的概况。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。 例如, 您可以使用**Skype For business 对等活动**报告查看用户使用 IM、音频、视频、应用程序共享和传输文件的程度。 

查看[报表概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
  
此报告以及其他 Skype for Business 报表提供了有关组织内活动的详细信息。 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。 
  
> [!NOTE]
> 当您以管理员身份登录到 Microsoft 365 管理中心时, 您可以看到所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>如何获取 Skype for Business 对等活动报告

1. 转到管理中心 >**报告** > **使用情况**。
    
2. 在 "**使用情况**" 页面上, 单击左侧的 "**选择报表" 列表**中的 " **Skype for business 对等活动**"。 或者, 单击 " **skype For business 活动**" 小组件, 然后单击 "skype for business**活动**" 列表上的 " **skype for business 对等活动**"。
    
     ![已选中 "Skype 对等" 菜单](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > [!重要信息] 你可能无法看到此处所示的所有产品和活动报告，具体取决于你拥有的 Office 365 订阅。 
  
## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>解释 Skype for Business 对等活动报告

你可以通过查看" **活动**"、" **用户**"和" **分钟数**"图表了解你的 Skype for Business 对等活动。
  
![带有标注的 Skype 对等报表。](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![第一](../images/sfbcallout1.png)<br/>可以查看" **Skype for Business 对等活动**"报告以了解过去 7 天、30 天、90 天或 180 天的趋势。 但是, 如果你单击报表中的某一特定日, 则该表 (请参阅数字 7) 将在生成报表时显示30天 (请参阅数字 2) 的数据。

> [!NOTE]
> 如果单击某一特定日的详细信息, 则该表将仅显示生成报表的日期之前30天内的数据。

***
![第二](../images/sfbcallout2.png)<br/>每个报表包含此报表的生成日期。 报告通常反映来自活动时间的24至48小时延迟。 
***
![第三](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的每个会话类型的会话总数。 它将显示你的组织内的**即时消息**、**音频**、**视频**、**应用程序共享**和**文件传输**会话的总数和类型。 
***
![第四](../images/sfbcallout4.png)<br/>使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在进行的对等活动的单独用户数。 它将向你显示对等会话中的用户总数以及**IM**、**音频**、**视频**、**应用程序共享**和**文件传输**的类型。
***
![第五](../images/sfbcallout5.png)<br/>使用" **分钟数**"图表上的交互式图表数据可了解使用趋势并查看用户在使用音频和视频进行对等活动时所用的分钟数。它将显示在对等会话中使用的 **音频**和 **视频**的总分钟数。
***
![第六](../images/sfbcallout6.png)<br/>每个图表都具有"X"（水平）轴和"Y"（垂直）轴。 
*    在" **活动**"活动图表中，Y 轴代表组织中的用户举行的即时消息、音频、视频、应用程序共享和文件传输会话的总数。
*    在 "**用户**" 活动图表上, Y 轴表示保持 IM、音频、视频、应用程序共享和传输文件会话的总用户数。 
*    在" **分钟数**"活动图表中，Y 轴代表组织中的用户使用音频和视频对等会话的总分钟数。 

这两个图表的 X 轴都表示此特定报表的所选日期范围。
***
![数字7](../images/sfbcallout7.png)<br/>你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如, 在 "**活动**" 图表上, 单击或点击 " **IM**"、"**音频**"、"**视频**"、"**应用程序共享**和**文件传输**", 以仅查看与每个文件相关的信息。 更改此选择不会更改网格表中的信息。 
***
![数字8](../images/sfbcallout8.png)<br/>该表格显示了按用户细分的对等活动。它将显示所有分配了 Skype for Business 的用户及其对等活动。你可以向该表格中添加其他列。
*    " **用户名**"是用户的名称。
*    " **已删除**"表示用户的许可证已删除。 <br/> <br/> **注意:** 只要在所选时间段内有一段时间的许可, 已删除用户的活动仍将显示在报表中。 The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.  <br/><br/>
*    **Deleted date** is the date on which the user's license was removed. 
*    " **上次活动日期(UTC)**"是该用户的上次活动日期 (UTC)。
*    " **即时消息**"显示该用户使用的对等会话的总数。
*    " **音频**"显示使用音频的的对等会话的总数。
*    " **视频**"显示使用视频的的对等会话的总数。
*    " **应用程序共享**"显示对等应用程序共享会话的总数。
*    " **文件传输**"显示对等文件传输会话的总数。
*    " **音频分钟数**"显示整个组织使用的音频的总分钟数。 
*    " **视频分钟数**"显示整个组织使用的视频的总分钟数。 

如果你的组织的策略阻止你查看用户信息可标识的报表, 你可以更改所有这些报表的隐私设置。 查看[管理中心的活动报表中](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)的 "**如何隐藏用户级别的详细信息？** " 部分。 
***
![数字9](../images/sfbcallout9.png)<br/>你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> !["Skype for business 报告导出" 按钮。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。
***
![数字10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>单击或点击任何列中的 "**列**" 图标, 在报表中添加或删除列。         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype For business 活动报告](activity-report.md)你可以查看你的用户使用对等、组织和参与会议会话的数量。
    
- [Skype For business 设备使用情况报告](device-usage-report.md)你可以查看设备, 包括安装了 Skype for Business 应用的基于 Windows 的操作系统和移动设备并将其用于即时消息和会议。
    
- [Skype for business 会议组织者活动报告](conference-organizer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享、Web、拨入/拨出和拨入/拨出的方式组织会议的程度。
    
- [Skype for business 会议参与者活动报告](conference-participant-activity-report.md)你可以查看参与的即时消息、音频/视频、应用程序共享、Web 和电话拨入/拨出式会议会议的数量。
    
- 已[阻止的 Skype for business 用户报告](users-blocked-report.md)你可以查看组织中已阻止进行 PSTN 呼叫的用户。
    
- [Skype for BUSINESS PSTN 使用报告](pstn-usage-report.md)您可以查看入站/出站通话所用的分钟数和这些通话的费用。
    
- [Skype For BUSINESS PSTN 分钟池报告](pstn-minute-pools-report.md)您可以查看在您的组织内的当前月份内消耗的分钟数。

- [Skype For business 会话详细信息报告](session-details-report.md)你可以查看有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报表](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 