---
title: 管理会议配置设置Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: Summary： Learn how to manage meeting configuration settings in Skype for Business Server.
ms.openlocfilehash: fe622a04e25795471e8f757c352fcaebd7fb1e3b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754831"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>管理会议配置设置Skype for Business Server
 
**摘要：** 了解如何在会议环境中管理Skype for Business Server。
  
本主题介绍如何管理会议配置设置。 若要详细了解如何计划和部署会议，请参阅在 Skype for Business Server 中[](../../plan-your-deployment/conferencing/conferencing.md)规划会议[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
会议配置设置规定用户可创建的会议类型，以及控制 (或) 匿名用户和电话拨入式会议用户能否加入这些会议的方式。 请注意，这些设置仅影响安排的会议;它们不会影响通过单击"会议"中的"现在开会"选项创建Skype for Business。
  
会议配置设置定义以下内容：
  
- 从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅
    
- 谁能成为演示者
    
- 默认情况下是否分配会议类型
    
- 默认情况下是否允许匿名（未经身份验证）用户加入会议
    
可以使用控制面板或命令行管理程序Skype for Business Server会议Skype for Business Server特征。 
  
您可以在默认情况下创建会议级别的全局 (、) 级别或池级别指定会议设置。 默认情况下，全局设置定义会议体验。 如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。 如果未创建池级别的设置，则应用站点级别的设置（如果存在）。 如果未定义站点级别的设置，则全局设置将应用于所有会议。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>使用控制面板Skype for Business Server会议设置

若要使用"控制面板"Skype for Business Server会议设置：
  
1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server会议设置

若要使用命令行管理程序Skype for Business Server会议，请使用以下 cmdlet：
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关组织中当前使用的会议配置设置的信息。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在站点或服务范围创建新的会议配置设置集合。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除现有的会议配置设置集合。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
