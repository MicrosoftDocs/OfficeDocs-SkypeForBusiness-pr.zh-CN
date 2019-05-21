---
title: 在 Skype for Business 服务器中管理会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '摘要: 了解如何在 Skype for Business 服务器中管理会议。'
ms.openlocfilehash: 55fd2ff645e6e95199b2558ef494eea019b155bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280423"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>在 Skype for Business 服务器中管理会议
 
**摘要:** 了解如何在 Skype for Business 服务器中管理会议。
  
本主题描述如何管理会议。 有关如何规划和部署会议的详细信息, 请参阅在 skype for business[服务器中规划会议](../../plan-your-deployment/conferencing/conferencing.md)和[在 Skype for Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
在 Skype for Business 服务器中, 通过指定配置和策略设置来管理会议的详细信息, 如下所示。 请注意英语中的术语 conferencing（会议）和 meeting（会议）有时候互换使用。 但是可以将 meeting 视为 conferencing 的具体实例。
  
- **会议策略设置**包含各种安排和参与选项，包括从会议能否包括 IP 音频和视频，到可参与会议的最大人数。 可以使用会议策略管理会议的安全性、带宽以及法律发面的问题。
    
    请注意，会议策略应用于用户或站点，不能应用于具体会议。 因此, 可以提前在几周内创建会议的会议邀请, 但应在会议开始之前将限制性的会议策略应用于会议组织者的 Skype for Business 帐户。 
    
    如果专用帐户用于会议组织者角色，会议策略可以一直分配给该帐户。 如果会议组织者使用常规 Skype for Business 帐户, 则必须在会议完成后删除该策略。
    
- **会议配置设置**规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。请注意，这些设置只影响已安排的会议。会议配置按池、按站点或全局应用。
    
- **会议配置设置**决定了会议内容和讲义的最大允许大小;应用程序共享会议服务的最大带宽量;存储限额和到期期;支持的客户端的内部和外部下载的 Url;指向用户可获取会议帮助和资源的内部和外部 Url 的指针;以及用于应用程序共享、客户端音频、文件传输和媒体流量的端口。
    
    这些设置可让你管理实际服务器本身。 这些设置只能通过使用 Skype for Business Server 命令行管理程序来设置。 
    
- **拨入访问设置**允许你定义有关用户是否从电话拨入，以及如何拨入的信息。 你可以从控制面板“会议”选项卡指定某些拨入访问信息，如访问号码，可以从控制面板“语音路由”选项卡指定某些拨入信息，如拨号计划、语音策略、路由和 PSTN 用法。
    
- **PIN 策略设置**可让你指定和定义参与者用于拨入访问的 PIN。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>使用 Skype for business 服务器控制面板或使用 Skype for business Server 命令行管理程序管理会议

您可以使用 Skype for Business 服务器控制面板或使用 Skype for business Server 命令行管理器管理大多数会议策略和配置设置。 某些配置设置仅适用于使用 Skype for Business Server 命令行管理程序。
  
- 若要管理会议策略设置：
    
  - 在控制面板中，选择“**会议 | 会议策略**”。
    
  - 在 PowerShell 中搜索 **-CsConferencingPolicy** cmdlet。
    
- 若要管理会议配置设置：
    
  - 在控制面板中，选择“**会议 | 会议配置**”。
    
  - 在 Skype for Business Server 命令行管理程序中, 搜索 **-CsMeetingConfiguration** cmdlet。
    
- 若要管理拨入访问号码设置：
    
  - 在控制面板中，选择“**会议 | 拨入访问号码**”。
    
  - 在 Skype for Business Server 命令行管理程序中, 搜索 **-CsDialInConferencing** cmdlet。
    
- 若要管理拨入访问信息，如拨号计划、语音策略、路由和 PSTN 用法： 
    
  - 在控制面板中，选择“**会议 | 语音路由**”。
    
  - 在 Skype for Business Server Management Shell 中, 搜索 **-CsDialPlan**和 **-CsVoice** cmdlet。
    
- 管理 PIN 策略设置：
    
  - 在控制面板中，选择“**会议 | PIN 策略**”。
    
  - 在 Skype for Business Server 命令行管理程序中, 搜索 **-CsPinPolicy** cmdlet。
    
- 要管理会议配置设置, 您必须使用 Skype for Business 服务器命令行管理程序。 搜索 **-CsConferencingConfiguration** cmdlet。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business 服务器管理外壳 cmdlet

你可以使用以下 Skype for Business Server Management Shell cmdlet 管理会议: 
  
**会议策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |返回有关已配置为在组织中使用的会议策略的信息。会议策略决定了会议中可以使用的功能，从会议能否加入 IP 音频和视频到可参加会议的最大人数，涵盖会议的方方面面。  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每用户范围分配会议策略。  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |创建在组织中使用的新会议策略。  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |删除指定的会议策略。  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改现有会议策略。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关组织中当前正在使用的会议配置设置的信息。会议配置设置帮助规定用户可创建的会议类型，以及控制匿名用户和电话拨入式会议用户如何（甚至是否）可以加入这些会议。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在 site 或服务范围创建新的会议配置设置集合。 请注意, 这些设置仅影响计划的会议;它们不会影响通过单击 Skype for Business 中的 "立即开会" 选项创建的临时会议。  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除会议配置设置的现有集合。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。会议设置可确定诸如会议内容和讲义允许的最大大小、内容宽限期（即内容在被删除前存储的时间）以及用于内部和外部下载支持的客户端的 URL 等信息。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置的集合。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
**拨号配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |返回有关配置为在组织中使用的会议目录的信息。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |检索有关 Skype for Business 服务器在用户加入或离开电话拨入式会议时如何响应的信息。  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |返回有关配置为在组织中使用的所有电话拨入式会议访问号码的信息。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |返回用于电话拨入式会议的双音多频 (DTMF) 信号设置。通过 DTMF，拨号接入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |返回一系列语言, 其中包括与 Skype for business 服务器拨入式会议配合使用所支持的各种语言 (包括区域/少数) 语言。 这些语言用于将音频消息和说明中继到使用电话参与会议的用户。  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |返回有关您组织中使用的拨号计划的信息。  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |向一个或多个用户或组分配拨号计划。  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |将会议目录从 Microsoft Office 通信服务器 2007 R2 导入到 Skype for business 服务器。 这有助于提供 Skype for Business 服务器与 Office 通信服务器 2007 R2 之间的互操作性。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |将现有的会议目录从一个池移动到另一个池。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |创建在组织中使用的新会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |创建新的电话拨入式会议访问号码。  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |创建新的电话拨入式会议配置设置集合。 这些设置决定了当用户加入或离开电话拨入式会议时, Skype for business 服务器的响应方式。 特别是，返回有关是否要求参会者在加入会议时记录其姓名的信息，以及系统如何（甚至是否）通知某人已加入或退出呼叫的信息。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |创建新的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |创建新的拨号计划。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |删除现有会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |删除现有的电话拨入式会议访问号码。  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |删除电话拨入式会议配置设置的一个或多个集合。 这些设置决定了当用户加入或离开电话拨入式会议时, Skype for business 服务器的响应方式。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |删除现有的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改现有电话拨入式会议接入号码的属性值。电话拨入式会议为用户提供了一种使用"常规"电话、移动电话或公用电话交换网 (PSTN) 上的其他设备加入会议的音频部分的方法。  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改确定当用户加入或离开电话拨入式会议时, Skype for business 服务器如何响应的设置。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改用于电话拨入式会议的双音多频 (DTMF) 信号设置。  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改现有的拨号计划。  <br/> |
   
**PIN 策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |返回有关配置为在组织中使用的客户端个人标识号 (PIN) 策略的信息。 PIN 身份验证使用户可以通过提供 PIN (而不是用户名和密码) 来访问 Skype for business 服务器。  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |向一个或一组用户分配客户端个人标识号 (PIN) 策略。  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |创建新的客户端个人标识号 (PIN) 策略。  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |删除指定的个人标识号 (PIN) 策略。  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一个或多个现有的客户端个人标识号 (PIN) 策略。  <br/> |
   
**其他会议设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |禁用 Skype for business Server 会议室。 会议室是一个旨在处理小会议室中的视频会议和协作方案的会议设备。 禁用会议室对象时, 将删除分配给代表会议室的用户帐户的所有特定于 Skype for business 服务器的 Active Directory 属性。 但是，不会删除 Active Directory 用户帐户本身。  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |启用 Skype for business 服务器会议室。 若要启用会议室, 必须首先创建一个将代表该系统的 Active Directory 用户帐户。 请注意, 尽管会议室对象基于用户帐户, 但当你运行 Move-csuser cmdlet 时, 这些对象不会显示。  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |返回有关组织中使用的会议免责声明的信息。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |返回已配置为在组织中使用的所有 Skype for business Server 会议室的相关信息。  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |将 Skype for business Server 会议室对象从一个注册机构池移动到另一个注册机构。  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |从组织中使用的会议免责声明的标题和正文中清除文本。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |修改现有 Skype for Business Server 会议室的属性值。  <br/> |
   
**测试设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |测试用户对能否参与应用程序共享会议。  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |测试用户能否连接到其音频会议提供商。音频会议提供商是为组织提供会议服务的第三方公司。此外，音频会议提供商使外出且未连接到企业网络或 Internet 的用户可以通过音频参加会议。  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |测试一对用户能否加入音频/视频 (A/V) 会议。  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |验证是否有一对用户可以参与 Skype for Business Server web 会议, 包括共享或查看 PowerPoint 幻灯片、白板或投票等活动。 该 cmdlet 还验证 Skype for Business Server web 会议服务是否可以发现 Office Web Apps 服务器, 并且客户端可以通过 Office Web Apps 服务器上载 PowerPoint 文件进行广播。  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |检查用户是否可以参与电话拨入式会议会话。  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |针对拨号计划（以前称为位置配置文件）测试一个电话号码，返回将应用于该号码的规范化规则，以及应用该规范化规则后的转换号码。  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |测试三位用户是否能够参与 Skype for Business Server 移动服务会议。 移动服务使手机 (如 Iphone 和 Windows phone) 的用户可以执行诸如 exchange 即时消息和状态信息等操作。在内部存储和检索语音邮件, 而不是无线提供商。利用 Skype for Business 服务器功能, 例如通过工作电话和拨出式会议进行呼叫。  <br/> **注意:** Skype for Business Server 2019 不支持使用 MCX 的客户端。|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |测试一对用户使用统一通信 Web API (UCWA) 安排、加入然后召开联机会议的能力。  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |返回 Skype for Business 服务器中包含的数据会议功能的诊断信息。  <br/> |
   

