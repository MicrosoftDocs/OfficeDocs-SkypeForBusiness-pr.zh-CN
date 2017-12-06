---
title: "创建电话系统呼叫队列"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# 创建电话系统呼叫队列

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](67ccda94-1210-43fb-a25b-7b9785f8a061.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/67ccda94-1210-43fb-a25b-7b9785f8a061) 中查找本文的英文版本以便参考。
  
电话系统呼叫队列包括问候语有人在您的组织、 能够自动将呼叫置于保持状态，并进行搜索下一个可用的呼叫代理处理呼叫时的人员的功能的电话号码呼叫时使用的人员呼叫收听音乐置于保持状态。您可以为您的组织创建单个或多个呼叫队列。
  
电话系统呼叫队列可以提供：
  
- 组织问候语。
    
- 在呼叫者保持等待时播放的音乐。
    
- 重定向的呼叫转接到呼叫中启用邮件的通讯组列表和安全组的代理。
    
- 进行呼叫队列最大大小、 超时和呼叫处理选项设置。
    
当有人呼叫设置的电话号码到向上与呼叫队列，他们将听到问候语第一个 （如果任何已设置），然后将它们会在队列中放置，并等待下一个可用的呼叫代理。拨入的人员将收听音乐时，他们置于保持状态等待，并且呼叫将提供给 *第一个中，先出*  （先进先出） 方式中的呼叫代理。
  
将使用助理路由模式或串行路由模式 （适用于仅预览客户） 分发等待队列中的所有呼叫：
  
- 助理路由，队列中的第一个呼叫将同时拨打所有代理。
    
- 使用串行路由，队列中的第一个呼叫将拨打所有呼叫代理逐个 （适用于仅预览客户）。
    
-     > [!注释]
    > 不会称为呼叫代理处于 **脱机状态**，将其状态设置为 **请勿打扰，**或已退出呼叫队列。 
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
    
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。
    
## 第 1 步 - 开始

要开始使用呼叫队列，记住以下几点至关重要：
  
- 企业版 E3 与 **电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低）。将被分配的 **电话系统**的用户许可证数影响的服务号码可用于呼叫队列。您可以呼叫队列数是依赖于 **电话系统**和 **音频会议**在您的组织中分配的许可证的数量。若要了解有关许可，转[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!注释]
    > 要重定向呼叫转接到的人员在您的组织中处于联机状态，它们必须 **电话系统**许可证并启用企业语音或具有 Office 365 调用计划。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。要启用企业语音它们，您可以使用 Windows PowerShell。例如运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 调用计划的详细信息，请参阅[什么是致电 Office 365 中计划？](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)和[致电 office 365 计划](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)。
    
    > [!注释]
    > 用户托管本地使用 Lync Server 2010 为呼叫队列代理不支持。 
  
- 您可以仅分配收费和免费服务有 **Skype for Business 管理中心**中或从另一个服务提供商转移到电话系统呼叫队列的电话号码。要获取和使用服务的免费电话号码，您需要设置通信贷项。
    
    > [!注释]
    > 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。 
  
- 当您分发的传入呼叫的电话系统呼叫队列中时，这些客户端支持呼叫代理：
    
  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）
    
  - Lync 桌面客户端 2013（32 位和 64 位版本）
    
  - 支持 Skype for Business Online 的所有 IP 电话型号。请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。
    
  - Mac Skype for Business 客户端 (版本 16.8.196 及更高版本)
    
  - Android 的 Skype for Business 客户端 (版本 6.16.0.9 及更高版本)
    
  - iPhone Skype for Business 客户端 (版本 6.16.0 及更高版本)
    
  - iPad Skype for Business 客户端 (版本 6.16.0 及更高版本)
    
## 第 2 步 - 获取或转移收费或免费服务电话号码

您可以创建和设置您的呼叫队列之前，您需要获取或将现有收费或免费服务传输数字。收费电话或服务的免费电话号码后，它们将显示在 **Skype for Business 管理中心**> **语音**> **电话号码**，并列出的 **数字类型**将被列为 **服务-免费电话**。要获取您的服务号码，请查看[获取 Skype for Business 服务电话号码](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)或如果您希望的传输和现有服务号码，请参阅[将电话号码转移到 Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。
  
> [!注释]
> 如果您是在美国以外，您无法使用 Skype for Business 管理中心获取服务号码。转[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)相反，了解如何执行此操作从美国的外侧。 
  
## 第 3 步 - 创建新的呼叫队列

在 **Skype for Business 管理中心**，单击" **呼叫路由**">" **呼叫队列**"，然后单击" **新增**"：
  
### 设置呼叫队列显示名称、电话号码和域（如有）

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。 <br/> 此名称将显示在传入呼叫的通知中。  <br/> |
|**2** <br/> |**电话号码**选择服务收费电话或呼叫队列免费电话号码。这是可选的。  <br/> 如果没有列出任何号码，则需要首先获取服务号码，然后才能创建此服务队列。要获取服务号码，请参阅[获取 Skype for Business 服务电话号码](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) <br/> |
|**3** <br/> |**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。 <br/> 例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_ <br/> |
   
### 设置通话保持时播放的问候语和音乐

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |**问候语**是可选的。这是会向呼叫队列编号播放的拨入的人员的问候语。  <br/> 您可以上载音频文件 （.wav, .mp3 或.wma 格式）。  <br/> |
|**2** <br/> |**保持音乐**您可以在保留提供与呼叫队列中，使用默认音乐或可以上载音频文件.wav、 mp3 或.wma 格式，以用作自定义的音乐置于保持状态。  <br/> |
   
### 选择呼叫分发方法 （适用于仅预览客户）

![Shows the call distribution method options](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
|||
|:-----|:-----|
|**1** <br/> |**呼叫分发方法**您可以为您的呼叫队列分发方法选择 **助理**或 **串行**。所有新的和现有呼叫队列将具有默认选择助理路由。若要使用串行路由，您必须在用户界面和 cmdlet 显式选择 **串行**路由选项。  <br/> 当选定串行路由并保存呼叫队列，从队列呼叫将拨打您的开始处的代理列表中的代理，逐个。如果代理关闭或不领取呼叫，呼叫将拨打列表上的下一个代理，并将尝试所有代理逐个按，直到它领取或出队列中等待的时间。  <br/> > [!注释]> 串行路由将跳过人士 **脱机** ，将其状态设置为 **请勿打扰** ，或从该队列中获取呼叫的 **选择不参加** 的代理。          |
   
### 选择代理选择退出选项 （适用于仅预览客户）

![Shows the agent opt out check box](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
|||
|:-----|:-----|
|**1** <br/> |**代理选择退出选项**您可以选择允许呼叫队列代理选择退出通过选择 **代理选择退出选项**来在接听呼叫特定队列中。  <br/> 启用此选项允许将在此队列中的所有代理启动或停止从在此呼叫队列中接收呼叫。您可以取消代理退出特权随时通过清除该复选框，导致代理会自动在选择此队列再次 （所有代理的默认设置）。  <br/> 若要访问退出选项，代理可以执行以下操作：  <br/> 1.打开其桌面 Skype for Business 客户端中的 **选项**。  <br/> 2.在 **呼叫转接**选项卡上，单击 **编辑设置联机**链接  <br/> 3.在用户设置页面中，单击 **呼叫队列**，，然后清除要为其选择退出任何队列对应的复选框。  <br/> |
   
### 向呼叫队列添加呼叫代理

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1** <br/> | 呼叫代理（最多 50 个）可以是： <br/>  联机用户与 **电话系统**许可证启用企业语音或呼叫计划。  <br/> > [!注释]>  要重定向呼叫转接到的人员在您的组织中处于联机状态，它们必须 **电话系统**许可证并启用企业语音或有呼叫计划。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。要启用企业语音它们，您可以使用 Windows PowerShell。例如运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Online 用户与 **电话系统**许可证或呼叫计划添加到已启用邮件的通讯组列表或安全组。可能需要 30 分钟的通讯组列表或以开始接收呼叫呼叫队列中的安全组添加新的代理。新创建的通讯组列表或安全组可能需要长达 48 小时变为可用于呼叫队列。  <br/> > [!注释]>  Office 365 组 （现代组） 不能使用呼叫队列。          > [!注释]>  用户托管本地使用 Lync Server 2010 不支持。          |
   
### 设置队列最大大小和最长等待时间。

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1**|**呼叫队列中的最大值**使用此选项来同时在队列中设置可以等待最大呼叫。默认值为 50，但它可以介于 0 到 200。达到此限制后，将按照在后面的" **达到最大呼叫次数时**"设置中指定的方式来处理呼叫。|
|**2**|**当达到呼叫的最大数目时**当呼叫队列达到最大值 （设置使用 **呼叫队列中的最大值**设置） 时，您可以选择新的传入呼叫会发生什么情况。 **断开连接并显示繁忙信号** 呼叫将断开连接。 **这将呼叫转接至**选择此操作时，您将具有这些选项： **您所在公司的人员**联机用户与 **电话系统**许可证并启用企业语音或有呼叫计划。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，并设置其呼叫转接到语音邮件直接此人。 > [!注释]>  用户托管本地使用 Lync Server 2010 不支持。          **呼叫队列**您必须已创建另一个呼叫队列，但执行操作之后，您可以选择该呼叫队列。 **自动助理**您必须已创建自动助理，但执行操作之后，您可以选择自动助理。请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。 |
|**3**|**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。> [!注释]> **预览客户仅供：** 超时值可以在 15 秒的时间间隔 （秒），设置。这样，您可以使用细致操作呼叫流。例如，您可以指定任何 30 秒内代理未应答的呼叫进入目录搜索自动助理。          |
|**4**|**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫： **断开连接** 呼叫将断开连接。 **这将呼叫转接至**选择此操作时，您将具有这些选项： **您所在公司的人员**联机用户与 **电话系统**许可证并启用企业语音或有呼叫计划。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，并设置其呼叫转接到语音邮件直接此人。 > [!注释]>  用户托管本地使用 Lync Server 2010 不支持。          **呼叫队列**您必须已创建另一个呼叫队列，但执行操作之后，您可以选择该呼叫队列。 **自动助理**您必须已创建自动助理，但执行操作之后，您可以选择自动助理。请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。 |
   
## 更改为呼叫队列的电话号码的用户的呼叫者 ID

您可以通过更改其到呼叫队列出站呼叫的呼叫者 ID 改为创建使用 **New-CallingLineIdentity** cmdlet 策略保护用户的身份。
  
若要执行此操作，运行：
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后将该策略应用于使用 **Grant-CallingLineIdentity** cmdlet 的用户。若要执行此操作，运行：
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以获得有关如何更改您的组织中的呼叫者 ID 设置的详细信息[如何在你的组织中使用来电显示](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)。
  
## 希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置呼叫队列。
  
### 呼叫队列 cmdlet

以下是管理呼叫队列时需要使用的 cmdlet。
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### 有关 Windows PowerShell 的详细信息

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

