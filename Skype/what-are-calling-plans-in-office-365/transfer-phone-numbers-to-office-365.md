---
title: "将电话号码转移到 Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PortingNumbersOverview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e

description: "Learn what you need to know and do before porting phone numbers to Skype for Business, and how to create a port order to transfer them."
---

# 将电话号码转移到 Office 365

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](47b3af8e-4171-4dec-8333-c956f108664e.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/47b3af8e-4171-4dec-8333-c956f108664e) 中查找本文的英文版本以便参考。
  
将你的电话号码从当前的服务提供商转移到 Skype for Business 很简单。将你的电话号码转网到 Skype for Business 之后，Microsoft 将成为你的服务提供商并为你出具这些号码的账单。
  
转接电话号码在开始之前，我们建议您查看[转接电话号码的常见问题](transferring-phone-numbers-common-questions.md)中的信息。如果您有服务拨入式会议网桥、 自动助理或其他服务的数字的数字，免费电话号码或有多个 999 用户 （订阅服务器） 电话号码，您需要将传输到Skype for Business，请参阅[手动提交自定义服务请求](manually-submit-a-custom-service-request.md)下载正确的窗体并将其发送给我们。
> [!注释]
> 我们处理端口订单仅在美国工作日上而不是在公共假日或周末转接电话号码。 
  
## 如何创建转网订单并将电话号码转移到 Skype for Business
<a name="bk_LNPcountries_1"> </a>

> [!注释]
> 如果您有服务拨入式会议网桥、 自动助理或其他服务的数字的数字，免费电话号码或有多个 999 用户 （订阅服务器） 电话号码，您需要将传输到Skype for Business，请参阅[手动提交自定义服务请求](manually-submit-a-custom-service-request.md)下载正确的窗体并将其发送给我们。 
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在左侧导航中，转到" **语音**">" **转网订单**"，单击" **添加**"。
    
4. 在" **新建本地号码转网订单**"页面上，阅读信息，然后单击" **我们开始吧**"。
    
5. 在" **帐户信息**"页面上，输入以下信息，然后单击" **下一步**"：
    
  - **帐号**服务提供商或运营商的帐号。
    
  - **帐单的电话号码**必须采用 E.164 格式 (需要 + 号预置数)。例如，对于北美地区数字，使用格式 + 1XXXYYYZZZZ。
    
  - **输入 PIN 以取消阻止号码**PIN - 如果你的当前服务提供商或运营商需要。
    
  - **公司名称** 这是你的公司或组织的名称。
    
    > [!注释]
    > " **公司名称**"框将仅接受包括空格在内的 25 个字符。如果公司名称超过 25 个字符，将提交名称的前 25 个字符，仍将处理转网订单。 
  
  - **授权人员**授权用户的姓名。
    
    > [!注释]
    > " **授权人员**"框将仅接受包括空格在内的 15 个字符。如果授权人员的姓名超过 15 个字符，将提交姓名的前 15 个字符，仍将处理转网订单。 
  
  - **服务地址**帐户的服务地址。这会列在服务提供商或运营商的帐单上。
    
  - 服务地址的 **城市**、 **省/市/自治区**、 **邮政编码**。
    
6. 在 **号码**页面中，输入您想要转移 E.164 格式中的电话号码。例如，对于北美地区数字，使用格式 + 1XXXYYYZZZZ。通过使用逗号分隔多个电话号码。
    
    > [!注释]
    > 如果要执行完整转网，你需要在列表中包括服务付费电话号码 (BTN)。如果要执行部分转网，请不要在此列表中包括服务付费电话号码 (BTN)。 
  
    如果要执行完整转网，请选择" **我正在从我当前的运营商转移我的所有号码**"。如果要执行部分转网，请选择" **我只转移我的部分号码**"。在选择合适的选项之后，请单击" **请检查号码可转网性**"。
    
7. 单击 **继续**。
    
8. **转移日期**在页面上， **一天**的下拉列表中，选择日期和在 **开始时间**下拉列表中，下选择的时间 （东部），然后单击 **下一步**。
    
9. 在 **字母的授权**页上，选中每个下面的框。然后在 **签名**框中，键入有权更改帐户的人员。这是用于在 **帐户信息**页面的相同名称 > **Authorizing 人员**。单击 **下一步**。
    
10. 在 **其他人通知**下的 **提交**页面上输入您想并单击 **提交端口顺序**的人员的任何其他电子邮件地址。现在将在 **端口订单**页上列出的端口顺序。您可以查看在 **状态**列下订单的状态。您可以查看如 **订单 ID**、 **已提交**、 **转移日期**和 **状态**端口订单的详细信息。您可以查看更多详细信息操作窗格，包括运营商的名称中的端口顺序。
    
## 下一步会发生什么？
<a name="bk_LNPcountries_1"> </a>

你的转网订单提交并被接收后，你会收到一封确认转网订单的电子邮件。
  
将选中和每日更新端口顺序请求并将其电子邮件中的状态和进度的通知您。如果您的请求被拒绝，系统将要求打开支持票证，并在所支持的票证我们要求您提供 **端口订单 ID**。 在 Skype for Business 管理中心，在 **声音**下，可以找到 ID 的端口顺序 > **端口订单**> **订单 ID**列。
  
## 如果我遇到问题该怎么办？
<a name="bk_LNPcountries_1"> </a>

 **服务地址不帐单地址相同。我提交订单上的地址信息匹配我的客户帐单副本，为什么它仍然拒绝？** 大多数运营商将识别移植基于服务地址信息，而不是帐单地址的信息。由于帐单副本帐单的记录，不可能为端口连接的电话号码提供相同的服务地址信息。
  
 **怎么办如果我顺序需要花费很长时间来处理？** 我们希望数字移植非常简单而快速的过程。如果您的订单长于您思考应仍状态不Skype for Business管理中心中显示为已完成，请打开支持票证和包括端口订单 id。
  
## 
<a name="bk_LNPcountries_1"> </a>

||
|:-----|
|![领英学习快捷图标。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **刚开始使用 Office 365？**         探索由 LinkedIn Learning 提供的适用于 **Office 365 管理员和 IT 专业人士**的免费视频课程。 |
   
## 相关主题
<a name="bk_LNPcountries_1"> </a>

[设置呼叫计划](set-up-calling-plans.md)
  
[转接电话号码的常见问题](transferring-phone-numbers-common-questions.md)
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

