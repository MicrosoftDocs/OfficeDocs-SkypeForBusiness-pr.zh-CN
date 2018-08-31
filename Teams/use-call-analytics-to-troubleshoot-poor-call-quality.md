---
title: 使用通话分析解决通话质量不佳的问题
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
description: 使用设备、 网络和连接的呼叫分析信息解决用户问题与 Skype 的业务呼叫和会议。
ms.openlocfilehash: db1f0ed4ce79936a5355fe087220fe2802f61ce6
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23783147"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通话分析解决通话质量不佳的问题

呼叫分析可帮助您解决的 Microsoft 团队和 for Business 的 Skype 调用或连接问题。 呼叫分析您的 Office 365 帐户中显示有关设备、 网络和连接的呼叫和会议的每个用户的详细的信息。 如果生成，网站，并租户信息已添加到呼叫分析，它还会显示为每个呼叫和会话。 可通过调用分析获得的信息可帮助您明白为什么用户具有质量欠佳的呼叫或会议体验。 
  
**呼叫分析现已推出中的 Microsoft 团队和 Skype 的业务 Admin Center。** 若要查看的所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过仪表板用户可以搜索用户的配置文件页上查找或**用户**的左侧导航中查找用户执行此操作。

> [!IMPORTANT]
> 帮助台代理权限和网络拓扑上载中将提供新的管理门户在几个月。 同时，您可以继续使用https://adminportal.services.skypeforbusiness.com1 层和第 2 层帮助台访问。
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>解决使用调用分析的呼叫质量问题

分配给您的权限级别决定哪些类型的信息您调用分析中有权访问：
  
- **针对业务管理员 Skype**： 和业务管理中心的 Skype 调用分析中，您有权访问所有信息。
    
- **帮助台代理具有 1 层权限**： 您看到一组有限的呼叫分析中的数据。 您可以解决呼叫，但将交给会议问题的第 2 层代理。 您无需访问业务 Admin center Skype 的其余部分。
    
- **第 2 层权限的帮助台代理**： 请参阅呼叫分析中的所有可用的数据并帮助解决问题呼叫和会议。 您无需访问业务 Admin center Skype 的其余部分。
    
如果您需要具有权限的帮助，请参阅 Business admin 您 Skype。
  
 **打开呼叫分析作为层 1 或 2 层帮助台代理**
  
1. 转到 Office 365 管理中心，并使用工作或学校帐户登录。 在 web 浏览器前往*https://adminportal.services.skypeforbusiness.com*。
    
2. 在**用户搜索**，开始键入您想要解决，然后从列表中选择用户其呼叫的用户的名称或 sip 地址。
    
    ![在 Business Admin Center Skype 调用分析的用户搜索框的屏幕截图。](media/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. 在**呼叫历史记录**，请选择您想要解决该呼叫或会议。
    
    ![屏幕快照显示了具有用户的联系人的详细信息，如汇总 7 天质量和活动的会议和呼叫，以及的日期和时间、 收件人和音频质量，概述的信息的用户的呼叫历史记录页](media/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. 选择**高级**选项卡，然后查找的黄色和红色项目指示质量欠佳的呼叫质量或连接问题。
    
    在每个呼叫或会议的会话详细信息，次要问题都显示在黄色。 （例如，在下面的屏幕快照，值为黄色的平均抖动、 最大抖动和平均数据包丢失率。）如果内容为黄色，外部正常范围和它可能会造成的问题，但它不太可能出现问题的主要原因。 如果内容为红色，很重要的问题，并且可能此会话质量欠佳的呼叫质量的主要原因。 
    
    ![屏幕截图显示用户的呼叫历史记录高级选项卡与入站的网络部分展开以显示平均抖动、 最大抖动和平均数据包丢失率的数据所示为黄色，这意味着它们次要问题。](media/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
在极少数情况下，体验质量数据不接收到音频会话。 通常这是由呼叫放和连接导致与客户端终止。 发生这种情况，会话分级时"不可用"。
  
有体验 (QoE) 数据质量的音频会话下, 表介绍限定为"差。"的会话的主要问题
  
|**问题**|**区域**|**说明**|
|:-----|:-----|:-----|
|呼叫设置  <br/> |会话  <br/> |Ms 诊断 20 29 的错误代码指示呼叫安装失败。 用户无法加入呼叫或会议。  <br/> |
|音频网络分类质量欠佳的呼叫  <br/> |会话  <br/> |网络质量问题中数据包丢失、 抖动 NMOS 下降，RTT，这些方面遇到或隐藏比率。 有关用于分类质量欠佳的呼叫的条件的详细信息，请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。  <br/> |
|设备无法正常工作  <br/> |设备  <br/> | 设备未正常工作。 设备无法正常工作的比率是： <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## <a name="related-topics"></a>相关主题
[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[呼叫分析和呼叫质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
