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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: 7616e13f81b2b8ec204409f7a90e275dab795742
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592936"
---
# <a name="peer-to-peer-activity-report"></a>对等活动报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

"**报表**"仪表板显示组织中Microsoft 365 Office 365产品的活动概述。 利用它，你可以深入了解各个产品级别的报告，从而更加详细地了解每个产品中的活动。 例如，可以使用Skype for Business活动报告来查看有多少用户使用即时消息、音频、视频、应用程序共享和传输文件。 

请查看报表 [概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
  
此报表以及其他Skype for Business一起提供有关整个组织活动的详细信息。 当你为组织进行调查、规划及执行其他业务决策时，这些详细信息非常有用。 
  
> [!NOTE]
> 以管理员登录 Skype for Business时，可以看到所有报告Microsoft 365 管理中心。 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>如何获取 Skype for Business 对等活动报告

1. 转到管理中心，>**报告**  >  **使用情况"。**
    
2. 在"**使用情况"Skype for Business** 左侧的"选择报表"列表上，选择"对等活动  >  "。  或者，单击Skype for Business **活动** 小组件，Skype for Business活动列表上的"对等Skype for Business **活动**。

## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>解释 Skype for Business 对等活动报告

你可以通过查看" **活动**"、" **用户**"和" **分钟数**"图表了解你的 Skype for Business 对等活动。
  
![Skype标注的对等报表。](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![第一](../images/sfbcallout1.png)<br/>可以查看" **Skype for Business 对等活动**"报告以了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果单击报告中的某一天，则表 (请参阅数字 7) 将显示 30 天的数据，截至日期 (请参阅报告生成时间的第 2) 个数字。

> [!NOTE]
> 如果单击特定日期的详细信息，该表将只显示报告生成日期之前 30 天的数据。

***
![第二](../images/sfbcallout2.png)<br/>每个报表包含此报表的生成日期。 报告通常反映从活动时间到 24 到 48 小时的延迟。 
***
![第三](../images/sfbcallout3.png)<br/>使用" **活动**"图表上的交互式图表数据可了解使用趋势并查看组织中正在进行的每个会话类型的会话总数。 它将显示整个组织的 **即时消息**、音频、视频、应用程序共享和文件传输会话的总数和类型。 
***
![第四](../images/sfbcallout4.png)<br/>使用" **用户**"图表上的交互式图表数据可了解使用趋势并查看参与组织中正在进行的对等活动的单独用户数。 它将显示用户总数，以及对等会话中 **的即时消息**、音频、视频、应用程序共享和文件传输的类型。 
***
![第五](../images/sfbcallout5.png)<br/>使用" **分钟数**"图表上的交互式图表数据可了解使用趋势并查看用户在使用音频和视频进行对等活动时所用的分钟数。它将显示在对等会话中使用的 **音频** 和 **视频** 的总分钟数。
***
![第六](../images/sfbcallout6.png)<br/>每个图表都具有"X"（水平）轴和"Y"（垂直）轴。 
*    在" **活动**"活动图表中，Y 轴代表组织中的用户举行的即时消息、音频、视频、应用程序共享和文件传输会话的总数。
*    在 **"用户** "活动图表中，Y 轴表示保存即时消息、音频、视频、应用程序共享和传输文件会话的用户总数。 
*    在" **分钟数**"活动图表中，Y 轴代表组织中的用户使用音频和视频对等会话的总分钟数。 

这两个图表的 X 轴都表示此特定报表的所选日期范围。
***
![数字 7](../images/sfbcallout7.png)<br/>你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在"活动 **"** 图表上，单击或点击 **"IM"、"** 音频"、"视频"、"应用程序共享"和"文件传输"，仅查看与每个传输相关的信息。    更改此选择不会更改网格表中的信息。 
***
![数字 8](../images/sfbcallout8.png)<br/>该表格显示了按用户细分的对等活动。它将显示所有分配了 Skype for Business 的用户及其对等活动。你可以向该表格中添加其他列。
*    " **用户名**"是用户的名称。
*    " **已删除**"表示用户的许可证已删除。 <br/> <br/> **注意：**  只要已删除用户在所选时段的某个时间获得许可，该用户的活动仍会显示在报告中。 The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.  <br/><br/>
*    **Deleted date** is the date on which the user's license was removed. 
*    " **上次活动日期(UTC)**"是该用户的上次活动日期 (UTC)。
*    " **即时消息**"显示该用户使用的对等会话的总数。
*    " **音频**"显示使用音频的的对等会话的总数。
*    " **视频**"显示使用视频的的对等会话的总数。
*    " **应用程序共享**"显示对等应用程序共享会话的总数。
*    " **文件传输**"显示对等文件传输会话的总数。
*    " **音频分钟数**"显示整个组织使用的音频的总分钟数。 
*    " **视频分钟数**"显示整个组织使用的视频的总分钟数。 

如果您的组织策略阻止您查看可识别用户信息的报表，您可以更改所有这些报表的隐私设置。 请查看管理中心的活动报告中的 **"** 如何隐藏用户 [级别详细信息？"部分](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。 
***
![数字 9](../images/sfbcallout9.png)<br/>你还可以单击或点击" **导出**"按钮，将报告数据导出到 Excel .csv 文件中。           <br/> ![Skype for Business"报告导出"按钮。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。
***
![数字 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>单击或点击任何 **列中** 的"列"图标，在报表中添加或删除列。         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype for Business活动报告](activity-report.md)你可以看到你的用户使用对等会议会话、组织会议会话和参与会议会话的用户数。
    
- [Skype for Business设备使用情况报告](device-usage-report.md)你可以查看设备，包括Windows操作系统和移动设备，这些设备已安装Skype for Business应用，并使用它进行即时消息和会议。
    
- [Skype for Business组织者活动报告](conference-organizer-activity-report.md)你可以看到有多少用户正在组织使用即时消息、音频/视频、应用程序共享、Web、拨入/拨出 - 第三方和拨入/拨出 -Microsoft 的会议。
    
- [Skype for Business会议参与者活动报告](conference-participant-activity-report.md)你可以看到正在参与多少个即时消息、音频/视频、应用程序共享、Web 和电话拨入/拨出式会议。
    
- [Skype for Business用户阻止的报告](users-blocked-report.md)可以看到组织中被阻止进行 PSTN 呼叫的用户。
    
- [Skype for Business PSTN 使用情况报告](pstn-usage-report.md)可以看到在入站/出站调用中花费的分钟数以及这些调用的成本。
    
- [Skype for Business PSTN 分钟](pstn-minute-pools-report.md)数池报告，可以看到组织内部当月使用的分钟数。

- [Skype for Business会话详细信息报告](session-details-report.md)可以看到有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
