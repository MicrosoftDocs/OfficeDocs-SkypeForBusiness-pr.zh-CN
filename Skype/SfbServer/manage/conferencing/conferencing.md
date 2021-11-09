---
title: 管理会议Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 摘要：了解如何在会议Skype for Business Server。
ms.openlocfilehash: 122b7d797983df9bb3ef6252234099869650a66e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845455"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>管理会议Skype for Business Server
 
**摘要：** 了解如何在会议Skype for Business Server。
  
本主题介绍如何管理会议。 若要详细了解如何计划和部署会议，请参阅在 Skype for Business Server 中[](../../plan-your-deployment/conferencing/conferencing.md)规划会议[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
在Skype for Business Server中，通过指定配置和策略设置来管理会议的详细信息，如下所示。 请注意，术语"会议"和"会议"有时可以互换使用。 但是，通常可以将会议视为会议的特定实例。
  
- **会议策略设置** 包含各种安排和参与选项，范围从会议能否包括 IP 音频和视频到可参与会议的最大人数。 可以使用会议策略来管理会议的安全性、带宽和法律方面。
    
    请注意，会议策略应用于用户或站点，不能应用于特定会议。 因此，可以提前几周创建会议的会议邀请，但限制会议策略应在会议启动前应用于会议组织者的 Skype for Business 帐户。 
    
    如果将专用帐户用于会议组织者角色，则会议策略可以仍分配给该帐户。 如果会议组织者使用常规Skype for Business帐户，则必须在会议完成后删除该策略。
    
- **会议配置** 设置规定用户可创建的会议类型，以及控制 (或) 匿名用户和电话拨入式会议用户能否加入这些会议的方式。 请注意，这些设置仅影响安排的会议。 每个池、每个站点或全局应用会议配置。
    
- **会议配置设置** 可确定诸如会议内容和讲义允许的最大大小等内容;应用程序共享会议服务的最大带宽量;存储限制和过期期限;支持客户端的内部和外部下载的 URL;指向用户可获取会议帮助和资源的内部 URL 和外部 URL 的指针;以及用于应用程序共享、客户端音频、文件传输和媒体流量的端口。
    
    这些设置允许您管理实际服务器本身。 这些设置只能使用命令行管理程序Skype for Business Server设置。 
    
- **拨入访问设置** 允许你定义有关用户是否从电话拨入以及如何拨入的信息。 You specify some of the dial-in access information， such as access number， from the Control Panel Conferencing tab and some dial-in information -- such as dial-in plan， voice policy， route， and PSTN usage -from the Control Panel Voice Routing tab.
    
- **PIN 策略设置** 允许你命名和定义参与者用于拨入访问的 PIN。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>使用控制面板Skype for Business Server命令行管理程序管理Skype for Business Server会议

通过使用控制面板或命令行管理程序，Skype for Business Server大多数会议策略和Skype for Business Server设置。 某些配置设置仅在命令行管理程序Skype for Business Server可用。
  
- 管理会议策略设置：
    
  - 在"控制面板"中，选择 **"会议|会议策略**。
    
  - 在 PowerShell 中，搜索 **-CsConferencingPolicy** cmdlet。
    
- 管理会议配置设置：
    
  - 在"控制面板"中，选择 **"会议|会议配置**。
    
  - 在Skype for Business Server命令行管理程序中，搜索 **-CsMeetingConfiguration** cmdlet。
    
- 管理拨入访问号码设置：
    
  - 在"控制面板"中，选择 **"会议|拨入访问号码**。
    
  - 在Skype for Business Server命令行管理程序中，搜索 **-CsDialInConferencing** cmdlet。
    
- 要管理拨入访问信息，例如拨号计划、语音策略、路由和 PSTN 用法： 
    
  - 在"控制面板"中，选择 **"会议|语音路由**。
    
  - 在Skype for Business Server命令行管理程序中，搜索 **-CsDialPlan** 和 **-CsVoice** cmdlet。
    
- 管理 PIN 策略设置：
    
  - 在"控制面板"中，选择 **"会议|PIN 策略**。
    
  - 在Skype for Business Server命令行管理程序中，搜索 **-CsPinPolicy** cmdlet。
    
- 若要管理会议配置设置，必须使用命令行管理Skype for Business Server命令行管理程序。 搜索 **-CsConferencingConfiguration** cmdlet。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server命令行管理程序 cmdlet

可以使用以下命令行管理Skype for Business Server cmdlet 管理会议： 
  
**会议策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |返回有关已配置为在组织中使用的会议策略的信息。 会议策略决定了会议中可以使用的功能，从会议能否加入 IP 音频和视频到可参加会议的最大人数，涵盖会议的方方面面。  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每用户范围分配会议策略。  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |创建在组织中使用的新会议策略。  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |删除指定的会议策略。  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改现有的会议策略。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关组织中当前使用的会议配置设置的信息。 会议配置设置帮助规定用户可创建的会议类型，并控制 (甚至) 匿名用户和电话拨入式会议用户如何加入这些会议。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在站点或服务范围创建新的会议配置设置集合。 请注意，这些设置仅影响安排的会议;它们不会影响通过单击"会议"中的"现在开会"选项创建Skype for Business。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除现有的会议配置设置集合。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。 会议设置可确定诸如会议内容和讲义允许的最大大小、内容宽限期 (即内容在删除) 之前存储的时间以及用于内部和外部下载受支持客户端的 URL 等内容。  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置的集合。  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
**拨入配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |返回有关配置为在组织中使用的会议目录的信息。 会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |检索有关用户Skype for Business Server或离开电话拨入式会议时如何响应的信息。  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |返回有关配置为在组织中使用的所有电话拨入式会议访问号码的信息。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |返回用于电话拨入式会议的双音多频 (DTMF) 信号设置。 通过 DTMF，拨号接入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |返回支持与电话拨入式会议一Skype for Business Server语言列表，包括地域/少数语言。 这些语言用于将音频消息和说明中继到使用电话参与会议的用户。  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |返回有关您组织中使用的拨号计划的信息。  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |向一个或多个用户或组分配拨号计划。  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |将会议目录从 Microsoft Office Communications Server 2007 R2 导入Skype for Business Server。 这有助于在 Communications Server 2007 R2 Skype for Business Server Office互操作性。  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |将现有的会议目录从一个池移动到另一个池。 会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |创建在组织中使用的新会议目录。 会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |创建新的电话拨入式会议访问号码。  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |创建新的电话拨入式会议配置设置集合。 这些设置确定Skype for Business Server加入或离开电话拨入式会议时如何响应。 特别是，将返回有关是否要求参与者在加入会议时记录其姓名的信息，以及 (或系统是否) 系统宣布有人已加入或已离开呼叫。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |创建新的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |创建新的拨号计划。  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |删除现有会议目录。 会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |删除现有的电话拨入式会议访问号码。  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |删除电话拨入式会议配置设置的一个或多个集合。 这些设置确定Skype for Business Server加入或离开电话拨入式会议时如何响应。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |删除用于电话拨入式会议 (DTMF) 信号设置的现有双音多频集合。  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改现有电话拨入式会议接入号码的属性值。 电话拨入式会议为用户提供了一种使用“常规”电话、移动电话或公用电话交换网 (PSTN) 上的其他设备加入会议的音频部分的方法。  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改确定用户Skype for Business Server离开电话拨入式会议时如何响应的设置。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改用于电话拨入式会议的双音多频 (DTMF) 信号设置。  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改现有的拨号计划。  <br/> |
   
**PIN 策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |返回有关配置为在组织 (PIN) 客户端个人标识号的信息。 通过 PIN 身份验证，Skype for Business Server提供 PIN 而不是用户名和密码来访问密码。  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |向一个或一组用户分配客户端个人标识号 (PIN) 策略。  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |使用 PIN 策略创建新的客户端个人标识 () 号。  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |删除指定的个人标识号 (PIN) 策略。  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一个或多个现有的客户端个人标识号 (PIN) 策略。  <br/> |
   
**其他会议设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |禁用Skype for Business Server会议室。 会议室是一个旨在处理小会议室中的视频会议和协作方案的会议设备。 禁用会议室对象时，将删除分配给Skype for Business Server该会议室的用户帐户的所有特定于 Active Directory 的属性。 但是，不会删除 Active Directory 用户帐户本身。  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |启用Skype for Business Server会议室。 要启用某会议室，您必须先创建一个代表该系统的 Active Directory 用户帐户。 请注意，尽管会议室对象基于用户帐户，但在您运行 Get-CsUser cmdlet 时不会出现这些对象。  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |返回有关组织中使用的会议免责声明的信息。 会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |返回有关配置为Skype for Business Server组织使用的所有会议室的信息。  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |将Skype for Business Server一个注册器池移动到另一个注册器池。  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |从组织中使用的会议免责声明的标题和正文中清除文本。 会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |修改现有会议室Skype for Business Server属性值。  <br/> |
   
**测试设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |测试用户对能否参与应用程序共享会议。  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |测试用户能否连接到其音频会议提供商。音频会议提供商是为组织提供会议服务的第三方公司。此外，音频会议提供商使外出且未连接到企业网络或 Internet 的用户可以通过音频参加会议。  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |测试一对用户能否参与音频/视频 (A/V) 会议。  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |验证一对用户能否参加 Skype for Business Server Web 会议，该会议包括共享或查看PowerPoint幻灯片、白板或投票等活动。 此 cmdlet 还验证 Skype for Business Server Web 会议服务能否发现 Office Web Apps Server，以及客户端能否上载 PowerPoint 文件供 Office Web Apps Server 广播。  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |检查用户能否参与电话拨入式会议会话。  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |针对拨号计划（以前称为位置配置文件）测试一个电话号码，返回将应用于该号码的规范化规则，以及应用该规范化规则后的转换号码。  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |测试三个用户能否参加 Skype for Business Server Mobility Service 会议。 Mobility Service 使移动电话（如 iPhone 和 Windows 电话）的用户能够执行诸如交换即时消息和状态信息等操作;在内部而不是与其无线提供商一起存储和检索语音邮件;以及利用Skype for Business Server电话呼叫和电话拨出式会议等功能。  <br/> **注意：** 使用 MCX 的客户端在 2019 Skype for Business Server不受支持。|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |测试一对用户能否使用 UCWA (统一通信 Web API 安排、加入) 。  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |返回报告中包含的数据会议功能的诊断Skype for Business Server。  <br/> |
