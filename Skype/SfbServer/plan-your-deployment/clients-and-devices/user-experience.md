---
title: 为用户Skype for Business 2015 客户端体验
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要：了解新的 Skype for Business 以及为更新准备环境和用户而可以执行的步骤，无论你使用的是 Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、LyncServer 2013 或 Lync Server 2010。
ms.openlocfilehash: 9979b7d9fe449de926358097b9fd2fdd36e5afb4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864739"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>为用户Skype for Business 2015 客户端体验
 
**摘要：** 了解新 Skype for Business以及为更新准备环境和用户而可以执行的步骤（无论你使用的是 Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server）2013 或 Lync Server 2010。
  
2015 年 4 月 14 Office Lync 2013 更新包括新的 Skype for Business 用户界面。 此更新使管理员能够控制客户端的外观并选择是保留 Lync 2013 客户端体验还是使用改进的 Skype for Business 客户端体验。 Skype for Business客户端实际上取代了 Lync 2013 客户端，并增加了管理员对现有 Lync 客户端体验和新的 Lync 客户端体验Skype for Business选择的能力。 有关此更新的信息，请参阅[Lync 2013 (Skype for Business)  (KB2889923) 2015 年 4 月 14 日更新](https://support.microsoft.com/kb/2889923/)。
  
2015 年 5 月 12 日，Office更新，其中包括更新后的 Skype for Business 客户端。 许多未应用 4 月更新的客户将选取 2013 年 5 月 12 Office更新。 本主题中的信息将帮助您为组织、环境和用户准备客户端更新。 若要为用户和支持团队轻松过渡，请使用本主题中的信息帮助您确定用户需要哪种客户端体验，然后在组织中部署客户端更新之前对环境进行更改。
  
- [需要为用户提供哪些客户端体验？](user-experience.md#clientexperience)
    
- [为客户端准备Skype for Business环境](user-experience.md#usinglync)
    
- [帮助你为支持团队和最终用户做好更新准备的资源](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 客户端体验不是适用于 Skype for Business 2016 客户端版本的选项。 在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保它不会以数字 16 开始;例如：16.x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>需要为用户提供哪些客户端体验？
<a name="clientexperience"> </a>

使用新的 Skype for Business 客户端，您可以控制用户获取的客户端体验（Lync 或 Skype for Business）。 默认客户端体验取决于是在本地还是联机Skype for Business Lync 或客户端。 如果您现在将 Skype for Business Online (Lync Online) 与 Microsoft 365 企业应用版、Microsoft 365 商业标准版 或 Office 2013 一同使用，则更新后的 Skype for Business 客户端体验受外观启发Skype -将成为默认用户体验。 如果当前使用的是本地 Lync Server，则 Lync 客户端体验将为默认体验。
  
可以使用客户端策略配置用户获取的客户端体验。 客户端策略是一组配置设置，当用户登录到 Lync 或 Skype for Business。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business客户端体验

除了 Lync 的所有功能之外，Skype for Business还通过来自 Lync 的简化控件和熟悉的图标Skype。 Skype for Business中的一些新功能仅适用于新的 Skype for Business 客户端体验。 若要了解有关最新功能Skype for Business，请参阅[发现](https://go.microsoft.com/fwlink/p/?LinkId=528686)Skype for Business。
  
### <a name="lync-client-experience"></a>Lync 客户端体验

Lync 客户端体验与用户已熟悉的 Lync 2013 客户端体验非常相似，但是有一些更改需要让用户了解。 若要了解 Lync 客户端体验与 Lync 2013 客户端之间有什么不同，请参阅为什么在使用 Lync 时会看到[Skype for Business？](https://go.microsoft.com/fwlink/p/?LinkId=544712)以及本主题稍后介绍的其他链接。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>为客户端准备Skype for Business环境
<a name="usinglync"> </a>

需要执行一些操作才能使环境为客户端更新做好准备。 在开始对配置客户端体验进行任何更改之前，首先需要确保使用的是支持客户端策略设置的 Skype for Business Server 或 Lync Server 版本。
  
确认您使用的是支持策略设置的 Skype for Business Server 或 Lync Server 版本来控制客户端体验后，您需要在您的环境中配置策略设置。 您需要执行的特定步骤取决于您使用的 Skype for Business Server 或 Lync Server 的版本，以及您的用户是本地用户还是联机用户。 
  
在将客户端更新传递到用户之前，您需要进行这些更改，以便可以从用户首次启动客户端客户端时控制Skype for Business体验。 下表列出了为用户配置所需客户端体验的环境所需执行的步骤。
  
|**部署**|**Skype for Business客户端体验**|**Lync 客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |除了在 2015 年 4 月或 (部署客户端内部版本 4711.1002) 任何其他步骤。  <br/> |[将 Lync 客户端体验与 Skype for Business Online 一同使用](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |除了在 2015 年 4 月或 (部署客户端内部版本 4711.1002) 任何其他步骤。  <br/> |[在本地部署中Skype for Business Server Lync 客户端体验](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[使用Skype Lync Server 2013 或 Lync Server 2010 内部部署体验](user-experience.md#SkypewithLynconprem) <br/> |[将 Lync 客户端体验与本地 Lync Server 2013 或 Lync Server 2010 一同使用](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>使用Skype Lync Server 2013 或 Lync Server 2010 内部部署体验
<a name="SkypewithLynconprem"> </a>

如果要在本地部署中配置 Skype客户端体验，请按照本节中的步骤操作。 本地的默认体验
  
 **步骤 1：** 首先，请确保运行的 Lync Server 版本支持客户端策略设置。
  
- **Lync Server 2013** - 必须运行 Lync Server 2013 的 2014 年 12 月累积更新 (5.0.8308.857) 或更高版本。 有关信息，请参阅[Updates for Lync Server 2013。](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
- **Lync Server 2010** - 必须运行 Lync Server 2010 的 2015 年 2 月累积更新 (4.0.7577.710) 或更高版本。 有关信息，请参阅[Updates for Lync Server 2010。](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
  **步骤 2：** 接下来，使用客户端策略设置Skype客户端的客户端Skype for Business体验。 使用客户端策略设置客户端体验有 **3** 个选项。
  
  **选项 1：** 使用全局Skype设置客户端体验。 请注意，全局策略适用于部署中的所有用户，但用户和站点级别策略优先于全局策略：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **选项 2：** 修改环境中使用的现有客户端策略，以包括用于启用客户端Skype设置。 这样，你Skype现有策略的用户分配客户端体验：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **选项 3：** 创建一个新策略，以分配给包括客户端体验Skype设置的用户。 首先，创建新的客户端策略，并提供策略名称作为 **Identity** 参数的值：
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然后，使用策略名称将策略名称分配给 (**Identity** 参数使用的值) **PolicyName** 参数的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步骤 3：** 配置客户端策略后，部署 Skype for Business 客户端，内部版本 4711.1002 (2015 年 4 月) 更高版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>将 Lync 客户端体验与本地 Lync Server 2013 或 Lync Server 2010 一同使用
<a name="LyncwithLynconprem"> </a>

这是在本地 Lync Server Skype for Business部署客户端时的默认体验。 不需要将任何客户端策略配置为使用 Lync 客户端体验，但可能需要控制客户端的首次运行行为。 默认情况下，用户第一次启动 Skype for Business 客户端时，会使用 Skype 客户端体验，并且会向用户显示一条通知，请求他们重新启动客户端以获得 Lync 客户端体验。 您可以配置环境，以便用户首次启动客户端时显示 Lync 客户端体验，以及通过修改客户端计算机上的系统注册表来关闭客户端教程。 有关在部署 Skype for Business 客户端之前需要执行的步骤，请参阅下列主题之一：
  
- **Lync Server 2013，** 请参阅 [Configure the client experience with Skype for Business in Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010** 请参阅 [Configure the client experience with Skype for Business in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>在本地部署中Skype for Business Server Lync 客户端体验
<a name="LyncwithSfBServer"> </a>

如果要在本地部署部署中配置 Lync 客户端体验，请按照Skype for Business Server步骤。
  
如果要在本地部署中配置 Skype客户端体验，请按照本节中的步骤操作。 本地的默认体验
  
 **步骤 1：** 首先，部署Skype for Business Server。
  
 **步骤 2：** 接下来，使用客户端策略设置 Lync 客户端与 Skype for Business 体验。 使用客户端策略设置客户端体验有 **3** 个选项。
  
 **选项 1：** 使用全局策略设置 Lync 客户端体验。 请注意，全局策略适用于部署中的所有用户，但用户和站点级别策略优先于全局策略：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **选项 2：** 修改环境中使用的现有客户端策略，以包括启用 Lync 客户端体验的设置。 这样，您仅可以将 Lync 客户端体验分配给分配了现有策略的用户：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **选项 3：** 创建一个新策略，以分配给包含 Lync 客户端体验设置的用户。 首先，创建新的客户端策略，并提供策略名称作为 **Identity** 参数的值：
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然后，使用策略名称将策略名称分配给 (**Identity** 参数使用的值) **PolicyName** 参数的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步骤 3：** 可选 - 默认情况下，用户第一次启动 Skype for Business 客户端时，会使用 Skype 客户端体验，并且会向用户显示通知，要求他们重新启动客户端以获得 Lync 客户端体验。 您可以配置环境，以便用户首次启动客户端时显示 Lync 客户端体验，以及通过修改客户端计算机上的系统注册表来关闭客户端教程。 有关在部署客户端之前需要执行的步骤Skype for Business请参阅 Configure [the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步骤 4：** 配置客户端策略后，部署 Skype for Business 客户端，内部版本 4711.1002 (2015 年 4 月) 更高版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>将 Lync 客户端体验与 Skype for Business Online 一同使用
<a name="LyncwithSfBO"> </a>

如果要配置 Lync 客户端体验并且使用 Skype for Business Online，请按照本节中的步骤操作。
  
如果您使用的是 Skype for Business Online，您仍可以使用 Lync 客户端体验和 Skype for Business 客户端，方法为使用远程 PowerShell 配置客户端策略。 使用客户端策略设置客户端体验有 **3** 个选项。 请注意，策略和参数名称不同于在内部部署或 Lync Server Skype for Business配置客户端体验的设置。
  
 **选项 1：** 使用全局策略设置 Lync 客户端体验。 请注意，应用于用户的客户端和站点策略将优先于全局策略。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 2：** 修改环境中使用的现有客户端策略，以包括启用 Lync 客户端体验的设置。 这样，您仅可以将 Lync 客户端体验分配给分配了现有策略的用户：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 3：** 使用包含 Lync 客户端体验设置的自定义策略实例。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

配置客户端策略后，部署 Skype for Business 客户端，生成号 4711.1002 (2015 年 4 月) 或更高版本。
  
若要详细了解如何使用 Skype for Business Online 配置客户端体验，包括如何控制首次运行体验的步骤以及可用于配置环境的 PowerShell 脚本，请参阅在 Skype for Business 和[Lync](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)客户端用户界面之间切换。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>帮助你为支持团队和最终用户做好更新准备的资源
<a name="support"> </a>

为了便于你和组织为过渡做准备，我们提供了许多其他资源来帮助你规划、培训最终用户并吸引最终用户。
  
- [视频：Skype for Business 简介](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business快速入门指南 (下载) ](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 现已Skype for Business，请参阅新增功能](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business：新用户的分步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [为什么在使用 Lync Skype for Business时看到此限制？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
