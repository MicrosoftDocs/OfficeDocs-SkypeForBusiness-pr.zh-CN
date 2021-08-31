---
title: PSTN 分钟池报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: 新的Skype for Business管理中心报告"区域显示你组织的呼叫和音频会议活动。 它使你能够深入了解报表，从而更细致地了解每个用户的活动。 例如，可以使用 PSTN Skype for Business报告查看组织内部当月使用的分钟数。
ms.openlocfilehash: d3b75fd81628e4cfcd49b7b120ceed3e3f327bdc
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727991"
---
# <a name="pstn-minute-pools-report"></a>PSTN 分钟池报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>此报告仅适用于预览版客户。

新的Skype for Business管理中心 **报告**"区域显示你组织的呼叫和音频会议活动。 它使你能够深入了解报表，从而更细致地了解每个用户的活动。 例如，可以使用 **PSTN** Skype for Business报告查看组织内部当月使用的分钟数。
  
有关更多 [可用报表，](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 请查看报表概述。
  
此报表以及其他Skype for Business一起提供有关整个组织活动的详细信息。 在调查、规划和为组织做出其他业务决策以及设置通信信用额度时，这些详细信息非常有用[](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> 以管理员角色登录到 Skype for Business时，可以看到所有Microsoft 365 管理中心。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>如何访问 PSTN Skype for Business报告

![一个图标，显示Skype for Business徽标。](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

- 转到管理中心>**管理Skype for Business**  >  **报告**  >    >  **PSTN 分钟池**。
    
> [!NOTE]
> 根据你Microsoft 365或Office 365订阅，可能看不到此处显示的所有相同详细信息。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>解释 PSTN Skype for Business池报告

通过查看显示的每个列，Skype for Business分钟池的视图。
  
以下是此报告的外观。

![Skype for BusinessPSTN 分钟池报告。](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![数字 1。](../images/sfbcallout1.png)<br/>下表按许可证和使用位置 (分钟) 池。 
*    **功能** 是用于调用的许可证/服务计划。 可以在此报告中看到的许可证/服务计划包括：
     * MCOPSTN1 - 国内呼叫 (3000 分钟美国/1200 分钟欧盟计划
     * MCOPSTN2 - 国内 & 国际呼叫计划，你将看到国内池 (3000 分钟美国/加拿大/PR、1200 分钟的欧洲国家/地区) 以及一个 600 分钟的国际池 () 。 只要在日历月达到国内 -OR- 国际上限，就会达到分钟数上限。 
     * MCOPSTN5 - 国内呼叫 (120 分钟的呼叫计划) 
     * MCOPSTN6 - 国内呼叫 (240 分钟呼叫计划) 
     * MCOMEETADD - 音频会议
*    **功能** 说明是调用使用的许可类型的说明。
*    **国家/** 地区分钟池是共享分钟池 (用户) 许可证使用位置。 
*    **"已** 用分钟数"是每月使用的分钟数。
*    **总分钟** 数是当月可用的总分钟数。 
*    **"已** 用百分比"表示当月使用的分钟数百分比。 
***
![数字 2。](../images/sfbcallout2.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。 
***
![数字 3。](../images/sfbcallout3.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果用户数少于 2000，可以在报表本身的表中进行排序和筛选。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype for Business活动报告](activity-report.md)你可以看到你的用户使用对等会议会话、组织会议会话和参与会议会话的用户数。
    
- [Skype for Business设备使用情况报告](device-usage-report.md)你可以查看设备，包括Windows操作系统和移动设备，这些设备已安装Skype for Business应用，并使用它进行即时消息和会议。
    
- [Skype for Business会议组织者活动报告](conference-organizer-activity-report.md)可以看到有多少用户正在组织使用即时消息、音频/视频、应用程序共享、Web、/拨出 - 第三方和 /dial out - Microsoft 的会议。
    
- [Skype for Business参与者活动报告](conference-participant-activity-report.md)可以看到正在参与多少个即时消息、音频/视频、应用程序共享、Web 和拨出音频会议。
    
- [Skype for Business对等活动报告](peer-to-peer-activity-report.md)可以看到有多少用户使用即时消息、音频/视频、应用程序共享和传输文件。
    
- [Skype for Business用户阻止的报告](users-blocked-report.md)可以看到组织中被阻止进行 PSTN 呼叫的用户。

- [Skype for Business会话详细信息报告](session-details-report.md)可以看到有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
