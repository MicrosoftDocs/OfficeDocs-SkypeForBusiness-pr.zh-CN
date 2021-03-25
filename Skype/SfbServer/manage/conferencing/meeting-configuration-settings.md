---
title: 在 Skype for Business Server 中管理会议配置设置
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要：了解如何在 Skype for Business Server 中管理会议配置设置。
ms.openlocfilehash: 1e6ef11992a547456d2a971c2f8de6f3097b166e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119431"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中管理会议配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中管理会议配置设置。
  
本主题介绍如何管理会议配置设置。 若要详细了解如何计划和部署会议，请参阅在 [Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) 中规划会议和在 Skype for Business Server 中部署 [会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议配置设置规定用户可创建的会议类型，以及控制 (或者) 匿名用户和电话拨入式会议用户能否加入这些会议。 请注意，这些设置仅影响安排的会议;它们不会影响通过单击 Skype for Business 中的"现在开会"选项创建临时会议。
  
会议配置设置定义以下内容：
  
- 从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅
    
- 谁能成为演示者
    
- 默认情况下是否分配会议类型
    
- 默认情况下是否允许匿名（未经身份验证）用户加入会议
    
可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序定义会议的特征。 
  
可以在全局级别指定会议设置 (默认创建) 、站点级别或池级别。 默认情况下，全局设置定义会议体验。 如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。 如果未创建池级别的设置，则应用站点级别的设置（如果存在）。 如果未定义站点级别的设置，则全局设置将应用于所有会议。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板管理会议设置

若要使用 Skype for Business Server 控制面板管理会议设置：
  
1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序管理会议设置

若要使用 Skype for Business Server 命令行管理程序管理会议，请使用以下 cmdlet：
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关组织中当前使用的会议配置设置的信息。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在站点或服务范围创建新的会议配置设置集合。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除现有的会议配置设置集合。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
