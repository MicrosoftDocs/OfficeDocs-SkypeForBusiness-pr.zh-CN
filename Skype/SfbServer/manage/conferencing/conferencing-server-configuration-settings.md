---
title: 在 Skype for Business Server 中管理会议服务器配置设置
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：了解如何在 Skype for Business Server 中管理会议服务器配置设置。
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828282"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中管理会议服务器配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中管理会议服务器配置设置。
  
本主题介绍如何管理会议配置设置。 若要详细了解如何计划和部署会议，请参阅 Plan for [conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
会议配置设置可确定诸如会议内容和讲义允许的最大大小等内容;应用程序共享会议服务的最大带宽量;存储限制和过期期限;支持的客户端的内部和外部下载的 URL;指向内部和外部 URL 的指针，用户可以获取会议帮助和资源;以及用于应用程序共享、客户端音频、文件传输和媒体流量的端口。 这些设置允许你管理实际服务器本身。 可以使用 Skype for Business Server 命令行管理程序设置这些设置。
  
安装 Skype for Business Server 时，系统会在全局集合集中 (一个会议) 。 如果您需要为站点或服务创建自定义设置，则可以使用 **New-CsConferencingConfiguration** cmdlet 来完成。 请注意，新设置只能在站点范围或服务范围应用;无法创建新的会议配置设置的全局集合，但可以使用 **Set-CsConferencingConfiguration** cmdlet 修改全局集合。 此外，任何站点和服务都不得承载多个设置集合。 如果尝试为 Redmond 站点创建新设置，并且 Redmond 站点已托管会议配置设置集合，则命令将失败。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序管理会议配置设置

若要使用 Skype for Business Server 命令行管理程序管理会议配置设置，请使用以下 cmdlet：
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置集合。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
以下命令为 Redmond 站点服务器 site：Redmond (创建一个新的会议) 。 在此示例中，组织 (一) 参数，用于将 Organization 属性的值设置为 Litwareinc： 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

请注意，每个站点只能有一个此类集合，因此，如果 Redmond 站点已有会议配置设置集合，则此命令将失败。 
  
下一个示例定义一个新的会议配置设置集合，这些设置最初存储在内存中，稍后再应用到 Redmond 站点。 
  
第一个命令使用 **New-CsConferencingConfiguration** cmdlet 创建存储在变量 $x 中新的内存中设置集合。 InMemory 参数指定应在内存中创建集合，而不是立即应用于 Redmond 站点。
  
创建集合后，第二个命令将 Organization 属性的值设置为 Litwareinc。 
  
最后，第三个命令使用 **Set-CsConferencingConfiguration** cmdlet 将新设置实际应用到 Redmond 站点：
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

如果不调用 **Set-CsConferencingConfiguration** cmdlet，则新设置永远不会生效。 相反，一旦结束会话或删除Windows PowerShell变量，它们就会$x。
  

