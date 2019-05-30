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
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 新的 Skype for Business 管理中心报告区域显示你的组织中的通话和音频会议活动。 它使您能够深入查看报表, 让您更细致地了解每个用户的活动。 例如, 您可以使用 Skype for Business PSTN 分钟池报告查看您的组织内当前月份内消耗的分钟数。
ms.openlocfilehash: bfbc21453732d338c4d0cf6355903df344c826f4
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494012"
---
# <a name="pstn-minute-pools-report"></a>PSTN 分钟池报告

>[!NOTE]
>此报告仅供预览客户使用。

新的 Skype for Business 管理中心**报告**区域显示你的组织中的通话和音频会议活动。 它使您能够深入查看报表, 让您更细致地了解每个用户的活动。 例如, 您可以使用**Skype For BUSINESS PSTN 分钟池**报告查看您的组织内当前月份内消耗的分钟数。
  
有关可用报表的详细信息, 请查看[报表概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
  
此报告以及其他 Skype for Business 报表提供了有关组织内活动的详细信息。 在调查、规划和为组织制定其他业务决策以及设置[通信信用点数](/microsoftteams/what-are-communications-credits)时, 这些详细信息非常有用。
  
> [!NOTE]
> [!注释] 以管理员身份登录 Office 365 管理中心后，可以查看所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>如何访问 Skype for Business PSTN 分钟池报告

![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标

- 转到**Office 365 管理中心** > **管理中心** > **Skype for business 管理中心** > **报告** > **PSTN 分钟池**。
    
> [!NOTE]
> 根据你拥有的 Office 365 订阅, 你可能看不到此处显示的所有相同详细信息。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>解释 Skype for Business PSTN 分钟池报告

通过查看显示的每一列, 可以查看用户的 Skype for Business 分钟池。
  
以下是此报告的外观。
  
## 

![Skype for Business PSTN 分钟池报告](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![第一](../images/sfbcallout1.png)<br/>该表显示按许可证 (功能) 和使用位置对分钟池的细分。 
*    **功能**是用于通话的许可证/服务计划。 您可能在此报告中看到的许可证/服务计划包括:
     * MCOPSTN1-国内通话计划 (3000-minute/1200-欧盟计划
     * MCOPSTN2-国内 & 国际通话计划, 您将从该计划中看到一个国内版池 (3000-minute/加拿大/PR, 1200-1-1-1-分钟) 和国际池子 (600-分钟)。 只要在日历月份内达到国内或国际 cap, 就会达到分钟上限。 
     * MCOPSTN5-国内通话计划 (120 分钟通话计划)
     * MCOPSTN6-国内通话计划 (240 分钟通话计划)
     * MCOMEETADD-音频会议
*    **功能说明**是针对通话使用的许可证类型的说明。
*    "**国家/分钟" 池**是共享 "分钟" 池的用户的许可证使用位置。 
*    "已**用分钟**数" 表示每个月使用的分钟数。
*    "**总分钟**数" 表示当月可用的总分钟数。 
*    **使用百分比**是指用于月份的分钟数。 
***
![第二](../images/sfbcallout2.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。 
***
![第三](../images/sfbcallout3.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果您的用户少于 2000, 则可以在报表本身的表中对其进行排序和筛选。 如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype For business 活动报告](activity-report.md)你可以查看你的用户使用对等、组织和参与会议会话的数量。
    
- [Skype For business 设备使用情况报告](device-usage-report.md)你可以查看设备, 包括安装了 Skype for Business 应用的基于 Windows 的操作系统和移动设备并将其用于即时消息和会议。
    
- [Skype for business 会议组织者活动报告](conference-organizer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享、Web、/dial 外接程序和/dial 注销的方式组织的会议量。
    
- [Skype for business 会议参与者活动报告](conference-participant-activity-report.md)你可以查看正在参与的 IM、音频/视频、应用程序共享、Web 和拨出音频会议的数量。
    
- [Skype For business 对等活动报告](peer-to-peer-activity-report.md)你可以查看你的用户使用 IM、音频/视频、应用程序共享和传输文件的数量。
    
- 已[阻止的 Skype for business 用户报告](users-blocked-report.md)你可以查看组织中已阻止进行 PSTN 呼叫的用户。

- [Skype For business 会话详细信息报告](session-details-report.md)你可以查看有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
