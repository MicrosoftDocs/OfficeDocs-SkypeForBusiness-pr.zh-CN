---
title: 使用通话分析来排查通话质量不良问题
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 使用呼叫分析有关设备、 网络和连接的详细信息解决用户问题与 Microsoft 团队和 Skype 业务呼叫和会议。
ms.openlocfilehash: d5409e1f37aaec6853362edc8caf74ea2a468cd7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464401"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通话分析来排查通话质量不良问题

呼叫分析可帮助您解决的 Microsoft 团队和 for Business 的 Skype 调用或连接问题。 呼叫分析您的 Office 365 帐户中显示有关设备、 网络和连接的呼叫和会议的每个用户的详细的信息。 如果生成，网站，并租户信息已添加到呼叫分析，它还会显示为每个呼叫和会话。 可通过调用分析获得的信息可帮助您明白为什么用户具有质量欠佳的呼叫或会议体验。 
  
## <a name="call-analytics-permissions"></a>呼叫分析权限

作为管理员，您获取的呼叫分析的所有功能的完全访问权限。 此外，您可以分配支持人员的 Azure Active Directory 角色。 团队 communications 支持专家角色分配用户应具有有限的呼叫分析视图。 团队 communications 支持工程师角色分配用户需要访问呼叫分析的全部功能。 这两个权限级别防止对其余的 Microsoft 团队管理中心的访问。

Communications 支持专家处理基本呼叫质量问题。 他们不调查与会议的问题。 相反，它们收集相关的信息，然后升级到 communications 支持工程师。 Communications 支持工程师请参阅详细的呼叫日志的已隐藏从通信支持专家的信息。 下表提供的信息概述了对通信支持专家和通信支持工程师使用调用分析时。

分配给您的权限级别决定哪些类型的信息您调用分析中有权访问：
  
- **团队服务管理员或团队 communications 管理员**： 呼叫分析中的和 Microsoft 团队管理中心中，您可以访问的所有信息。
    
- **团队 communications 支持专员**： 请参阅一组有限的呼叫分析中的数据。 您可以解决呼叫，但将交给会议问题的团队 communications 支持工程师。 您无需对其余的 Microsoft 团队管理中心的访问。
    
- **团队 communications 支持工程师**： 请参阅呼叫分析中的所有可用的数据并帮助解决问题呼叫和会议。 您无需对其余的 Microsoft 团队管理中心的访问。
    
> [!NOTE]
> Communications 支持专家角色等同于第 1 层支持它等效于第 2 层支持 communications 支持工程师角色。

有关团队管理员角色的详细信息，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。 团队通信支持的详细比较专员和团队通信支持工程师角色，请参阅[Set up 呼叫分析](set-up-call-analytics.md#set-call-analytics-permissions) 
  
请参阅工作组和 Skype 业务管理员如果您需要具有权限的帮助。
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>解决使用调用分析的呼叫质量问题

1. 使用您的团队通信支持或团队管理员凭据登录。

2. 在 web 浏览器中，转到*https://admin.teams.microsoft.com*。
    
3. 在**仪表板**，在**用户搜索**，开始键入名称或您想要解决或选中**查看用户**的用户列表，请参阅其呼叫用户的 sip 地址。
    
    ![呼叫的分析 Microsoft 团队管理中心中的用户搜索框的屏幕截图。](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. 从列表中选择用户。

5. 选择**呼叫历史记录**，，然后选择您想要解决该呼叫或会议。
    
    ![屏幕快照显示了用户的呼叫历史记录页。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. 选择**高级**选项卡，然后查找的黄色和红色项目指示质量欠佳的呼叫质量或连接问题。
    
    在每个呼叫或会议的会话详细信息，次要问题都显示在黄色。 （例如，在下面的屏幕快照，值为黄色的平均抖动、 最大抖动和平均数据包丢失率。）如果内容为黄色，外部正常范围和它可能会造成的问题，但它不太可能出现问题的主要原因。 如果内容为红色，很重要的问题，并且可能此会话质量欠佳的呼叫质量的主要原因。 
    
    ![屏幕快照显示了用户的呼叫历史记录高级选项卡 ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
在极少数情况下，体验质量数据不接收到音频会话。 通常这是由呼叫放和连接导致与客户端终止。 **如果发生这种情况，会话分级不可用。**
  
对于具有的用户体验 (QoE) 数据质量的音频会话下, 表介绍限定为**质量欠佳**的会话的主要问题。
  
|**问题**|**区域**|**说明**|
|:-----|:-----|:-----|
|呼叫设置  <br/> |会话  <br/> |Ms 诊断 20 29 的错误代码指示呼叫安装失败。 用户无法加入呼叫或会议。  <br/> |
|音频网络分类质量欠佳的呼叫  <br/> |会话  <br/> |遇到网络质量问题 （如数据包丢失、 抖动、 NMOS 下降，RTT 或隐藏的比率）。 有关用于分类质量欠佳的呼叫的条件的详细信息，请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。  <br/> |
|设备无法正常工作  <br/> |设备  <br/> | 设备未正常工作。 设备无法正常工作的比率是： <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## <a name="related-topics"></a>相关主题
[设置通话分析](set-up-call-analytics.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
