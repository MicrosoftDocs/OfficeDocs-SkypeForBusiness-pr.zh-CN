---
title: 管理会议中 Skype Business Server （英文）
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 摘要： 了解如何为业务服务器管理 Skype 中的会议。
ms.openlocfilehash: 031c0b19d8132d9c8658702a5bdb30d84b418ae3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973337"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>管理会议中 Skype Business Server （英文）
 
**摘要：** 了解如何为业务服务器管理 Skype 中的会议。
  
本主题描述如何管理会议。 有关如何规划和部署会议的详细信息，请参阅[Plan for Business Server 的 Skype 中的会议](../../plan-your-deployment/conferencing/conferencing.md)和[Skype 业务服务器中的部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
在业务服务器 Skype，您通过指定，如下所示的配置和策略设置管理会议的详细信息。 请注意英语中的术语 conferencing（会议）和 meeting（会议）有时候互换使用。 但是可以将 meeting 视为 conferencing 的具体实例。
  
- **会议策略设置**包含各种安排和参与选项，包括从会议能否包括 IP 音频和视频，到可参与会议的最大人数。 可以使用会议策略管理会议的安全性、带宽以及法律发面的问题。
    
    请注意，会议策略应用于用户或站点，不能应用于具体会议。 因此，可以创建会议的会议邀请一些周提前，但严格的会议策略应应用于会议组织者的 Skype 业务帐户，只需在会议开始之前。 
    
    如果专用帐户用于会议组织者角色，会议策略可以一直分配给该帐户。 如果会议组织者使用常规的 Skype 业务帐户，必须完成会议后删除策略。
    
- **会议配置设置**规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。请注意，这些设置只影响已安排的会议。会议配置按池、按站点或全局应用。
    
- **会议配置设置**确定诸如最大允许大小会议内容和讲义;最大数量的带宽为应用程序共享会议服务;存储限制和过期时段;内部和外部 Url 下载的受支持的客户端;指向内部和外部 Url，用户可从中获取会议帮助和资源。和用于应用程序共享、 客户端音频、 文件传输和媒体流量的端口。
    
    这些设置可让你管理实际服务器本身。 仅可以使用适用于业务 Server 命令行管理程序 Skype 设置这些设置。 
    
- **拨入访问设置**允许你定义有关用户是否从电话拨入，以及如何拨入的信息。 你可以从控制面板“会议”选项卡指定某些拨入访问信息，如访问号码，可以从控制面板“语音路由”选项卡指定某些拨入信息，如拨号计划、语音策略、路由和 PSTN 用法。
    
- **PIN 策略设置**可让你指定和定义参与者用于拨入访问的 PIN。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell 管理会议

使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以管理大多数会议策略和配置设置。 配置提供了某些设置只能由 Skype 用于业务 Server Management Shell。
  
- 若要管理会议策略设置：
    
  - 在控制面板中，选择“**会议 | 会议策略**”。
    
  - 在 PowerShell 中搜索 **-CsConferencingPolicy** cmdlet。
    
- 若要管理会议配置设置：
    
  - 在控制面板中，选择“**会议 | 会议配置**”。
    
  - 在业务 Server Management Shell 的 Skype，搜索 **-CsMeetingConfiguration** cmdlet。
    
- 若要管理拨入访问号码设置：
    
  - 在控制面板中，选择“**会议 | 拨入访问号码**”。
    
  - 在业务 Server Management Shell 的 Skype，搜索 **-CsDialInConferencing** cmdlet。
    
- 若要管理拨入访问信息，如拨号计划、语音策略、路由和 PSTN 用法： 
    
  - 在控制面板中，选择“**会议 | 语音路由**”。
    
  - 在业务 Server Management Shell 的 Skype，搜索 **-CsDialPlan**和 **-CsVoice** cmdlet。
    
- 管理 PIN 策略设置：
    
  - 在控制面板中，选择“**会议 | PIN 策略**”。
    
  - 在业务 Server Management Shell 的 Skype，搜索 **-CsPinPolicy** cmdlet。
    
- 若要管理会议配置设置，您必须使用 Skype 业务 Server Management Shell。 搜索 **-CsConferencingConfiguration** cmdlet。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype 业务 Server 命令行管理程序 cmdlet

以下 Skype 业务 Server Management Shell cmdlet 可用于管理会议： 
  
**会议策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |返回有关已配置为在组织中使用的会议策略的信息。会议策略决定了会议中可以使用的功能，从会议能否加入 IP 音频和视频到可参加会议的最大人数，涵盖会议的方方面面。  <br/> |
|[Grant-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每用户范围分配会议策略。  <br/> |
|[New-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |创建在组织中使用的新会议策略。  <br/> |
|[Remove-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |删除指定的会议策略。  <br/> |
|[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改现有会议策略。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关组织中当前正在使用的会议配置设置的信息。会议配置设置帮助规定用户可创建的会议类型，以及控制匿名用户和电话拨入式会议用户如何（甚至是否）可以加入这些会议。  <br/> |
|[New-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在 site 或服务范围创建新的会议配置设置集合。 请注意，这些设置仅影响安排的会议;它们不会影响通过单击 Skype for Business 中的立即开会选项创建的临时会议。  <br/> |
|[Remove-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除会议配置设置的现有集合。  <br/> |
|[通过 Set-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。会议设置可确定诸如会议内容和讲义允许的最大大小、内容宽限期（即内容在被删除前存储的时间）以及用于内部和外部下载支持的客户端的 URL 等信息。  <br/> |
|[New-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[删除 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置的集合。  <br/> |
|[Set-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
**拨号配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-csconferencedirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |返回有关配置为在组织中使用的会议目录的信息。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Get-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |检索有关如何 Skype 业务服务器响应当用户加入或离开电话拨入式会议信息。  <br/> |
|[Get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |返回有关配置为在组织中使用的所有电话拨入式会议访问号码的信息。  <br/> |
|[Get-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |返回用于电话拨入式会议的双音多频 (DTMF) 信号设置。通过 DTMF，拨号接入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。  <br/> |
|[Get-csdialinconferencinglanguagelist](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |返回语言版本，包括与 Skype 用于支持 Business Server 电话拨入式会议区域/少数语言列表。 这些语言用于将音频消息和说明中继到使用电话参与会议的用户。  <br/> |
|[Get-csdialplan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |返回有关您组织中使用的拨号计划的信息。  <br/> |
|[Grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |向一个或多个用户或组分配拨号计划。  <br/> |
|[Import-cslegacyconferencedirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |将导入的会议目录从 Microsoft Office Communications Server 2007 R2 到 Skype 业务服务器。 这有助于提供 Skype 业务 server 和 Office Communications Server 2007 R2 之间的互操作性。  <br/> |
|[Move-csconferencedirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |将现有的会议目录从一个池移动到另一个池。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |创建在组织中使用的新会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[New-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |创建新的电话拨入式会议访问号码。  <br/> |
|[新 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |创建新的电话拨入式会议配置设置集合。 这些设置可确定业务服务器 Skype 如何响应用户加入或离开电话拨入式会议时。 特别是，返回有关是否要求参会者在加入会议时记录其姓名的信息，以及系统如何（甚至是否）通知某人已加入或退出呼叫的信息。  <br/> |
|[新 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |创建新的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[新 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |创建新的拨号计划。  <br/> |
|[Remove-csconferencedirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |删除现有会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Remove-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |删除现有的电话拨入式会议访问号码。  <br/> |
|[Remove-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |删除电话拨入式会议配置设置的一个或多个集合。 这些设置可确定业务服务器 Skype 如何响应用户加入或离开电话拨入式会议时。  <br/> |
|[Remove-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |删除现有的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[Set-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改现有电话拨入式会议接入号码的属性值。电话拨入式会议为用户提供了一种使用"常规"电话、移动电话或公用电话交换网 (PSTN) 上的其他设备加入会议的音频部分的方法。  <br/> |
|[Set-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改确定业务服务器 Skype 如何响应用户加入或离开电话拨入式会议时的设置。  <br/> |
|[通过 Set-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改用于电话拨入式会议的双音多频 (DTMF) 信号设置。  <br/> |
|[Set-csdialplan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改现有的拨号计划。  <br/> |
   
**PIN 策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |返回有关配置为在组织中使用的客户端个人标识号 (PIN) 策略的信息。 PIN 身份验证，用户可以访问通过提供而不是用户名和密码 PIN Skype 业务服务器。  <br/> |
|[Grant-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |向一个或一组用户分配客户端个人标识号 (PIN) 策略。  <br/> |
|[新 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |创建新的客户端个人标识号 (PIN) 策略。  <br/> |
|[Remove-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |删除指定的个人标识号 (PIN) 策略。  <br/> |
|[Set-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一个或多个现有的客户端个人标识号 (PIN) 策略。  <br/> |
   
**其他会议设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |禁用 Business Server 会议室 Skype。 会议室是一个旨在处理小会议室中的视频会议和协作方案的会议设备。 当您禁用会议室对象删除分配给该用户帐户值，该值代表会议室的业务特定于服务器的 Active Directory 属性的所有 Skype。 但是，不会删除 Active Directory 用户帐户本身。  <br/> |
|[Enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |启用 Business Server 会议室 Skype。 若要启用会议室，必须先创建 Active Directory 用户帐户将表示该系统。 注意，尽管会议室对象基于用户帐户，运行 Get-csuser cmdlet 时，这些对象将不显示。  <br/> |
|[Get-csconferencedisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |返回有关组织中使用的会议免责声明的信息。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[Get-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |返回有关所有 Skype 业务服务器配置为在组织中使用的会议室的信息。  <br/> |
|[Move-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |将 Skype 移动会议到另一个注册器池会议室对象的业务服务器。  <br/> |
|[删除 CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |从组织中使用的会议免责声明的标题和正文中清除文本。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。  <br/> |
|[Set-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |修改现有的业务服务器会议室 Skype 的属性值。  <br/> |
   
**测试设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Test-csasconference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |测试用户对能否参与应用程序共享会议。  <br/> |
|[Test-csaudioconferencingprovider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |测试用户能否连接到其音频会议提供商。音频会议提供商是为组织提供会议服务的第三方公司。此外，音频会议提供商使外出且未连接到企业网络或 Internet 的用户可以通过音频参加会议。  <br/> |
|[Test-csavconference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |测试一对用户能否加入音频/视频 (A/V) 会议。  <br/> |
|[Test-csdataconference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |验证一对用户可以参与 Business Server web 会议，其中包括共享或查看 PowerPoint 幻灯片、 白板或投票等活动 Skype。 此 cmdlet 还验证 Business Server web 会议服务的 Skype 可以发现 Office Web Apps Server 和客户端可以上载 PowerPoint 文件以通过 Office Web Apps Server 的广播。  <br/> |
|[Test-csdialinconferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |检查用户是否可以参与电话拨入式会议会话。  <br/> |
|[测试 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |针对拨号计划（以前称为位置配置文件）测试一个电话号码，返回将应用于该号码的规范化规则，以及应用该规范化规则后的转换号码。  <br/> |
|[Test-csmcxconference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |测试的三个用户参与业务服务器 Mobility Service 会议 Skype 的能力。 Mobility Service 允许用户的移动电话，如 Iphone 和 Windows Phone 事情交换即时消息和状态信息;存储和检索与其无线服务提供商; 而不是内部的语音邮件和充分利用 Skype 的业务服务器功能，例如，通过单位电话号码和拨出式会议的呼叫。  <br/> **注意：** 使用 MCX 的客户端不支持在 Skype 业务服务器 2019年。|
|[Test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |测试一对用户使用统一通信 Web API (UCWA) 安排、加入然后召开联机会议的能力。  <br/> |
|[调试 CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |返回诊断信息业务服务器 Skype 中包含的数据会议功能。  <br/> |
   

