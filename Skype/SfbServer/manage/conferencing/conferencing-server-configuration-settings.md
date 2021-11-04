---
title: 管理会议服务器配置设置Skype for Business Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：了解如何在 Skype for Business Server 中管理会议服务器配置Skype for Business Server。
ms.openlocfilehash: 14fed927e18d291cf17a5c00ee82dac7ef80a6d1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773702"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>管理会议服务器配置设置Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中管理会议服务器配置Skype for Business Server。
  
本主题介绍如何管理会议配置设置。 若要详细了解如何计划和部署会议，请参阅在 Skype for Business Server 中[](../../plan-your-deployment/conferencing/conferencing.md)规划会议[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
会议配置设置可确定诸如会议内容和讲义允许的最大大小等内容;应用程序共享会议服务的最大带宽量;存储限制和过期期限;支持客户端的内部和外部下载的 URL;指向用户可获取会议帮助和资源的内部 URL 和外部 URL 的指针;以及用于应用程序共享、客户端音频、文件传输和媒体流量的端口。 这些设置允许您管理实际服务器本身。 这些设置可以使用命令行管理程序Skype for Business Server设置。
  
在安装Skype for Business Server时，系统会为您提供一个会议配置设置集合， (全局集合) 。 如果您需要为站点或服务创建自定义设置，则可以使用 **New-CsConferencingConfiguration** cmdlet 来完成。 请注意，新设置只能在站点范围或服务范围应用;您无法创建新的会议配置设置的全局集合，但可以使用 **Set-CsConferencingConfiguration** cmdlet 修改全局集合。 此外，任何站点或服务都不得承载多个设置集合。 如果尝试为 Redmond 站点创建新设置，并且 Redmond 站点已经托管了一组会议配置设置，则命令将失败。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序管理Skype for Business Server配置设置

若要使用命令行管理程序管理Skype for Business Server配置设置，请使用以下 cmdlet：
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置集合。  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
以下命令为 Site：Redmond 站点服务器创建一个新的会议配置 (site：Redmond) 。 本示例中，Organization (一) 参数，该参数用于将 Organization 属性的值设置为 Litwareinc： 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

请注意，每个站点只能有一个这样的集合，因此，如果 Redmond 站点已经有一个会议配置设置集合，此命令将失败。 
  
下一个示例定义一个新的会议配置设置集合，这些设置最初存储在内存中，稍后再应用到 Redmond 站点。 
  
第一个命令使用 **New-CsConferencingConfiguration** cmdlet 创建存储在变量 $x 中的新的内存中设置集合。 InMemory 参数指定应在内存中创建集合，而不是立即应用于 Redmond 站点。
  
创建集合后，第二个命令将 Organization 属性的值设置为 Litwareinc。 
  
最后，第三个命令使用 **Set-CsConferencingConfiguration** cmdlet 将新设置实际应用于 Redmond 站点：
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

如果不调用 **Set-CsConferencingConfiguration** cmdlet，则新设置永远不会生效。 相反，一旦结束会话或删除Windows PowerShell，它们就会$x。
