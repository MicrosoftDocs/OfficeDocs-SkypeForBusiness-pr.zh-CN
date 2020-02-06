---
title: 为你的用户规划 Skype for Business 2015 客户端体验
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要：了解新的 Skype for Business 和你可以采取哪些步骤来准备你的环境和用户进行更新，无论你使用的是 Skype for Business Online、Skype for business Server 2019、Skype for business Server 2015、Lync Server 2013 还是Lync Server 2010。
ms.openlocfilehash: afd0f9f8a764ef9430d9ac1a9887a872c02fedd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803522"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>为你的用户规划 Skype for Business 2015 客户端体验
 
**摘要：** 了解新的 Skype for Business 和你可以采取哪些步骤来准备你的环境和用户进行更新，无论你使用的是 Skype for Business Online、Skype for business Server 2019、Skype for Business Server 2015、Lync Server 2013 还是 Lync Server 2010。
  
Lync 2013 的2015年4月14日的 Office 更新包括新的 Skype for Business 用户界面。 此更新使管理员能够控制客户端的外观，并选择是保留 Lync 2013 客户端体验还是使用改进的 Skype for business 客户端体验。 Skype for Business 客户端有效地替换了 Lync 2013 客户端，并添加了管理员在现有 Lync 客户体验和新的 Skype for Business 客户体验之间进行选择的能力。 有关此更新的信息，请参阅[Lync 2013 的2015更新（Skype for business）（KB2889923）](https://support.microsoft.com/en-us/kb/2889923/)。
  
2015年5月12日将有来自 Office 的其他每月更新，包括更新的 Skype for business 客户端。 许多未应用四月更新的客户将获取 Office 2013 的5月更新更新。 本主题中的信息将帮助您为组织、环境和用户做好客户端更新准备。 为了便于用户和支持团队轻松完成过渡，请使用本主题中的信息帮助您确定要为用户选择哪种客户端体验，然后在将客户端更新部署到组织之前，先改变环境。
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [为使用 Skype for Business 客户端准备环境](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>您要为用户选择哪种客户端体验？
<a name="clientexperience"> </a>

使用新的 Skype for Business 客户端，你可以控制用户获取哪些客户端体验（Lync 或 Skype for business）。 默认的客户端体验取决于你使用的是 Lync 还是本地或联机的 Skype for business。 如果您目前使用的是 Skype for Business Online （Lync Online）和 Office 365 专业增强版、Office 365 商业高级版或 Office 2013，更新的 Skype for business 客户体验（受 Skype 的外观的创意）将是默认的用户体验。 如果现在使用的是 Lync Server 本地版，则 Lync 客户端体验将是默认设置。
  
可以使用客户端策略来配置用户得到哪种客户端体验。 客户端策略是一组配置设置，当用户登录到 Lync 或 Skype for Business 时应用这些设置。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business 客户端体验

除了 Lync 的所有功能之外，Skype for business 还通过来自 Skype 的简化控件和熟悉的图标提供了新功能。 Skype for Business 中的一些新功能仅适用于全新的 Skype for business 客户端体验。 若要了解有关 Skype for Business 中的新功能的详细信息，请参阅[发现 skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)for business。
  
### <a name="lync-client-experience"></a>Lync 客户端体验

Lync 客户端体验与你的用户已熟悉的 Lync 2013 客户端体验非常相似，但你可能希望让你的用户了解一些更改。 若要查看 Lync 客户端体验与 Lync 2013 客户端之间的区别，请参阅为什么我在[使用 Lync 时看到 Skype for business？](https://go.microsoft.com/fwlink/p/?LinkId=544712)以及本主题后面的其他链接。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>为使用 Skype for Business 客户端准备环境
<a name="usinglync"> </a>

为了让环境做好客户端更新准备，有几项工作要做。 在开始进行任何配置以配置客户端体验之前，首先需要确保你使用的是支持客户端策略设置的 Skype for Business Server 或 Lync Server 版本。
  
一旦你确认你使用的是支持策略设置控制客户体验的 Skype for Business Server 或 Lync Server 版本，你将需要在你的环境中配置策略设置。 你需要遵循的具体步骤取决于你正在使用的 Skype for business 服务器或 Lync Server 的版本，以及你的用户是否在本地或联机。 
  
在客户端更新被发送到您的用户之前，您需要进行这些更改，以便您可以在用户第一次启动 Skype for Business 客户端时控制客户体验。 下表指出了为用户所需的客户端体验配置环境时需要执行的步骤。
  
|**Deployment**|**Skype for Business 客户端体验**|**Lync 客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |除了部署客户端内部版本 4711.1002（2015 年 4 月）或更高版本之外，没有其他步骤。  <br/> |[在 Skype for Business Online 中使用 Lync 客户端体验](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |除了部署客户端内部版本 4711.1002（2015 年 4 月）或更高版本之外，没有其他步骤。  <br/> |[在 Skype for Business Server（本地部署）中使用 Lync 客户端体验](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[在本地使用 Lync Server 2013 或 Lync Server 2010 的 Skype 客户端体验](user-experience.md#SkypewithLynconprem) <br/> |[在本地使用 lync Server 2013 或 Lync Server 2010 的 Lync 客户端体验](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在本地使用 Lync Server 2013 或 Lync Server 2010 的 Skype 客户端体验
<a name="SkypewithLynconprem"> </a>

如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。本地部署的默认体验
  
 **步骤1：** 首先，请确保你运行的是支持客户端策略设置的 Lync Server 版本。
  
- **Lync server 2013** -必须运行 Lync Server 2013 或更高版本更新的12月2014累积更新（5.0.8308.857）。 有关信息，请参阅[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync server 2010** -必须运行 Lync Server 2010 或更高版本更新的2月2015累积更新（4.0.7577.710）。 有关信息，请参阅[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **步骤2：** 接下来，使用客户端策略设置 Skype for business 客户端的 Skype 客户端体验。 使用客户端策略来设置客户端体验有 **3 个选项**。
  
  **选项 1：** 使用全局策略来设置 Skype 客户端体验。请注意，全局策略适用于部署环境中的所有用户，但是用户级和站点级策略优先于全局策略：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **选项 2：** 修改环境中使用的现有客户端策略，引入启用 Skype 客户端体验的设置。这能让您将 Skype 客户端体验只分配给已分配了现有策略的那些用户：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **选项 3：** 创建包含 Skype 客户端体验设置的新策略来分配给用户。首先，创建新的客户端策略，然后将策略的名称作为 **Identity** 参数的值提供：
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然后，将策略的名称（用于 **Identity** 参数的值）用作 **PolicyName** 参数的值，将策略分配给用户：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步骤3：** 配置客户端策略后，部署 Skype for Business 客户端、内部版本4711.1002 （四月、2015）或更高版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在本地使用 lync Server 2013 或 Lync Server 2010 的 Lync 客户端体验
<a name="LyncwithLynconprem"> </a>

这是在本地 Lync Server 部署中部署 Skype for Business 客户端时的默认体验。 您无需配置任何客户端策略来使用 Lync 客户端体验，但是您可能想控制客户端的首次运行行为。 默认情况下，用户第一次启动 Skype for Business 客户端时，将使用 Skype 客户体验，并向用户显示通知，请求用户重新启动客户端以获取 Lync 客户端体验。 可以修改客户端计算机上的系统注册表，将环境配置为，在用户首次启动客户端时，显示 Lync 客户端体验，并且关闭客户端教程。 有关在部署 Skype for Business 客户端之前需要执行的步骤，请参阅以下主题之一：
  
- **Lync server 2013**，请参阅[在 Lync Server 2013 中配置客户端体验 Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010**请参阅[在 Lync Server 2010 中配置客户端体验 Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>在 Skype for Business Server（本地部署）中使用 Lync 客户端体验
<a name="LyncwithSfBServer"> </a>

如果要在本地 Skype for business Server 部署中配置 Lync 客户端体验，请按照本部分中的步骤操作。
  
如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。本地部署的默认体验
  
 **步骤1：** 首先，部署 Skype for Business 服务器。
  
 **步骤2：** 接下来，使用客户端策略设置 Skype for Business 客户端的 Lync 客户端体验。 使用客户端策略来设置客户端体验有 **3 个选项**。
  
 **选项 1：** 使用全局策略来设置 Lync 客户端体验。请注意，全局策略适用于部署环境中的所有用户，但是用户级和站点级策略优先于全局策略：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **选项 2：** 修改环境中使用的现有客户端策略，引入启用 Lync 客户端体验的设置。这能让您将 Lync 客户端体验只分配给已分配了现有策略的那些用户：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **选项 3：** 创建包含 Lync 客户端体验设置的新策略来分配给用户。首先，创建新的客户端策略，然后将策略的名称作为 **Identity** 参数的值提供：
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然后，将策略的名称（用于 **Identity** 参数的值）用作 **PolicyName** 参数的值，将策略分配给用户：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步骤3：可选**-默认情况下，用户首次启动 Skype for business 客户端时，将使用 skype 客户体验，并向要求用户重新启动客户端以获取 Lync 客户端体验的用户显示通知。 可以修改客户端计算机上的系统注册表，将环境配置为，在用户首次启动客户端时，显示 Lync 客户端体验，并且关闭客户端教程。 有关部署 Skype for Business 客户端之前需要执行的步骤，请参阅[配置客户端体验 skype for](../../deploy/deploy-clients/configure-the-client-experience.md)business。
  
 **步骤4：** 配置客户端策略后，部署 Skype for Business 客户端、内部版本4711.1002 （四月、2015）或更高版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>在 Skype for Business Online 中使用 Lync 客户端体验
<a name="LyncwithSfBO"> </a>

如果要配置 Lync 客户体验和使用 Skype for Business Online，请按照本部分中的步骤操作。
  
如果您使用的是 Skype for Business Online，您仍然可以通过使用远程 PowerShell 配置客户端策略，将 Lync 客户端体验与组织中的 Skype for Business 客户端配合使用。 使用客户端策略来设置客户端体验有 **3 个选项**。 请注意，策略和参数名称与你在使用 Skype for Business 或 Lync Server 本地版时用于配置客户端体验的设置不同。
  
 **选项1：** 使用全局策略设置 Lync 客户端体验。 请注意，应用于用户的客户端和网站策略将优先于全局策略。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 2：** 修改环境中使用的现有客户端策略，引入启用 Lync 客户端体验的设置。这能让您将 Lync 客户端体验只分配给已分配了现有策略的那些用户：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项3：** 使用包含 Lync 客户端体验设置的自定义策略实例。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

配置客户端策略后，部署 Skype for Business 客户端、内部版本4711.1002 （四月、2015）或更高版本。
  
有关如何使用 Skype for Business Online 配置客户体验的详细信息，包括有关如何控制可用于配置你的环境的首次运行体验和 PowerShell 脚本的步骤，请参阅[在 Skype For business 和 Lync 客户端用户界面之间切换](https://aka.ms/SfBOUI)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>有助于为支持团队和最终用户做好更新准备的资源
<a name="support"> </a>

为了便于你和你的组织为过渡做好准备，我们还提供了许多其他资源，可帮助你规划、教育和接洽最终用户。
  
- [视频： Skype for business 简介](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business 快速入门指南（下载）](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 现在是 Skype for business-查看新增功能](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for business：新用户的分步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [为什么我在使用 Lync 时看到 Skype for business？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

