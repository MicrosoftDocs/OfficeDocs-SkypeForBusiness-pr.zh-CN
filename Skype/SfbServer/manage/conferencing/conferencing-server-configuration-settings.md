---
title: 在 Skype for Business Server 2015 中管理会议服务器配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要： 了解如何管理会议服务器配置设置在 Skype 业务服务器 2015年。
ms.openlocfilehash: 88c127acdd569945eddb41e997034e5ea23ea2a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理会议服务器配置设置
 
**摘要：**了解如何管理会议服务器配置设置在 Skype 业务服务器 2015年。
  
本主题描述如何管理会议配置设置。 有关如何规划和部署会议的详细信息，请参见[会议在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/conferencing/conferencing.md)和[业务服务器 2015年的 Skype 在部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
会议配置设置确定诸如最大允许大小会议内容和讲义。最大带宽的应用程序共享会议服务;存储限制和有效期;为内部和外部 Url 下载受支持的客户端;用户可以从何处获取会议帮助和资源; 内部和外部 Url 指向的指针和用于共享应用程序、 客户端音频、 文件传输和媒体通信的端口。 这些设置可让你管理实际服务器本身。 这些设置可以设置通过 Skype 业务服务器管理程序。
  
为业务服务器安装 Skype 时，系统为您提供会议的单个集合配置设置 （全局集合）。 如果需要为站点或服务创建自定义设置，可以使用 **New-CsConferencingConfiguration** cmdlet 来完成。 请注意，只能在站点范围或服务范围应用新设置；你无法创建新的会议配置设置全局集合，但是可以使用 **Set-CsConferencingConfiguration** 来修改全局集合。 此外，站点和服务都不能托管多个设置集合。 如果你尝试为 Redmond 站点创建新设置，而 Redmond 站点已托管一个会议配置设置集合，则命令将会失败。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>通过 Skype 业务服务器管理外壳程序管理会议配置设置

若要通过 Skype 业务服务器管理外壳程序管理会议配置设置，请使用以下 cmdlet:
  
**会议配置设置**

|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |返回有关组织的会议配置设置的信息。  <br/> |
|[新 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |创建新的会议配置设置集合。  <br/> |
|[删除 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |删除指定的会议配置设置集合。  <br/> |
|[一组 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改现有的会议配置设置集合。  <br/> |
   
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
  

