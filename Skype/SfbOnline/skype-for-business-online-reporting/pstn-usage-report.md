---
title: "PSTN 使用情况报告"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
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
description: "新 Skype 业务管理中心报告区域显示您呼叫和音频会议活动组织中。 它使您能够深入到报表，以使您更精确地了解每个用户的活动。 例如，你可以使用 Skype for Business PSTN 使用详细信息报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 您可以查看包括通话的成本，这样可以了解您的使用情况并调用记帐详细资料以确定您的组织中使用的音频会议 PSTN 使用状况细节。"
ms.openlocfilehash: af7e33bc2cdc69d244eed1574ef5a075884f550d
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="pstn-usage-report"></a>PSTN 使用情况报告

新 Skype 业务管理中心**报告**区域显示您呼叫和音频会议活动组织中。 它使您能够深入到报表，以使您更精确地了解每个用户的活动。 例如，你可以使用 **Skype for Business PSTN 使用详细信息**报告查看拨入/拨出呼叫的通话时长以及这些呼叫的费用。 您可以查看包括通话的成本，这样可以了解您的使用情况并调用记帐详细资料以确定您的组织中使用的音频会议 PSTN 使用状况细节。
  
检查出更多可用的报告的[报告概述](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
  
本报告中，以及其他 Skype 的业务报告，提供有关活动包括整个组织中调用使用详细信息。 当您研究，规划和进行其他业务决策为您的组织和建立[通信信用](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)，这些细节就很有帮助
  
> [!NOTE]
> [!注释] 以管理员身份登录 Office 365 管理中心后，可以查看所有 Skype for Business 报告。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>如何获取 Skype for Business PSTN 使用详细信息报告

- 请转到**Office 365 管理中心** > **中心管理** > **业务管理中心的 Skype** > **报告** > **PSTN 用法详细信息**。
    
    > [!NOTE]
    > [!重要信息] 你可能无法看到此处所示的所有产品和报告，具体取决于你拥有的 Office 365 订阅。 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>解释 Skype for Business PSTN 使用情况报告

你可以通过查看显示的每一列了解用户的 Skype for Business PSTN 使用情况。
  
以下是此报告的外观。
  
![Skype for Business PSTN 使用报告](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![1 号](../images/sfbcallout1.png)<br/>该表格显示了按用户细分的全部 PSTN 使用情况。 这将显示已分配给他们和他们的 PSTN 使用业务的 Skype 的所有用户。 你可以添加/删除表格的列。
*    **调用 ID**是调用的调用 ID。 它被调用时调用 Microsoft 服务支持所使用的唯一标识符。
*    " **用户 ID**"是用户的登录名。
*    **电话号码**是 Skype 为接收传入呼叫的商务电话号码或拨出站呼叫的号码。
*    **用户位置**是用户所在的国家/地区。
*    **呼叫方 ID**是入站呼叫，从数字的呼叫方的电话号码 (呼叫方 ID) 发起调用源自呼业务编号 Skype。
*    **调用类型**是该调用是否 PSTN 传出或传入调用，如调用调用的类型放置用户或音频会议。 您可能会看到的调用类型包括： 

     **电话计划调用类型** 
     *    **user_in**（用户接收的入站的 PSTN 呼叫） 
     *    **user_out**（用户置于传出 PSTN 呼叫） 
     *    **user_out_conf**（该用户添加到等 3 种方式电话会议呼叫 PSTN 参与者提供 2 个或更多） 
     *    **user_out_transfer**（用户转移到 PSTN 号码呼叫） 
     *    **user_out_forwarding**（用户转发到 PSTN 号码呼叫）

     **音频会议呼叫类型**
     *    **conf_in**（对音频会议桥的入站的调用） 
     *    **conf_out**（出站呼叫的音频会议桥通常要将 PSTN 号码添加到会议）

     **统一的通信应用程序 (UCAP)** 
     *    **ucap_in**（到统一通信应用程序，如自动助理或调用队列入站的调用） 
     *    **ucap_out**（从统一通信应用程序，如自动助理或调用队列的出站调用）
*     
     **国内/国际**告诉您是否已放置的调用被认为 （在某一国家/地区） 国内或国际 （以外某个国家/地区） 基于用户的位置。 
*    **拨打目标**是如法国、 德国或美国本土 （美国） 拨打国家/地区目标的名称。 
*    **数字类型**是一种来自用户的电话号码、 服务或免费电话号码的电话号码。  
*    " **开始时间(UTC)**"是开始或拨打呼叫的时间。 
*    " **持续时间**"是接听呼叫的时间。  
*    **ConfID**是音频会议的会议 ID。 
*    **费用**是资金的数额或成本会记入您的帐户的调用。 
*    **货币**是一种货币用来计算该调用的开销。 
*    **功能**是为呼叫使用的许可证。 您可能会看到的许可类型有： 
     *    **MCOPSTNPP** -通信片尾 <br/> **MCOPSTN1** -国内调用计划 (3000 分美国 / 1200 分钟欧盟规划) 
     *    **MCOPSTN2** -国际电话计划 
     *    **MCOPSTN5** -国内调用计划 （120 分钟调用计划） 
     *    **MCOMEETADD** -音频会议
     *    **MCOMEETACPEA** -按每分钟的音频会议 
***
![2 号](../images/sfbcallout2.png)<br/>如果你希望创建将一列或多列中的所有数据进行分组的视图，请单击某个列并将其拖动到" **若要按特定列进行分组，请将列标题拖至此处**"。
 ***
![数字 3](../images/sfbcallout3.png)<br/>你还可以单击或点击" **导出到 Excel**"按钮，将报告数据导出到 Excel .csv 文件中。 <br/><br/> 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。如果拥有的用户不足 2000 人，你可以在报告本身的表格中进行排序和筛选。如果拥有的用户超过 2000 人，你需要导出数据进行筛选和排序。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他 Skype for Business 报告？

- [Skype 的业务活动报告](activity-report.md)您可以看到多少用户使用对等、 有组织和参与了会议会话。
    
- [Skype 的业务设备使用情况报告](device-usage-report.md)您可以查看包括基于 Windows 操作系统的设备，拥有 Skype 的业务应用程序的移动设备安装，并将其用于即时消息和会议。
    
- [Skype 业务会议组织者活动报告](conference-organizer-activity-report.md)您可以看到您的用户多少组织使用 IM，音频/视频、 应用程序共享，Web，出的第三方的 /dial 和 /dial-Microsoft 的会议。
    
- [Skype 业务会议参与者的活动报告](conference-participant-activity-report.md)您可以看到多少 IM，音频/视频、 应用程序共享、 Web 和拨出音频会议都要参加。
    
- [Skype 业务对等活动报告](peer-to-peer-activity-report.md)您可以看到您的用户使用 IM，音频/视频、 应用程序共享和文件传输的多少。
    
- [适用于业务用户的 Skype 阻塞报表](users-blocked-report.md)您可以查看组织中的用户进行 PSTN 呼叫已被阻止。

- [Skype 业务 PSTN 分钟池报告](pstn-minute-pools-report.md)您可以看到在本月组织内消耗的分钟数。

- [Skype 的业务会话详细信息报告](session-details-report.md)您可以查看有关单个用户的呼叫体验的详细信息。
    
## <a name="related-topics"></a>相关主题
[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  

