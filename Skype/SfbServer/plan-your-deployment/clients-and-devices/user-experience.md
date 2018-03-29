---
title: 为用户规划 Skype for Business 客户端体验
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要： 了解业务和可以采取的步骤来准备您的环境和您的用户进行更新，无论你在线业务、 Skype 使用 Skype 业务服务器 2015年、 Lync Server 2013，或 Lync Server 2010 中的新的 Skype。
ms.openlocfilehash: 6ab79741a7a536e80beda0bc529351741136ea13
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-the-skype-for-business-client-experience-for-your-users"></a>为用户规划 Skype for Business 客户端体验
 
**摘要：**了解新的 Skype 业务和可以采取的步骤来准备您的环境和您的用户进行更新，无论你在线业务、 Skype 使用 Skype 业务服务器 2015年、 Lync Server 2013，或 Lync Server 2010。
  
4 月 14，2015 Lync 2013 的 Office 更新包括新的 Skype 业务用户界面。 此更新使管理员能够控制客户机的外观和感觉，并选择是否保留 Lync 2013 客户端体验或使用改进的 Skype 业务客户端体验。 业务客户端的 Skype 有效地替换 Lync 2013 客户端，并添加管理员现有 Lync 客户端体验和业务客户端体验新的 Skype 之间进行选择的能力。 有关此更新的信息，请参阅[于 2015 年 4 月 14 日更新的 Lync 2013 (Skype 业务) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/)。
  
上于 2015 年 5 月 12 日将会有另一个月更新，包括业务客户机更新的 Skype 的办公室。 未应用更新将拿起 5 月 12 月的很多客户更新 Office 2013。 本主题中的信息将帮助您为组织、环境和用户做好客户端更新准备。 为了便于用户和支持团队轻松完成过渡，请使用本主题中的信息帮助您确定要为用户选择哪种客户端体验，然后在将客户端更新部署到组织之前，先改变环境。
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [业务客户端的 Skype 为准备您的环境](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 客户端体验不是 Skype 业务 2016年的客户端版本的选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>您要为用户选择哪种客户端体验？
<a name="clientexperience"> </a>

与业务客户端新 Skype，您可以控制 Lync 或 Skype 业务的客户端体验您的用户获取，请。 默认客户端体验取决于您是否使用 Lync 或 Skype 的业务场所或联机。 如果您使用 Skype 业务联机 (Lync Online) 今天与 Office 365 ProPlus、 Office 365 的业务津贴或 Office 2013，业务客户机更新的 Skype 遇到 — 通过 Skype 的外观和感觉又提出了 — — 将默认用户体验。 如果您目前使用 Lync Server 部署，Lync 客户端体验将为默认值。
  
可以使用客户端策略来配置用户得到哪种客户端体验。 客户端策略是一组登录 Lync 或 Skype 业务时应用于用户的配置设置。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business 客户端体验

Lync 的所有功能，除了 Skype 业务从 Skype 提供新功能和简化的控件和熟悉的图标。 Skype 业务中的一些新功能可只与业务客户端体验新的 Skype。 若要了解有关 Skype 业务中的新功能的详细信息，请参阅[为业务发现 Skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync 客户端体验

Lync 客户端体验是非常相似的 Lync 2013 客户端体验用户已熟悉，但是有几个您需要让用户知道有关的改动。 Lync 客户端体验和 Lync 2013 客户端之间的不同，请参阅[时我使用 Lync 为什么看到 Skype 业务？](https://go.microsoft.com/fwlink/p/?LinkId=544712)和本主题后面部分中的其他链接。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>为使用 Skype for Business 客户端准备环境
<a name="usinglync"> </a>

为了让环境做好客户端更新准备，有几项工作要做。 在开始进行配置的客户端体验的任何更改之前，您首先需要确保业务服务器或 Lync 服务器支持的客户端策略设置为使用 Skype 的版本。
  
一旦确认业务服务器或支持的策略设置来控制客户端体验的 Lync Server 使用 Skype 的版本后，您需要在您的环境中配置的策略设置。 需要执行的特定步骤取决于 Skype 的版本对于业务服务器或正在使用 Lync Server 和您的用户是否是内部或联机。 
  
要将客户机更新传递给您的用户，从而使您可以控制从第一次开始 Skype 业务客户端的客户端体验之前进行这些更改。 下表列出了您需要配置您的用户所需的客户端体验的环境采取的步骤的。
  
|**部署**|**Skype 的业务客户端体验**|**Lync 客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |除了部署客户端内部版本 4711.1002（2015 年 4 月）或更高版本之外，没有其他步骤。  <br/> |[使用 Lync 客户端的体验与 Skype 的在线业务](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |除了部署客户端内部版本 4711.1002（2015 年 4 月）或更高版本之外，没有其他步骤。  <br/> |[对于业务服务器部署 Skype 使用 Lync 客户端体验](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[使用 Lync Server 2013 或 Lync Server 2010 上部署 Skype 客户端体验](user-experience.md#SkypewithLynconprem) <br/> |[使用 Lync Server 2013 或 Lync Server 2010 内部 Lync 客户端体验](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>使用 Lync Server 2013 或 Lync Server 2010 上部署 Skype 客户端体验
<a name="SkypewithLynconprem"> </a>

如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。本地部署的默认体验
  
 **第 1 步：**首先，请确保您运行的版本的 Lync 服务器支持的客户端策略设置。
  
- **Lync Server 2013** -您必须运行 12 月 2014年累积更新 Lync Server 2013 或更高版本的更新 (5.0.8308.857)。 有关信息，请参阅[更新 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync Server 2010** -您必须运行 2 月 2015年累积更新 Lync Server 2010 或更高版本的更新 (4.0.7577.710)。 有关信息，请参阅[Lync Server 2010 中的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
 **第 2 步：**接下来，使用客户端策略设置与业务客户端的 Skype 的 Skype 客户端体验。 使用客户端策略来设置客户端体验有 **3 个选项**。
  
 **选项 1：**使用全局策略来设置 Skype 客户端体验。请注意，全局策略适用于部署环境中的所有用户，但是用户级和站点级策略优先于全局策略：
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **选项 2：**修改环境中使用的现有客户端策略，引入启用 Skype 客户端体验的设置。这能让您将 Skype 客户端体验只分配给已分配了现有策略的那些用户：
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **选项 3：**创建包含 Skype 客户端体验设置的新策略来分配给用户。首先，创建新的客户端策略，然后将策略的名称作为 **Identity** 参数的值提供：
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然后，将策略的名称（用于 **Identity** 参数的值）用作 **PolicyName** 参数的值，将策略分配给用户：
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **第 3 步：**您已配置客户端策略后，将部署 Skype 业务客户机，生成 4711.1002 (四月，2015) 或更高版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>使用 Lync Server 2013 或 Lync Server 2010 内部 Lync 客户端体验
<a name="LyncwithLynconprem"> </a>

这是默认体验当 Skype 业务客户端部署在内部 Lync Server 部署。 您无需配置任何客户端策略来使用 Lync 客户端体验，但是您可能想控制客户端的首次运行行为。 默认情况下，用户首次启动业务客户端的 Skype、 使用 Skype 客户端体验和对请求他们重新启动客户机获取 Lync 客户端体验的用户显示一个通知。 可以修改客户端计算机上的系统注册表，将环境配置为，在用户首次启动客户端时，显示 Lync 客户端体验，并且关闭客户端教程。 有关的步骤，您需要执行之前部署 Skype 业务客户端，请参阅以下主题之一：
  
- **Lync Server 2013**，请参阅[的配置 Lync Server 2013 业务的 Skype 客户端体验](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010**请参阅[的配置 Lync Server 2010 中的业务的 Skype 客户端体验](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>在 Skype for Business Server（本地部署）中使用 Lync 客户端体验
<a name="LyncwithSfBServer"> </a>

如果您想要在内部部署 Skype 业务服务器 2015年部署中配置 Lync 客户端体验，请按照本节中的步骤操作。
  
如果要在本地部署中配置 Skype 客户端体验，请遵循本节中的步骤。本地部署的默认体验
  
 **第 1 步：**首先，对于业务服务器 2015年部署 Skype。
  
 **第 2 步：**接下来，使用客户端策略设置与业务客户端的 Skype 的 Lync 客户端体验。 使用客户端策略来设置客户端体验有 **3 个选项**。
  
 **选项 1：**使用全局策略来设置 Lync 客户端体验。请注意，全局策略适用于部署环境中的所有用户，但是用户级和站点级策略优先于全局策略：
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **选项 2：**修改环境中使用的现有客户端策略，引入启用 Lync 客户端体验的设置。这能让您将 Lync 客户端体验只分配给已分配了现有策略的那些用户：
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **选项 3：**创建包含 Lync 客户端体验设置的新策略来分配给用户。首先，创建新的客户端策略，然后将策略的名称作为 **Identity** 参数的值提供：
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然后，将策略的名称（用于 **Identity** 参数的值）用作 **PolicyName** 参数的值，将策略分配给用户：
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **第 3 步： 可选**-默认情况下，用户首次启动 Skype 业务客户端，使用 Skype 客户端体验并要求他们重新启动客户机获取 Lync 客户端体验的用户显示一个通知。 可以修改客户端计算机上的系统注册表，将环境配置为，在用户首次启动客户端时，显示 Lync 客户端体验，并且关闭客户端教程。 有关的步骤，您需要执行之前部署 Skype 业务客户端，请参阅[配置客户端使用 Skype 业务体验](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步骤 4:**您已配置客户端策略后，将部署 Skype 业务客户机，生成 4711.1002 (四月，2015) 或更高版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>在 Skype for Business Online 中使用 Lync 客户端体验
<a name="LyncwithSfBO"> </a>

如果您想要配置 Lync 客户端体验和您的在线业务使用 Skype，请按照本节中的步骤操作。
  
如果您使用 Skype 的在线业务，仍可用 Lync 客户端体验的 Skype 业务客户端组织中通过使用远程 PowerShell 来配置客户端策略。 使用客户端策略来设置客户端体验有 **3 个选项**。 请注意，策略和参数名称不同的设置用于配置客户端体验的业务或 Lync Server 使用 Skype 时内部。
  
 **选项 1:**通过使用全局策略设置 Lync 客户端体验。 请注意，客户端和网站应用于用户的策略将优先于全局策略。
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 2：**修改环境中使用的现有客户端策略，引入启用 Lync 客户端体验的设置。这能让您将 Lync 客户端体验只分配给已分配了现有策略的那些用户：
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **选项 3:**使用自定义策略的实例包括 Lync 客户端体验的设置。
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

您已配置客户端策略后，将部署 Skype 业务客户机，生成 4711.1002 (四月，2015) 或更高版本。
  
有关如何配置客户端的详细信息会遇到与 Skype 有关业务联机，包括有关如何控制首次运行的体验和 PowerShell 脚本可用来配置您的环境的步骤，请参阅[之间切换Skype 业务和 Lync 客户端用户界面的](https://aka.ms/SfBOUI)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>有助于为支持团队和最终用户做好更新准备的资源
<a name="support"> </a>

若要使它更容易为您和您的组织为过渡做好准备，我们有很多其他资源可用来帮助您规划、 教育和与最终用户。
  
- [视频： 为企业引入 Skype](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype 业务快速入门指南 （下载）](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 现为业务 Skype — — 请参见新增功能](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype 的业务： 为新用户的逐步式指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [为什么当我使用 Lync 看到 Skype 业务？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

