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
description: 摘要：了解新的 Skype for Business 以及为更新准备您的环境和用户所需执行的步骤，无论您使用的是 Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013 还是Lync Server 2010。
ms.openlocfilehash: c54465b2f2c6cb7fb8d131b52de27c3f64d0bcc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028003"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>为你的用户规划 Skype for Business 2015 客户端体验
 
**摘要：** 了解新的 Skype for Business 以及为更新准备您的环境和用户所需执行的步骤，无论您使用的是 Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013 还是 Lync Server 2010。
  
2015年4月14日的 Lync 2013 Office 更新包括新的 Skype for Business 用户界面。 此更新使管理员能够控制客户端的外观，并选择是保留 Lync 2013 客户端体验还是使用改进的 Skype for Business 客户端体验。 Skype for Business 客户端有效地取代了 Lync 2013 客户端，并添加了管理员在现有 Lync 客户端体验与新的 Skype for Business 客户端体验之间进行选择的能力。 有关此更新的信息，请参阅[Lync 2013 的2015更新（Skype For business）（KB2889923）](https://support.microsoft.com/kb/2889923/)。
  
在5月12日，将有来自 Office 的其他每月更新2015，其中包括更新的 Skype for Business 客户端。 许多未应用四月份更新的客户将为 Office 2013 选择5月12日更新。 本主题中的信息将帮助您为您的组织、您的环境和用户准备客户端更新。 若要使您的用户和支持团队易于过渡，请使用本主题中的信息来帮助您决定您的用户所需的客户端体验，然后在组织中部署客户端更新之前对您的环境进行更改。
  
- [你希望为你的用户提供什么客户端体验？](user-experience.md#clientexperience)
    
- [为 Skype for business 客户端准备环境](user-experience.md#usinglync)
    
- [帮助你准备支持团队和最终用户进行更新的资源](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。 在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保其不以数字16开头;例如： x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>你希望为你的用户提供什么客户端体验？
<a name="clientexperience"> </a>

使用新的 Skype for Business 客户端，您可以控制用户获取的客户端体验，即 Lync 或 Skype for Business。 默认的客户端体验取决于您是在本地使用 Lync 还是 Skype for business，还是在线。 如果你目前使用的是 Skype for Business Online （Lync Online），则使用 Office 365 专业增强版、Office 365 商业高级版或 Office 2013，更新的 Skype for business 客户端体验（受 Skype 的外观的欢迎）将成为默认的用户体验。 如果现在使用的是本地 Lync Server，Lync 客户端体验将为默认设置。
  
您可以使用客户端策略来配置您的用户获得的客户端体验。 客户端策略是一组配置设置，当用户登录到 Lync 或 Skype for Business 时，这些设置将应用于这些设置。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business 客户端体验

除了 Lync 的所有功能外，Skype for Business 还通过 Skype 中的简化控件和常见图标提供了新功能。 Skype for Business 中的一些新功能仅适用于新的 Skype for Business 客户端体验。 若要了解有关 Skype for Business 中的新功能的详细信息，请参阅[发现 skype For business](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync 客户端体验

Lync 客户端体验与你的用户已经熟悉的 Lync 2013 客户端体验非常相似，但你需要让你的用户知道一些更改。 若要查看 Lync 客户端体验与 Lync 2013 客户端之间的不同之处，请参阅为什么我在[使用 Lync 时看到 Skype For business？](https://go.microsoft.com/fwlink/p/?LinkId=544712)和本主题后面的其他链接。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>为 Skype for business 客户端准备环境
<a name="usinglync"> </a>

为客户端更新准备好环境需要执行一些操作。 在开始进行任何更改以配置客户端体验之前，首先需要确保使用的是支持客户端策略设置的 Skype for Business Server 或 Lync Server 版本。
  
在您确认使用的是支持策略设置以控制客户端体验的 Skype for Business Server 或 Lync Server 版本之后，您需要在您的环境中配置策略设置。 您需要遵循的具体步骤取决于您正在使用的 Skype for Business Server 或 Lync Server 版本，以及您的用户是本地用户还是联机用户。 
  
您需要在将客户端更新传递给您的用户之前进行这些更改，以便您可以在首次启动 Skype for Business 客户端时控制客户端体验。 下表指出了为用户所需的客户端体验配置环境时需要执行的步骤。
  
|**部署**|**Skype for Business 客户端体验**|**Lync 客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |除了部署客户端版本4711.1002 （四月份、2015）或更高版本外，没有其他步骤。  <br/> |[将 Lync 客户端体验与 Skype for Business Online 结合使用](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |除了部署客户端版本4711.1002 （四月份、2015）或更高版本外，没有其他步骤。  <br/> |[在本地 Skype for business Server 中使用 Lync 客户端体验](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[在本地使用 Lync Server 2013 或 Lync Server 2010 的 Skype 客户端体验](user-experience.md#SkypewithLynconprem) <br/> |[在本地使用 lync Server 2013 或 Lync Server 2010 的 Lync 客户端体验](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在本地使用 Lync Server 2013 或 Lync Server 2010 的 Skype 客户端体验
<a name="SkypewithLynconprem"> </a>

如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。 本地的默认体验
  
 **步骤1：** 首先，请确保您运行的是支持客户端策略设置的 Lync Server 版本。
  
- **Lync server 2013** -必须运行 Lync server 2013 的12月2014累积更新（5.0.8308.857）或更高版本的更新。 有关信息，请参阅[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync server 2010** -您必须运行 Lync server 2010 或更高版本更新的二月2015累积更新（4.0.7577.710）。 有关信息，请参阅[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **步骤2：** 接下来，使用客户端策略设置 skype for business 客户端的 Skype 客户端体验。 使用客户端策略设置客户端体验有**3 个选项**。
  
  **选项1：** 使用全局策略设置 Skype 客户端体验。 请注意，全局策略适用于部署中的所有用户，但用户和网站级别策略的优先级高于全局策略：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **选项2：** 修改在您的环境中使用的现有客户端策略，以包含启用 Skype 客户端体验的设置。 这使您可以仅向已分配现有策略的用户分配 Skype 客户端体验：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **选项3：** 创建新策略以分配给包含 Skype 客户端体验设置的用户。 首先，创建新的客户端策略并将策略的名称提供为**Identity**参数的值：
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然后，将策略的名称（用作**Identity**参数的值）用作**PolicyName**参数的值，将策略分配给用户：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步骤3：** 配置客户端策略后，部署 Skype for Business 客户端、内部版本4711.1002 （4月、2015）或更高版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在本地使用 lync Server 2013 或 Lync Server 2010 的 Lync 客户端体验
<a name="LyncwithLynconprem"> </a>

当在本地 Lync Server 部署中部署 Skype for Business 客户端时，这是默认体验。 您无需将任何客户端策略配置为使用 Lync 客户端体验，但您可能需要控制客户端的首次运行行为。 默认情况下，用户首次启动 Skype for Business 客户端时，将使用 Skype 客户端体验，并向请求用户重新启动客户端以获取 Lync 客户端体验的用户显示一个通知。 您可以配置您的环境，以便在用户首次启动客户端时显示 Lync 客户端体验，也可以通过修改客户端计算机上的系统注册表来关闭客户端教程。 有关部署 Skype for Business 客户端之前需要执行的步骤，请参阅以下主题之一：
  
- **Lync server 2013**，请参阅[在 Lync Server 2013 中配置使用 Skype for business 的客户端体验](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010**请参阅[在 Lync Server 2010 中配置使用 Skype for business 的客户端体验](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>在本地 Skype for business Server 中使用 Lync 客户端体验
<a name="LyncwithSfBServer"> </a>

如果要在本地 Skype for Business Server 部署中配置 Lync 客户端体验，请遵循本节中的步骤。
  
如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。 本地的默认体验
  
 **步骤1：** 首先，部署 Skype for Business Server。
  
 **步骤2：** 接下来，使用客户端策略设置 Skype for Business 客户端的 Lync 客户端体验。 使用客户端策略设置客户端体验有**3 个选项**。
  
 **选项1：** 使用全局策略设置 Lync 客户端体验。 请注意，全局策略适用于部署中的所有用户，但用户和网站级别策略的优先级高于全局策略：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **选项2：** 修改您的环境中使用的现有客户端策略，以包含启用 Lync 客户端体验的设置。 这样，您只需将 Lync 客户端体验分配给已分配现有策略的用户：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **选项3：** 创建新策略以分配给用户，其中包括 Lync 客户端体验的设置。 首先，创建新的客户端策略并将策略的名称提供为**Identity**参数的值：
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然后，将策略的名称（用作**Identity**参数的值）用作**PolicyName**参数的值，将策略分配给用户：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步骤3：** 默认为可选-默认情况下，用户首次启动 Skype for business 客户端时，将使用 Skype 客户端体验，并向用户发出通知，询问他们是否重新启动客户端以获取 Lync 客户端体验。 您可以配置您的环境，以便在用户首次启动客户端时显示 Lync 客户端体验，也可以通过修改客户端计算机上的系统注册表来关闭客户端教程。 有关在部署 Skype for Business 客户端之前需要执行的步骤，请参阅[Configure the client experience With skype For business](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步骤4：** 配置客户端策略后，部署 Skype for Business 客户端、内部版本4711.1002 （4月、2015）或更高版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>将 Lync 客户端体验与 Skype for Business Online 结合使用
<a name="LyncwithSfBO"> </a>

如果要配置 Lync 客户端体验并使用 Skype for Business Online，请遵循本节中的步骤。
  
如果使用的是 Skype for Business Online，您仍可以使用远程 PowerShell 配置客户端策略，以便在组织中的 Skype for Business 客户端中使用 Lync 客户端体验。 使用客户端策略设置客户端体验有**3 个选项**。 请注意，策略和参数名称不同于您在使用 Skype for Business 或本地 Lync Server 时用于配置客户端体验的设置。
  
 **选项1：** 使用全局策略设置 Lync 客户端体验。 请注意，应用于用户的客户端和网站策略将优先于全局策略。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项2：** 修改您的环境中使用的现有客户端策略，以包含启用 Lync 客户端体验的设置。 这样，您只需将 Lync 客户端体验分配给已分配现有策略的用户：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项3：** 使用包含 Lync 客户端体验设置的自定义策略实例。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

配置客户端策略后，部署 Skype for Business 客户端、内部版本4711.1002 （4月、2015）或更高版本。
  
有关如何配置使用 Skype for Business Online 的客户端体验的详细信息，包括有关如何控制可用于配置环境的首次运行体验和 PowerShell 脚本的步骤，请参阅[在 Skype For business 和 Lync 客户端用户界面之间切换](https://aka.ms/SfBOUI)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>帮助你准备支持团队和最终用户进行更新的资源
<a name="support"> </a>

为了便于你和你的组织为过渡做好准备，我们还提供了许多其他资源，可帮助你规划、教育和接洽最终用户。
  
- [视频：Skype for Business 简介](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business 快速入门指南（下载）](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 现在是 Skype for Business，请参阅新增功能](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business：新用户的分步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [使用 Lync 时，为什么我会看到 Skype for Business？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

