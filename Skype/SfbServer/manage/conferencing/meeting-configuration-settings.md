---
title: 管理会议中 Skype 业务服务器的配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要： 了解如何管理会议中 Skype 业务服务器的配置设置。
ms.openlocfilehash: 90d1004101f1dd3b4737c7bfa4414438a65c54a6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883219"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>管理会议中 Skype 业务服务器的配置设置
 
**摘要：** 了解如何管理会议中 Skype 业务服务器的配置设置。
  
本主题描述如何管理会议配置设置。 有关如何规划和部署会议的详细信息，请参阅[Plan for Business Server 的 Skype 中的会议](../../plan-your-deployment/conferencing/conferencing.md)和[Skype 业务服务器中的部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议配置设置规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。 请注意，这些设置仅影响安排的会议;它们不会影响通过单击 Skype for Business 中的立即开会选项创建的临时会议。
  
会议配置设置定义以下事项：
  
- 从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅
    
- 谁能成为演示者
    
- 默认情况下是否分配会议类型
    
- 默认情况下是否允许匿名（未经身份验证）用户加入会议
    
使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以定义的会议的特征。 
  
您可以指定会议在全局级别 （默认情况下创建） 的设置，网站级别或池级别。 默认情况下，全局设置定义会议体验。 如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。 如果未创建池级别的设置，则应用站点级别的设置（如果存在）。 如果未定义站点级别的设置，则全局设置将应用于所有会议。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 管理会议设置

使用适用于业务 Server Control Panel Skype 管理会议设置：
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server Management Shell 管理会议设置

若要使用 Skype 业务 Server Management Shell 管理会议，请使用以下 cmdlet:
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关当前组织中使用的会议配置设置的信息。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在 site 或服务范围创建新的会议配置设置集合。  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除会议配置设置的现有集合。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   

