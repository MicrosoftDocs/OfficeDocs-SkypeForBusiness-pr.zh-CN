---
title: 使用调用分析诊断较差企业的 Skype 通话质量
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 使用调用分析有关设备、 网络和连接的详细信息来解决用户的问题与 Skype 进行业务联络和会议。
ms.openlocfilehash: b7f900509506433bd2c863fb6c0c33c4f71f2ab5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>使用调用分析诊断较差企业的 Skype 通话质量

调用分析可帮助您诊断有关业务 Skype 呼叫或连接问题。 调用分析显示在您的企业往来帐户的 Skype 有关设备、 网络和电话和会议的每个用户的连接的详细的信息。 如果构建，站点，和租户信息已添加到调用的分析，它也将显示为每个调用和会话。 通过调用分析提供的信息可帮助您找出为什么用户会有不良的调用或会议体验。 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>使用调用分析通话质量问题的疑难解答

分配给您的权限级别决定什么类型的信息您调用分析中有权：
  
- **Skype 业务管理员**： 您有权访问所有信息，在调用分析和业务管理中心为 Skype。
    
- **帮助台代理使用第 1 层权限**： 看到一组有限的数据调用分析中。 您可以解决调用，但将移交问题会议到第 2 层工程师。 您没有访问 Skype 的其余部分的业务管理中心。
    
- **帮助台代理使用第 2 层权限**： 请参见调用分析中的所有可用数据，能够帮助您解决问题的呼叫和会议。 您没有访问 Skype 的其余部分的业务管理中心。
    
如果您需要使用的权限的帮助，请参阅您 Skype 的业务管理。
  
 **为第 1 层或 2 层支持人员代理打开调用分析**
  
1. 请转到 Office 365 管理中心并使用您的工作或学校的帐户进行登录。 在 web 浏览器前往*https://adminportal.services.skypeforbusiness.com*。
    
2. 在**用户搜索**，键入您想要解决问题，然后从列表中选择用户的呼叫的用户的名称或 sip 地址。
    
    ![在业务管理中心为 Skype 呼叫分析用户的搜索框的屏幕快照。](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. 在**通话记录**，选择您要排查故障的电话或会议。
    
    ![屏幕抓图显示信息用户的联系人的详细信息，如 7 天质量和为会议和联络活动的摘要和概述日期和时间、 收件人和音频质量，具有权限的用户调用历史页](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. 选择**高级**选项卡，然后查找黄色和红色指示较差的呼叫质量或连接问题的项目。
    
    对于每个调用或会议会话的详细信息，小问题中出现的黄色。 （例如，在下面的屏幕快照的值是以黄色为平均抖动、 最大抖动和平均数据包丢失率。）如果什么东西是黄色的超出正常范围，以及它可能会造成问题，但它不可能是问题的主要原因。 如果什么东西是红色的很重要的问题，并很可能为此会话较差的呼叫质量的主要原因。 
    
    ![屏幕抓图显示用户的通话记录的高级选项卡进行入站的网络一部分展开以显示平均抖动、 最大的抖动和平均的数据包丢失率的数据所示的颜色为黄色，表示它们次要问题。](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
在极少数情况下，经验数据的质量不会接收到音频会话。 通常这被由于调用放和连接与客户端终止。 在这种情况下，会话评级为"不可用"。
  
对于音频会话具有质量 (QoE) 的经验数据下, 表描述了确认为"较差"。 一个会话的主要问题
  
|**问题**|**区域**|**说明**|
|:-----|:-----|:-----|
|呼叫设置  <br/> |会话  <br/> |Ms 诊断 20-29 的错误代码指示调用安装程序失败。 用户无法加入电话或会议。  <br/> |
|音频网络分类较差的呼叫  <br/> |会话  <br/> |网络质量问题遇到诸如数据包丢失、 抖动、 NMOS 降级，RTT，或隐藏比率。 有关用于分类较差的呼叫的条件的详细信息，请参阅以下[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。  <br/> |
|设备无法正常工作  <br/> |设备  <br/> | 设备运行不正常。 设备无法正常工作的比率如下： <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## <a name="related-topics"></a>相关主题
[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[通话分析与通话质量仪表板之间有何区别？](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 