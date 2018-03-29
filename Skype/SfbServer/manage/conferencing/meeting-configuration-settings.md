---
title: 在 Skype for Business Server 2015 中管理会议配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要： 了解如何管理会议在 Skype 业务服务器 2015年的配置设置。
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理会议配置设置
 
**摘要：**了解如何管理会议在 Skype 业务服务器 2015年的配置设置。
  
本主题描述如何管理会议配置设置。 有关如何规划和部署会议的详细信息，请参见[会议在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/conferencing/conferencing.md)和[业务服务器 2015年的 Skype 在部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议配置设置规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。 请注意，这些设置只影响已安排的会议;它们不会影响通过单击 Skype 业务中的立即开会选项创建的特别会议。
  
会议配置设置定义以下事项：
  
- 从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅
    
- 谁能成为演示者
    
- 默认情况下是否分配会议类型
    
- 默认情况下是否允许匿名（未经身份验证）用户加入会议
    
通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳，您可以定义会议的特征。 
  
您可以指定会议 （默认情况下创建） 的全局级别设置，在站点级别，或池级别。 默认情况下，全局设置定义会议体验。 如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。 如果未创建池级别的设置，则应用站点级别的设置（如果存在）。 如果未定义站点级别的设置，则全局设置将应用于所有会议。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>通过 Skype 业务服务器控制面板管理会议设置

通过 Skype 业务服务器控制面板管理会议设置：
  
1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>通过 Skype 业务服务器管理外壳程序管理会议设置

若要管理会议通过 Skype 业务服务器管理外壳程序，请使用以下 cmdlet:
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |返回有关当前组织中使用的会议配置设置的信息。  <br/> |
|[新 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在 site 或服务范围创建新的会议配置设置集合。  <br/> |
|[删除 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |删除会议配置设置的现有集合。  <br/> |
|[一组 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改组织中当前使用的会议配置设置。  <br/> |
   

