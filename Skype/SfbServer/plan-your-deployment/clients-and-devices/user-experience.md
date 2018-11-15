---
title: 规划业务 2015年为您的用户的客户端体验的 Skype
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要： 了解新的业务的 Skype 和可采取的步骤进行更新，准备您的环境和您的用户是否使用 Skype 业务 Online、 业务服务器 2019年的 Skype 业务服务器 2015，Lync Server 2013 的 Skype 或Lync Server 2010。
ms.openlocfilehash: 351582e7a7619541d5401acfb46854f61c9e052d
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531165"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>规划业务 2015年为您的用户的客户端体验的 Skype
 
**摘要：** 了解业务和可采取的步骤进行更新，准备您的环境和您的用户是否正在业务服务器 2015年、 Lync Server 2013 或 Lync Server 中使用业务 online Skype、 业务服务器 2019年的 Skype Skype 新 Skype2010。
  
年 4 月 14，2015年的 Lync 2013 的 Office 更新包含业务用户界面的新 Skype。 此更新使管理员可以控制客户端的外观，并选择是否保留 Lync 2013 客户端体验或改进的 Skype 用于业务客户端体验。 业务客户端 Skype 有效地替换 Lync 2013 客户端，并添加管理员可以选择现有的 Lync 客户端体验和业务客户端体验的新 Skype 之间的功能。 有关此更新的信息，请参阅 [Lync 2013 2015 年 4 月 14 日更新 (Skype for Business) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/)。
  
2015 年 5 月 12 日上将会从 Office 包含业务客户端的更新的 Skype 的另一个每月更新。 未应用更新将拿年 5 月 12 年 4 月的许多客户的 Office 2013 更新。 本主题中的信息将帮助您为组织、环境和用户做好客户端更新准备。 为了便于用户和支持团队轻松完成过渡，请使用本主题中的信息帮助您确定要为用户选择哪种客户端体验，然后在将客户端更新部署到组织之前，先改变环境。
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [为使用 Skype for Business 客户端准备环境](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 客户端体验不是业务 2016年客户端版本的 Skype 选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>您要为用户选择哪种客户端体验？
<a name="clientexperience"> </a>

使用业务客户端的新 Skype，您可以控制 Lync 或 Skype for Business 的客户端体验获取您的用户，请。 默认客户端体验取决于您使用 Lync 还是 Skype 业务本地或联机。 如果您使用 Skype 业务联机 (Lync Online) 立即与 Office 365 ProPlus、 Office 365 企业高级版或 Office 2013，业务客户端的更新的 Skype 体验 — 通过外观 Skype 灵感 — 将默认用户体验。 如果您要使用的部署 Lync Server，Lync 客户端体验将默认值。
  
可以使用客户端策略来配置用户得到哪种客户端体验。 客户端策略是一组时他们登录到 Lync 或 for Business 的 Skype 应用到用户的配置设置。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business 客户端体验

Lync 的所有功能，除了 for Business 的 Skype 提供 Skype 简化的控件与熟悉的图标的新功能。 Skype for Business 中的某些新功能可仅与商业客户端体验的新 Skype。 若要了解有关 Skype for Business 中的新功能的详细信息，请参阅[发现 for Business 的 Skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync 客户端体验

Lync 客户端体验非常类似于 Lync 2013 客户端体验的用户已熟悉，但有一些您需要让您了解的用户的更改。 若要查看 Lync 客户端体验和 Lync 2013 客户端之间的不同，请参阅[在我使用 Lync 为什么看 Skype for Business？](https://go.microsoft.com/fwlink/p/?LinkId=544712)和本主题后面的其他链接。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>为使用 Skype for Business 客户端准备环境
<a name="usinglync"> </a>

为了让环境做好客户端更新准备，有几项工作要做。 在开始进行配置的客户端体验的任何更改之前，首先需要确保您使用进行业务服务器或 Lync Server 支持的客户端策略设置的 Skype 的版本。
  
一旦您已确认正在使用业务服务器或 Lync Server 的支持策略设置控制客户端体验 Skype 的版本，您需要在您的环境中配置的策略设置。 您需要遵循的具体步骤依赖于业务服务器或使用的 Lync Server Skype 的版本和您的用户是否在本地或联机。 
  
您需要进行这些更改之前客户端更新传递到您的用户，以便您可以控制从首次启动业务客户端 Skype 的客户端体验。 下表将指向您需要配置您的环境的用户所需的客户端体验采取的步骤。
  
|**Deployment**|**Skype for Business 客户端体验**|**Lync 客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |除了部署客户端内部版本 4711.1002（2015 年 4 月）或更高版本之外，没有其他步骤。  <br/> |[在 Skype for Business Online 中使用 Lync 客户端体验](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |除了部署客户端内部版本 4711.1002（2015 年 4 月）或更高版本之外，没有其他步骤。  <br/> |[在 Skype for Business Server（本地部署）中使用 Lync 客户端体验](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[使用 Lync Server 2013 的 Skype 客户端体验或 Lync Server 2010 部署](user-experience.md#SkypewithLynconprem) <br/> |[使用 Lync Server 2013 或 Lync Server 2010 内部部署 Lync 客户端体验](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>使用 Lync Server 2013 的 Skype 客户端体验或 Lync Server 2010 部署
<a name="SkypewithLynconprem"> </a>

如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。本地部署的默认体验
  
 **步骤 1:** 首先，确保您正在运行某个版本的 Lync Server 支持的客户端策略设置。
  
- **Lync Server 2013** -您必须运行年 12 月 2014年累积更新 (5.0.8308.857) Lync Server 2013 或更高版本的更新。 有关详细信息，请参阅[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync Server 2010** -您必须运行年 2 月 2015年累积更新 (4.0.7577.710) Lync Server 2010 或更高版本的更新。 有关信息，请参阅[Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **步骤 2:** 接下来，使用客户端策略设置与业务客户端 Skype 的 Skype 客户端体验。 使用客户端策略来设置客户端体验有 **3 个选项**。
  
  **选项 1：** 使用全局策略来设置 Skype 客户端体验。请注意，全局策略适用于部署环境中的所有用户，但是用户级和站点级策略优先于全局策略：
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **选项 2：** 修改环境中使用的现有客户端策略，引入启用 Skype 客户端体验的设置。这能让您将 Skype 客户端体验只分配给已分配了现有策略的那些用户：
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **选项 3：** 创建包含 Skype 客户端体验设置的新策略来分配给用户。首先，创建新的客户端策略，然后将策略的名称作为 **Identity** 参数的值提供：
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然后，将策略的名称（用于 **Identity** 参数的值）用作 **PolicyName** 参数的值，将策略分配给用户：
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步骤 3:** 您已配置您的客户端策略后，部署业务客户端，生成 4711.1002 (年 4 月，2015) Skype 或更高版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>使用 Lync Server 2013 或 Lync Server 2010 内部部署 Lync 客户端体验
<a name="LyncwithLynconprem"> </a>

业务客户端 Skype 部署在内部部署 Lync Server 部署中时，这是默认体验。 您无需配置任何客户端策略来使用 Lync 客户端体验，但是您可能想控制客户端的首次运行行为。 默认情况下，用户首次启动业务客户端 Skype、 使用 Skype 客户端体验和请求他们重新启动客户端获取 Lync 客户端体验的用户显示一个通知。 可以修改客户端计算机上的系统注册表，将环境配置为，在用户首次启动客户端时，显示 Lync 客户端体验，并且关闭客户端教程。 有关的步骤，您需要执行部署业务客户端，请参阅以下主题之一 Skype 之前：
  
- **Lync Server 2013**，请参阅[的 Configure 与 Skype 的 Lync Server 2013 中的业务的客户端体验](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** ，请参阅[的配置客户端体验的 Lync Server 2010 中的业务的 Skype](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>在 Skype for Business Server（本地部署）中使用 Lync 客户端体验
<a name="LyncwithSfBServer"> </a>

如果您想要在内部部署 Skype 业务服务器部署中配置的 Lync 客户端体验，请按照本节中的步骤。
  
如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。本地部署的默认体验
  
 **步骤 1:** 首先，部署业务服务器 Skype。
  
 **步骤 2:** 接下来，使用客户端策略设置与业务客户端 Skype 的 Lync 客户端体验。 使用客户端策略来设置客户端体验有 **3 个选项**。
  
 **选项 1：** 使用全局策略来设置 Lync 客户端体验。请注意，全局策略适用于部署环境中的所有用户，但是用户级和站点级策略优先于全局策略：
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **选项 2：** 修改环境中使用的现有客户端策略，引入启用 Lync 客户端体验的设置。这能让您将 Lync 客户端体验只分配给已分配了现有策略的那些用户：
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **选项 3：** 创建包含 Lync 客户端体验设置的新策略来分配给用户。首先，创建新的客户端策略，然后将策略的名称作为 **Identity** 参数的值提供：
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然后，将策略的名称（用于 **Identity** 参数的值）用作 **PolicyName** 参数的值，将策略分配给用户：
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步骤 3： 可选**-默认情况下，用户首次启动业务客户端 Skype、 使用 Skype 客户端体验和用户请求他们重新启动客户端获取 Lync 客户端体验显示一个通知。 可以修改客户端计算机上的系统注册表，将环境配置为，在用户首次启动客户端时，显示 Lync 客户端体验，并且关闭客户端教程。 有关执行部署 Skype 业务客户端之前所需的步骤，请参阅[的配置客户端体验的 Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步骤 4:** 您已配置您的客户端策略后，部署业务客户端，生成 4711.1002 (年 4 月，2015) Skype 或更高版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>在 Skype for Business Online 中使用 Lync 客户端体验
<a name="LyncwithSfBO"> </a>

如果您想要配置的 Lync 客户端体验和您的业务联机使用 Skype，请按照本节中的步骤。
  
如果您使用 Skype 业务 Online，您可以仍使用 Lync 客户端体验 Skype for Business 客户端在组织中使用远程 PowerShell 配置客户端策略。 使用客户端策略来设置客户端体验有 **3 个选项**。 请注意的策略和参数的名称是您使用适用于商务或 Lync Server 使用 Skype 时配置的客户端体验的设置以外的其他内部部署。
  
 **选项 1:** 使用全局策略中设置 Lync 客户端体验。 请注意，应用于用户的客户端和站点策略将优先于全局策略。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 2：** 修改环境中使用的现有客户端策略，引入启用 Lync 客户端体验的设置。这能让您将 Lync 客户端体验只分配给已分配了现有策略的那些用户：
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 3:** 使用自定义策略的实例包含 Lync 客户端体验的设置。
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

您已配置您的客户端策略后，部署业务客户端，生成 4711.1002 (年 4 月，2015) Skype 或更高版本。
  
有关如何配置客户端的详细信息体验的 Skype 有关业务 Online，包括有关如何控制的首次运行的体验和可用于配置您的环境中的 PowerShell 脚本的步骤，请参阅[之间切换商业和 Lync 客户端用户界面的 Skype](https://aka.ms/SfBOUI)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>有助于为支持团队和最终用户做好更新准备的资源
<a name="support"> </a>

若要使您更轻松地和组织准备转换，我们具有许多可用于帮助您规划、 培训和使用最终用户的其他资源。
  
- [视频：Skype for Business 简介](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business 快速入门指南（下载）](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 现 for Business 的 Skype — 请参阅 what's new](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business： 适用于新的用户的分步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [使用 Lync 时，为什么我会看到 Skype for Business？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

