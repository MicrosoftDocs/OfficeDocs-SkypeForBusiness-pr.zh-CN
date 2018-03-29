---
title: 在 Skype for Business Server 2015 中管理电话拨入式会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 摘要： 了解如何管理业务服务器 2015 Skype 在拨入会议。
ms.openlocfilehash: 44427a9109fd061233d1c8676166788e162c7e08
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理电话拨入式会议
 
**摘要：**了解如何管理业务服务器 2015 Skype 在拨入会议。
  
本主题描述如何管理电话拨入式会议。 有关如何规划和配置拨入会议在部署的详细信息，请参阅[用于拨入会议在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/conferencing/dial-in-conferencing.md)和[业务服务器 2015年的 Skype 在配置拨入会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
您可以执行以下任务来管理拨入会议： 启用或禁用拨入会议、 管理访问号码、 管理拨入会议的 PIN 策略、 管理参加会议并保留通知，DTMF 修改键映射命令，并欢迎用户拨入会议。 
  
有关管理拨号计划的详细信息，请参阅[创建或修改的业务服务器 2015年的 Skype 的拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
PSTN 使用有关的详细信息，请参阅[配置语音策略、 PSTN 使用记录和业务 2015年的 Skype 语音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>管理拨入会议通过 Skype 业务服务器的控制面板

若要管理有关电话拨入式会议的信息：
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”。
    
若要管理有关拨号计划和 PSTN 用法的信息：
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**语音路由**”。
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>管理拨入会议通过 Skype 业务服务器管理外壳程序

若要管理拨入会议通过 Skype 业务服务器管理外壳程序，请使用以下 cmdlet:
  
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
|[移动 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |将现有的会议目录从一个池移动到另一个池。  <br/> |
|[新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |创建在组织中使用的新会议目录。  <br/> |
|[新 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |创建新的电话拨入式会议访问号码。  <br/> |
|[新 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |创建新的电话拨入式会议配置设置集合。 这些设置可确定当用户加入或离开拨入会议 Skype 业务服务器的响应方式。 特别是，返回有关是否要求参会者在加入会议时记录其姓名的信息，以及系统如何（甚至是否）通知某人已加入或退出呼叫的信息。  <br/> |
|[新 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |创建新的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[新 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |创建新的拨号计划。  <br/> |
|[删除 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |删除现有会议目录。  <br/> |
|[删除 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |删除现有的电话拨入式会议访问号码。  <br/> |
|[删除 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |删除电话拨入式会议配置设置的一个或多个集合。 这些设置可确定当用户加入或离开拨入会议 Skype 业务服务器的响应方式。  <br/> |
|[删除 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |删除现有的用于电话拨入式会议的双音多频 (DTMF) 信号设置的集合。  <br/> |
|[一组 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改现有电话拨入式会议接入号码的属性值。  <br/> |
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
   

