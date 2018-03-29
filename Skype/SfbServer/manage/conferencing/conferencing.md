---
title: 在 Skype for Business Server 2015 中管理会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 摘要： 了解如何管理业务服务器 2015年在 Skype 的会议。
ms.openlocfilehash: 2239c5aae8754e381bf6cf7b8b41aa6ef31b8033
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理会议
 
**摘要：**了解如何管理业务服务器 2015年在 Skype 的会议。
  
本主题描述如何管理会议。 有关如何规划和部署会议的详细信息，请参见[会议在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/conferencing/conferencing.md)和[业务服务器 2015年的 Skype 在部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
在 Skype 业务服务器，您通过指定，如下所示的配置和策略设置管理会议的详细信息。 请注意英语中的术语 conferencing（会议）和 meeting（会议）有时候互换使用。 但是可以将 meeting 视为 conferencing 的具体实例。
  
- **会议策略设置**包含各种安排和参与选项，包括从会议能否包括 IP 音频和视频，到可参与会议的最大人数。 可以使用会议策略管理会议的安全性、带宽以及法律发面的问题。
    
    请注意，会议策略应用于用户或站点，不能应用于具体会议。 因此，可以创建会议的会议邀请一些周提前，但严格会议策略应该应用于企业往来帐户的会议组织者的 Skype，只是在会议开始之前。 
    
    如果专用帐户用于会议组织者角色，会议策略可以一直分配给该帐户。 如果会议组织者对于企业往来帐户使用常规的 Skype，会议完毕后，必须删除该策略。
    
- **会议配置设置**规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。请注意，这些设置只影响已安排的会议。会议配置按池、按站点或全局应用。
    
- **会议配置设置**确定诸如最大允许大小会议内容和讲义。最大带宽的应用程序共享会议服务;存储限制和有效期;为内部和外部 Url 下载受支持的客户端;用户可以从何处获取会议帮助和资源; 内部和外部 Url 指向的指针和用于共享应用程序、 客户端音频、 文件传输和媒体通信的端口。
    
    这些设置可让你管理实际服务器本身。 这些设置只能通过 Skype 业务服务器管理外壳程序设置。 
    
- **拨入访问设置**允许你定义有关用户是否从电话拨入，以及如何拨入的信息。 你可以从控制面板“会议”选项卡指定某些拨入访问信息，如访问号码，可以从控制面板“语音路由”选项卡指定某些拨入信息，如拨号计划、语音策略、路由和 PSTN 用法。
    
- **PIN 策略设置**可让你指定和定义参与者用于拨入访问的 PIN。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳程序管理会议

通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳，您可以管理大多数会议策略和配置设置。 某些配置设置可以仅通过 Skype 业务服务器管理程序。
  
- 若要管理会议策略设置：
    
  - 在控制面板中，选择“**会议 | 会议策略**”。
    
  - 在 PowerShell 中搜索 **-CsConferencingPolicy** cmdlet。
    
- 若要管理会议配置设置：
    
  - 在控制面板中，选择“**会议 | 会议配置**”。
    
  - 企业服务器管理外壳的 Skype，在搜索**-CsMeetingConfiguration** cmdlet。
    
- 若要管理拨入访问号码设置：
    
  - 在控制面板中，选择“**会议 | 拨入访问号码**”。
    
  - 企业服务器管理外壳的 Skype，在搜索**-CsDialInConferencing** cmdlet。
    
- 若要管理拨入访问信息，如拨号计划、语音策略、路由和 PSTN 用法： 
    
  - 在控制面板中，选择“**会议 | 语音路由**”。
    
  - 企业服务器管理外壳的 Skype，在搜索**-CsDialPlan**和**CsVoice 的**cmdlet。
    
- 管理 PIN 策略设置：
    
  - 在控制面板中，选择“**会议 | PIN 策略**”。
    
  - 企业服务器管理外壳的 Skype，在搜索**-CsPinPolicy** cmdlet。
    
- 若要管理会议配置设置，您必须使用 Skype 业务服务器管理外壳程序。 搜索 **-CsConferencingConfiguration** cmdlet。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>企业服务器管理外壳 cmdlet 的 Skype

可以使用下面的业务服务器管理外壳 cmdlet Skype 来管理会议： 
  
**会议策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |返回有关已配置为在组织中使用的会议策略的信息。会议策略决定了会议中可以使用的功能，从会议能否加入 IP 音频和视频到可参加会议的最大人数，涵盖会议的方方面面。  <br/> |
|[授予 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每用户范围分配会议策略。  <br/> |
|[新 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |创建在组织中使用的新会议策略。  <br/> |
|[删除 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |删除指定的会议策略。  <br/> |
|[一组 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改现有会议策略。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关组织中当前正在使用的会议配置设置的信息。会议配置设置帮助规定用户可创建的会议类型，以及控制匿名用户和电话拨入式会议用户如何（甚至是否）可以加入这些会议。  <br/> |
|[新 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在 site 或服务范围创建新的会议配置设置集合。 请注意，这些设置只影响已安排的会议;它们不会影响通过单击 Skype 业务中的立即开会选项创建的特别会议。  <br/> |
|[删除 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除会议配置设置的现有集合。  <br/> |
|[一组 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。会议设置可确定诸如会议内容和讲义允许的最大大小、内容宽限期（即内容在被删除前存储的时间）以及用于内部和外部下载支持的客户端的 URL 等信息。  <br/> |
|[新 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[删除 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置的集合。  <br/> |
|[一组 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
**拨入配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |返回有关配置为在组织中使用的会议目录的信息。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[获得 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |检索有关业务服务器的 Skype 用户加入或离开拨入会议时的响应信息。  <br/> |
|[获得 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |返回有关配置为在组织中使用的所有电话拨入式会议访问号码的信息。  <br/> |
|[获得 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |返回用于电话拨入式会议的双音多频 (DTMF) 信号设置。通过 DTMF，拨号接入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。  <br/> |
|[获得 CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |返回的语言，包括区域/少数民族语言，支持使用 Skype 业务服务器拨入会议的列表。 这些语言用于将音频消息和说明中继到使用电话参与会议的用户。  <br/> |
|[获得 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |返回有关您组织中使用的拨号计划的信息。  <br/> |
|[授予 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |向一个或多个用户或组分配拨号计划。  <br/> |
|[导入 CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |从导入会议目录 Microsoft Office 通信服务器 2007 R2 到 Skype 业务服务器。 这有助于提供业务服务器的 Skype 和办公室通信服务器 2007 R2 之间的互操作性。  <br/> |
|[移动 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |将现有的会议目录从一个池移动到另一个池。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |创建在组织中使用的新会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[新 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |创建新的电话拨入式会议访问号码。  <br/> |
|[新 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |创建新的电话拨入式会议配置设置集合。 这些设置可确定当用户加入或离开拨入会议 Skype 业务服务器的响应方式。 特别是，返回有关是否要求参会者在加入会议时记录其姓名的信息，以及系统如何（甚至是否）通知某人已加入或退出呼叫的信息。  <br/> |
|[新 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |创建新的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[新 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |创建新的拨号计划。  <br/> |
|[删除 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |删除现有会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[删除 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |删除现有的电话拨入式会议访问号码。  <br/> |
|[删除 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |删除电话拨入式会议配置设置的一个或多个集合。 这些设置可确定当用户加入或离开拨入会议 Skype 业务服务器的响应方式。  <br/> |
|[删除 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |删除现有的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[一组 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改现有电话拨入式会议接入号码的属性值。电话拨入式会议为用户提供了一种使用"常规"电话、移动电话或公用电话交换网 (PSTN) 上的其他设备加入会议的音频部分的方法。  <br/> |
|[一组 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改设置，从而确定当用户加入或离开拨入会议 Skype 业务服务器的响应方式。  <br/> |
|[一组 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改用于电话拨入式会议的双音多频 (DTMF) 信号设置。  <br/> |
|[一组 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改现有的拨号计划。  <br/> |
   
**PIN 策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |返回有关配置为在组织中使用的客户端个人标识号 (PIN) 策略的信息。 PIN 身份验证允许用户访问 Skype 业务服务器通过提供一个 PIN 而不是用户名和密码。  <br/> |
|[授予 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |向一个或一组用户分配客户端个人标识号 (PIN) 策略。  <br/> |
|[新 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |创建新的客户端个人标识号 (PIN) 策略。  <br/> |
|[删除 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |删除指定的个人标识号 (PIN) 策略。  <br/> |
|[一组 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一个或多个现有的客户端个人标识号 (PIN) 策略。  <br/> |
   
**其他会议设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[禁用-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |禁用业务服务器的会议室的 Skype。 会议室是一个旨在处理小会议室中的视频会议和协作方案的会议设备。 当您禁用会议室对象删除特定于业务服务器的 Active Directory 特性分配给用户帐户表示会议室内的所有 Skype。 但是，不会删除 Active Directory 用户帐户本身。  <br/> |
|[启用 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |使业务服务器的会议室的 Skype。 若要启用会议室，首先必须创建一个 Active Directory 用户帐户表示该系统。 注意，尽管会议室基于用户帐户对象，这些对象将不会显示在运行时获取 CsUser cmdlet。  <br/> |
|[获得 CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |返回有关组织中使用的会议免责声明的信息。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[获得 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |返回有关所有 Skype 会议室配置为可在组织的业务服务器的信息。  <br/> |
|[移动 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |为业务会议到另一个注册库中的文件室对象的服务器移动 Skype。  <br/> |
|[删除 CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |从组织中使用的会议免责声明的标题和正文中清除文本。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[一组 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |修改现有的业务服务器的会议室 Skype 的属性值。  <br/> |
   
**测试设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[测试 CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |测试用户对能否参与应用程序共享会议。  <br/> |
|[测试 CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |测试用户能否连接到其音频会议提供商。音频会议提供商是为组织提供会议服务的第三方公司。此外，音频会议提供商使外出且未连接到企业网络或 Internet 的用户可以通过音频参加会议。  <br/> |
|[测试 CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |测试一对用户能否加入音频/视频 (A/V) 会议。  <br/> |
|[测试 CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |验证对用户可以参与 Skype 业务服务器 web 会议包含共享或查看 PowerPoint 幻灯片、 白板或轮询等活动。 该 cmdlet 还验证业务服务器 web 会议服务 Skype 可以发现 Office Web 应用程序服务器和客户端可以上载 PowerPoint 文件通过 Office Web 应用程序服务器的广播。  <br/> |
|[测试 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |检查用户是否可以参与电话拨入式会议会话。  <br/> |
|[测试 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |针对拨号计划（以前称为位置配置文件）测试一个电话号码，返回将应用于该号码的规范化规则，以及应用该规范化规则后的转换号码。  <br/> |
|[测试 CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |测试三个用户参与业务服务器移动服务会议的 Skype 的能力。 移动服务使用户的手机如 Iphone 和 Windows 手机事情交换即时消息和状态信息;存储和检索语音邮件内部而不是用其无线服务提供商;并利用 Skype 的业务服务器的功能，如通过工作和拨出的会议呼叫。  <br/> |
|[测试 CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |测试一对用户使用统一通信 Web API (UCWA) 安排、加入然后召开联机会议的能力。  <br/> |
|[调试-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |返回包含在 Skype 业务服务器的数据会议功能的诊断的信息。  <br/> |
   

