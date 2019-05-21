---
title: 在 Skype for Business Server 中管理会议服务器配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: '摘要: 了解如何在 Skype for Business Server 中管理会议服务器配置设置。'
ms.openlocfilehash: 190cd78e3c81f98859c40fe386fae2c4fd934a8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288997"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中管理会议服务器配置设置
 
**摘要:** 了解如何在 Skype for Business Server 中管理会议服务器配置设置。
  
本主题描述如何管理会议配置设置。 有关如何规划和部署会议的详细信息, 请参阅在 skype for business[服务器中规划会议](../../plan-your-deployment/conferencing/conferencing.md)和[在 Skype for Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议配置设置决定了会议内容和讲义的最大允许大小;应用程序共享会议服务的最大带宽量;存储限额和到期期;支持的客户端的内部和外部下载的 Url;指向用户可获取会议帮助和资源的内部和外部 Url 的指针;以及用于应用程序共享、客户端音频、文件传输和媒体流量的端口。 这些设置可让你管理实际服务器本身。 可以使用 Skype for Business Server 命令行管理程序设置这些设置。
  
安装 Skype for Business 服务器时, 系统会为你提供单个会议配置设置集合 (全局集合)。 如果需要为站点或服务创建自定义设置，可以使用 **New-CsConferencingConfiguration** cmdlet 来完成。 请注意，只能在站点范围或服务范围应用新设置；你无法创建新的会议配置设置全局集合，但是可以使用 **Set-CsConferencingConfiguration** 来修改全局集合。 此外，站点和服务都不能托管多个设置集合。 如果你尝试为 Redmond 站点创建新设置，而 Redmond 站点已托管一个会议配置设置集合，则命令将会失败。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序管理会议配置设置

若要使用 Skype for Business Server Management Shell 管理会议配置设置, 请使用以下 cmdlet:
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置集合。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
下面的命令为 Redmond 站点 (site:Redmond) 创建新的会议配置设置集合。在此示例中，包括一个额外的参数 (Organization)，该参数用于将 Organization 属性的值设置为 Litwareinc： 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

请注意，每个站点只能有一个这样的集合，因此，如果 Redmond 站点已经有一个会议配置设置集合，此命令将失败。 
  
下一个示例定义了一个新的会议配置设置集合，这些设置最初存储在内存中，然后在晚些时候应用到 Redmond 站点。 
  
第一条命令使用 **New-CsConferencingConfiguration** cmdlet 创建一个新的保存在内存中的设置集合，并存储在变量 $x 中。 InMemory 参数指定应在内存中创建集合，而不立即将该集合应用于 Redmond 站点。
  
创建集合后，第二个命令将 Organization 属性的值设置为 Litwareinc。 
  
最后，第三个命令使用 **Set-CsConferencingConfiguration** cmdlet 将新设置实际应用于 Redmond 站点：
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

如果不调用 **Set-CsConferencingConfiguration**，新的设置就不会生效。 相反，只要你结束 Windows PowerShell 会话或删除变量 $x，它们就会立即消失。
  

