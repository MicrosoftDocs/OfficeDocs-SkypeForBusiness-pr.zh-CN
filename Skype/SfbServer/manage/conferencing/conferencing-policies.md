---
title: 在 Skype for Business Server 2015 中管理会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要： 了解如何管理业务服务器 2015 Skype 会议策略。
ms.openlocfilehash: 48ae623a9571b848ccb70b377416343eccca0c1c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-policies-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理会议策略
 
**摘要：**了解如何管理业务服务器 2015 Skype 会议策略。
  
本主题描述如何管理会议策略。 有关如何规划和部署会议的详细信息，请参见[会议在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/conferencing/conferencing.md)和[业务服务器 2015年的 Skype 在部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议策略允许你定义各种安排和参与选项，包括从会议能否包括 IP 音频和视频，到可参与会议的最大人数。可以使用会议策略管理会议的安全性、带宽以及法律发面的问题。
  
可以在三个级别定义会议策略：全局作用域、站点作用域和用户作用域。 可以为不同范围的作用域中的特定用户应用设置。 如果为用户分配策略，则优先应用这些设置。 如果未分配用户策略，则应用站点设置。 如果未应用用户策略或站点策略，则全局策略会提供默认设置。
  
默认情况下，全局策略已存在，因此不能创建新的全局策略。 也不能删除现有全局策略，但可以更改现有全局策略以自定义默认设置。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>通过 Skype 业务服务器控制面板管理会议策略

通过 Skype 业务服务器控制面板管理会议策略：
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>通过 Skype 业务服务器管理外壳程序管理会议策略

若要管理会议通过 Skype 业务服务器管理外壳程序，请使用以下 cmdlet:
  
**会议策略设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |返回有关已配置为在组织中使用的会议策略的信息。  <br/> |
|[授予 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每用户范围分配会议策略。  <br/> |
|[新 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |创建在组织中使用的新会议策略。  <br/> |
|[删除 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |删除指定的会议策略。  <br/> |
|[一组 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改现有会议策略。  <br/> |
   

