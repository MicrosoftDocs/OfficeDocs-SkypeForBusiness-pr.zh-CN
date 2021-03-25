---
title: 在 Skype for Business Server 中管理电话拨入式会议
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 摘要：了解如何在 Skype for Business Server 中管理电话拨入式会议。
ms.openlocfilehash: 6bf5f13075b54d904ae70bc1b2106253442135db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119481"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中管理电话拨入式会议
 
**摘要：** 了解如何在 Skype for Business Server 中管理电话拨入式会议。
  
本主题介绍如何管理电话拨入式会议。 若要详细了解如何在部署中计划和配置电话拨入式会议，请参阅在 Skype [for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) 中规划电话拨入式会议和在 [Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md)中配置电话拨入式会议。
  
您可以执行以下任务来管理电话拨入式会议：启用或禁用电话拨入式会议、管理访问号码、管理电话拨入式会议的 PIN 策略、管理会议加入和离开通知、修改 DTMF 命令的键映射以及欢迎用户加入电话拨入式会议。 
  
有关管理拨号计划的信息，请参阅在 Skype for Business Server 中创建 [或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
有关 PSTN 用法详细信息，请参阅在 Skype for Business 中配置语音策略 [、PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)用法记录和语音路由。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板管理电话拨入式会议

要管理有关电话拨入式会议的信息，
  
1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”。
    
要管理有关拨号计划和 PSTN 用法的信息，
  
1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击"**语音路由"。**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序管理电话拨入式会议

若要使用 Skype for Business Server 命令行管理程序管理电话拨入式会议，请使用以下 cmdlet：
  
**拨入配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |返回有关配置为在组织中使用的会议目录的信息。 会议目录用于帮助电话拨入式会议用户查找会议信息。  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |检索有关用户加入或离开电话拨入式会议时 Skype for Business Server 如何响应的信息。  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |返回有关配置为在组织中使用的所有电话拨入式会议访问号码的信息。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |返回用于电话拨入式会议 (双音) DTMF 信号设置。 通过 DTMF，拨号接入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |返回支持用于 Skype for Business Server 电话拨入式会议的语言列表，包括区域语言/少数语言。 这些语言用于将音频消息和说明中继到使用电话参与会议的用户。  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |返回有关您组织中使用的拨号计划的信息。  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |向一个或多个用户或组分配拨号计划。  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |将会议目录从 Microsoft Office Communications Server 2007 R2 导入 Skype for Business Server。 这有助于提供 Skype for Business Server 和 Office Communications Server 2007 R2 之间的互操作性。  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |将现有的会议目录从一个池移动到另一个池。  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |创建在组织中使用的新会议目录。  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |创建新的电话拨入式会议访问号码。  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |创建新的电话拨入式会议配置设置集合。 这些设置确定当用户加入或离开电话拨入式会议时 Skype for Business Server 如何响应。 特别是，将返回有关是否要求参与者在加入会议时记录其姓名的信息，以及 (或系统是否) 有人已加入或离开呼叫的信息。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |创建用于电话拨入式会议 (DTMF) 信号设置的新双音多频集合。  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |创建新的拨号计划。  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |删除现有的会议目录。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |删除现有的电话拨入式会议访问号码。  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |删除电话拨入式会议配置设置的一个或多个集合。 这些设置确定当用户加入或离开电话拨入式会议时 Skype for Business Server 如何响应。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |删除用于电话拨入式会议 (DTMF) 信号设置的现有双音多频集合。  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改现有电话拨入式会议接入号码的属性值。  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改用于确定用户加入或离开电话拨入式会议时 Skype for Business Server 如何响应的设置。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改用于电话拨入式会议的双音多频 (DTMF) 信号设置。  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改现有的拨号计划。  <br/> |
   
**PIN 策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |返回有关配置为在组织 (PIN) 客户端个人标识号的信息。 通过 PIN 身份验证，用户可以通过提供 PIN 而不是用户名和密码来访问 Skype for Business Server。  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |向一个或一组用户分配客户端个人标识号 (PIN) 策略。  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |使用 PIN 策略创建新的客户端个人标识 () 号。  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |删除指定的个人标识号 (PIN) 策略。  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一个或多个现有的客户端个人标识号 (PIN) 策略。  <br/> |
