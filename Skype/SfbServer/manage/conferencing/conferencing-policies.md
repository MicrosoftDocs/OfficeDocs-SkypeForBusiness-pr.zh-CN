---
title: 管理会议策略Skype for Business Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要：了解如何在 Skype for Business Server 中管理会议策略。
ms.openlocfilehash: 8a4c209e711ba6ff332873147c0523839807b108
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835300"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>管理会议策略Skype for Business Server
 
**摘要：** 了解如何在会议部署中管理Skype for Business Server。
  
本主题介绍如何管理会议策略。 若要详细了解如何计划和部署会议，请参阅在 Skype for Business Server 中[](../../plan-your-deployment/conferencing/conferencing.md)规划会议[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
会议策略允许你定义各种安排和参与选项，范围从会议能否包括 IP 音频和视频到可参与会议的最大人数。 可以使用会议策略来管理会议的安全性、带宽和法律方面。
  
可以在三个级别定义会议策略：global 作用域、site 作用域和 user 作用域。 可以为不同范围的作用域中的特定用户应用设置。 如果将策略分配给用户，则优先使用这些设置。 如果未分配用户策略，则应用站点设置。 如果未应用用户策略或站点策略，则全局策略会提供默认设置。
  
默认情况下，全局策略已存在，因此不能创建新的全局策略。也不能删除现有全局策略，但可以更改现有全局策略以自定义默认设置。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用控制面板管理Skype for Business Server策略

若要使用控制面板管理Skype for Business Server策略：
  
1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"**会议策略"。**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server会议策略

若要使用命令行管理程序Skype for Business Server会议，请使用以下 cmdlet：
  
**会议策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |返回有关已配置为在组织中使用的会议策略的信息。  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每用户范围分配会议策略。  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |创建在组织中使用的新会议策略。  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |删除指定的会议策略。  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改现有的会议策略。  <br/> |
