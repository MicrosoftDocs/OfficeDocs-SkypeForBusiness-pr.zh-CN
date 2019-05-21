---
title: 管理 Skype for Business 服务器中的会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '摘要: 了解如何在 Skype for Business Server 中管理会议配置设置。'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283737"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的会议配置设置
 
**摘要:** 了解如何在 Skype for Business Server 中管理会议配置设置。
  
本主题描述如何管理会议配置设置。 有关如何规划和部署会议的详细信息, 请参阅在 skype for business[服务器中规划会议](../../plan-your-deployment/conferencing/conferencing.md)和[在 Skype for Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议配置设置规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。 请注意, 这些设置仅影响计划的会议;它们不会影响通过单击 Skype for Business 中的 "立即开会" 选项创建的临时会议。
  
会议配置设置定义以下事项：
  
- 从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅
    
- 谁能成为演示者
    
- 默认情况下是否分配会议类型
    
- 默认情况下是否允许匿名（未经身份验证）用户加入会议
    
你可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器定义会议的特征。 
  
可以在全局级别 (默认情况下创建)、网站级别或池级别指定会议设置。 默认情况下，全局设置定义会议体验。 如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。 如果未创建池级别的设置，则应用站点级别的设置（如果存在）。 如果未定义站点级别的设置，则全局设置将应用于所有会议。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server "控制面板" 管理会议设置

若要通过使用 Skype for Business 服务器控制面板管理会议设置, 请执行以下操作:
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序管理会议设置

若要使用 Skype for Business Server Management Shell 管理会议, 请使用以下 cmdlet:
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关当前组织中使用的会议配置设置的信息。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在 site 或服务范围创建新的会议配置设置集合。  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除会议配置设置的现有集合。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   

