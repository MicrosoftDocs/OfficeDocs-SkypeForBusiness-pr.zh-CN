---
title: PSTN 使用率报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
description: 新 Skype 业务管理中心报告区域显示您呼叫和音频会议活动在组织中。 使您钻取报告为您提供更精细了解每个用户的活动。 例如，你可以使用 Skype for Business PSTN 使用详细信息报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 您可以查看音频会议的 PSTN 用法详细信息，包括呼叫的成本，以便您可以了解您的使用，并调用帐单的详细信息，以确定您的组织内的使用情况。
search.appverid: MET150
ms.openlocfilehash: 59a1fbae9614fa6742f73b46c442d7912c71f88d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19973365"
---
# <a name="pstn-usage-report"></a>PSTN 使用率报告

新 Skype Business Admin Center**报告**区域显示您呼叫和音频会议活动在组织中。 使您钻取报告为您提供更精细了解每个用户的活动。 例如，你可以使用 **Skype for Business PSTN 使用详细信息**报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 您可以查看音频会议的 PSTN 用法详细信息，包括呼叫的成本，以便您可以了解您的使用，并调用帐单的详细信息，以确定您的组织内的使用情况。
  
签出[报告概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)可用的详细报告。
  
此报告中的，以及其他 Skype 业务报告提供有关活动包括在整个组织中调用使用率详细信息。 当您调查，规划，以及使其他业务决策为您的组织和设置[Communications 字幕式](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)，很有帮助这些详细信息
  
> [!NOTE]
> [!注释] 以管理员身份登录 Office 365 管理中心后，可以查看所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>如何获取 Skype for Business PSTN 使用详细信息报告

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**

- 转到**Office 365 管理中心** > **管理中心** > **业务管理中心的 Skype** > **报告** > **PSTN 用法详细信息**。
    
    > [!NOTE]
    > [!重要信息] 你可能无法看到此处所示的所有产品和报告，具体取决于你拥有的 Office 365 订阅。 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>解释 Skype for Business PSTN 使用情况报告

你可以通过查看显示的每一列了解用户的 Skype for Business PSTN 使用情况。
  
以下是此报告的外观。
  
![Skype for Business PSTN 使用报告](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![1 号](../images/sfbcallout1.png)<br/>该表格显示了按用户细分的全部 PSTN 使用情况。 此时将显示已分配给它们和其 PSTN 用法的业务的 Skype 的所有用户。 你可以添加/删除表格的列。
*    **呼叫 ID**是呼叫的呼叫 ID。 它是调用 Microsoft 服务支持时使用的呼叫的唯一标识符。
*    " **用户 ID**"是用户的登录名。
*    **电话号码**是 Skype 接收入站呼叫的呼叫的商务电话号码或拨出站呼叫的号码。
*    **用户位置**为用户所在的国家/地区。
*    **呼叫者 ID**将呼叫者的电话号码 (呼叫者 ID) 为入站呼叫，从数目的发起调用或业务呼叫源自出站呼叫的号码 Skype。
*    **呼叫类型**是呼叫的呼叫是否已传出或传入 PSTN 呼叫和因用户或音频会议发出，如呼叫类型。 您可能会看到的呼叫类型包括： 

     **呼叫计划呼叫类型** 
     *    **user_in**（用户已接收的入站的 PSTN 呼叫） 
     *    **user_out**（用户发起出站 PSTN 呼叫） 
     *    **user_out_conf**（用户添加到如 3 路电话会议呼叫 2 或更多 PSTN 参与者） 
     *    **user_out_transfer**（用户已将呼叫转移到 PSTN 号码） 
     *    **user_out_forwarding**（用户转发呼叫 PSTN 号码）

     **音频会议呼叫类型**
     *    **conf_in**（入站的呼叫到音频会议桥） 
     *    **conf_out**（出站呼叫从音频会议网桥通常以向会议添加 PSTN 号码）

     **统一的通信应用程序 (UCAP)** 
     *    **ucap_in**（如自动助理或呼叫的队列的 UC 应用程序对入站的调用） 
     *    **ucap_out**（出站呼叫从如自动助理或呼叫的队列的 UC 应用程序）
*     
     **国内/国际**告诉您是否已发出的呼叫被视为国内 （在国家/地区） 或国际 （之外的国家/地区） 基于用户的位置。 
*    **拨打的目标**是国家/地区目标如法国、 德国或美国 （美国） 时所拨打的名称。 
*    **数字类型**是一种从用户的电话号码、 服务或免费电话号码的电话号码。  
*    " **开始时间(UTC)**"是开始或拨打呼叫的时间。 
*    " **持续时间**"是接听呼叫的时间。  
*    **ConfID**是音频会议的会议 ID。 
*    **根据收费**的金额或呼叫会记入您的帐户的成本。 
*    **货币**是货币的呼叫的一种用于计算的成本。 
*    **功能**是用于呼叫的许可证。 您可能会看到的许可证类型包括： 
     *    **MCOPSTNPP** -Communications 字幕式 <br/> **MCOPSTN1** -国内调用规划 (3000 min 美国 / 1200 min 欧盟计划) 
     *    **MCOPSTN2** -国际呼叫计划 
     *    **MCOPSTN5** -国内调用计划 （120 分钟调用计划） 
     *    **MCOPSTN6** -国内调用计划 （240 分钟调用计划） 的说明： 有限的状态
     *    **MCOMEETADD** -音频会议
     *    **MCOMEETACPEA** -付薪每分钟的音频会议 
***
![2 号](../images/sfbcallout2.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。
 ***
![3 号](../images/sfbcallout3.png)<br/>您还可以导出报表选项卡中的数据分隔 Excel 文件，通过单击或点击**导出到 Excel**按钮。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype 的业务活动报告](activity-report.md)您可以看到多少您的用户将对等、 组织，和参加会议会话。
    
- [Skype 的业务设备使用情况报告](device-usage-report.md)您可以查看设备包括基于 Windows 的操作系统和移动设备具有业务应用程序 Skype 的安装和使用它的 IM 和会议。
    
- [Skype 的业务会议组织者活动报告](conference-organizer-activity-report.md)您可以看到多少您的用户的组织使用 IM、 音频/视频，应用程序共享、 Web、 /dial 出 — 第三方和 /dial 出-Microsoft 的会议。
    
- [Skype 的业务会议参与者活动报告](conference-participant-activity-report.md)您可以看到多少 IM、 音频/视频，应用程序共享、 Web 和拨出音频会议正在参与。
    
- [Skype 的业务对等活动报告](peer-to-peer-activity-report.md)您可以看到多少用户使用 IM、 音频/视频、 应用程序共享和文件传输。
    
- [适用于业务用户的 Skype 阻止报告](users-blocked-report.md)您可以看到您的组织中被阻止发出 PSTN 呼叫的用户。

- [Skype 业务 PSTN minute 池报表](pstn-minute-pools-report.md)，您可以看到在组织内当前月份消耗的分钟数。

- [Skype 业务会话详细信息报表](session-details-report.md)您可以看到有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
