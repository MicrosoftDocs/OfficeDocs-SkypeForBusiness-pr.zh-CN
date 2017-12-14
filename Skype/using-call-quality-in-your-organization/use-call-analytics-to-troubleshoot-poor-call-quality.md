---
title: "使用呼叫分析来进行故障排除较差 Skype for Business 呼叫质量"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# 使用呼叫分析来进行故障排除较差 Skype for Business 呼叫质量

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](66945036-ae87-4c08-a0bb-984e50d6b009.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/66945036-ae87-4c08-a0bb-984e50d6b009) 中查找本文的英文版本以便参考。
  
呼叫分析可帮助您Skype for Business呼叫或连接问题疑难解答。呼叫分析Skype for Business帐户中显示有关设备、 网络和呼叫和会议的每个用户的连接的详细的信息。如果构建，网站，并租户信息已添加到呼叫分析，它也将显示为每个呼叫和会话。通过呼叫分析提供的信息可以帮助您找出为什么用户具有较差呼叫或会议体验。
  
> [!NOTE]
> 正在预览呼叫分析。文本和图像此处所述可能与您的体验。 
  
## 使用呼叫分析呼叫质量问题疑难解答

分配给您的权限级别决定了哪些类型的信息您呼叫的分析中有权访问：
  
- **Skype for Business 管理员** ： 呼叫分析和Skype for Business管理中心中，您有权访问的所有信息。
    
- **技术支持人员代理层 1 权限** ： 您看到一组有限的呼叫分析中的数据。您可以解决呼叫，但您将交给问题会议 2 层工程师。您没有访问Skype for Business管理中心中的其余部分。
    
- **技术支持人员代理层 2 权限** ： 请参阅呼叫分析中的所有可用的数据，可以帮助您解决问题的呼叫和会议。您没有访问Skype for Business管理中心中的其余部分。
    
如果您需要具有权限的帮助，请参阅Skype for Business管理员。
  
 **打开呼叫分析层 1 或 2 层技术支持人员代理**
  
1. 转到[https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com)，，然后使用您的用户名和密码登录。
    
2. 在 **用户搜索**，开始键入您想要进行故障诊断，然后从列表中选择用户的呼叫的用户的名称或 sip 地址。
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. 在 **呼叫历史记录**，请选择您想要解决呼叫或会议。
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. 选择 **高级**选项卡，然后查找黄色和红色指示不佳的呼叫质量或连接问题的项目。
    
    在每个呼叫或会议的会话详细信息，在黄色出现次要问题。（例如，在下面的屏幕截图中的值是平均抖动、 Max 抖动和平均数据包丢失率的黄色。）如果出现黄色，外部普通区域，并可能导致此问题，但很可能是主问题的原因。如果出现红色，很重要的问题，并很可能较差的呼叫质量此会话的主要原因。
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
在出现次数较少的情况下，数据体验的质量未接收到音频会话。通常这被由于呼叫放和连接与客户端终止。 如果发生这种情况，会话分级是"不可用"。
  
有体验 (QoE) 数据的质量的音频会话下, 表介绍主要有资格为"质量较差。"会话的问题
  
|**问题**|**区域**|**描述**|
|:-----|:-----|:-----|
|呼叫设置  <br/> |会话  <br/> |错误代码 Ms 诊断 20 29 表示呼叫设置失败。用户无法加入呼叫或会议。  <br/> |
|音频网络划分不佳的呼叫  <br/> |会话  <br/> |网络质量问题遇到区域数据包丢失、 抖动、 NMOS 降级，RTT，如或隐藏比率。有关用于分类不佳的呼叫的条件的详细信息，请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。  <br/> |
|设备无法正常工作  <br/> |设备  <br/> | 设备未正常工作。设备无法正常工作的比率是： <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[设置 Skype for Business 呼叫分析](set-up-skype-for-business-call-analytics.md)

