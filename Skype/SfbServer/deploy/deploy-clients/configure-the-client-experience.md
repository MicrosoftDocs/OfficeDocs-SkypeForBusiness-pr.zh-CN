---
title: 使用 Skype for Business 2015 配置客户端体验
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要：阅读本主题，了解如何为 Skype for Business 用户配置客户端体验。
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096006"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>使用 Skype for Business 2015 配置客户端体验
 
**摘要：** 阅读本主题，了解如何为 Skype for Business 2015 用户配置客户端体验。
  
Skype for Business 2015 提供基于 Skype 消费者产品体验的新用户体验。 除了 Lync 的所有功能外，Skype for Business 还提供了新功能，并提供了简化的控件和熟悉的图标。 有关新客户端体验的详细信息，请参阅[探索 Skype for Business。](https://go.microsoft.com/fwlink/?LinkId=529022)
  
Skype for Business Server 支持新的 Skype for Business 客户端体验以及 Lync 客户端体验。 作为管理员，您可以选择用户的首选客户端体验。 例如，你可能想要部署 Lync 客户端体验，直到组织中用户经过全面培训了解新的 Skype for Business 体验。 或者，如果你尚未将所有用户升级到 Skype for Business Server，你可能希望所有用户都具有相同的客户端体验，直到所有用户都升级到新服务器。
  
> [!IMPORTANT]
> 如果你的组织同时部署了 Skype for Business Server 和 Lync Server，则默认客户端体验将因服务器版本和 UI 设置不同而不同。 当用户首次启动 Skype for Business 时，他们将始终看到 Skype for Business 用户界面，即使你已选择 Lync 客户端体验。 几分钟后，将要求用户切换到 Lync 模式。 有关详细信息，请参阅本主题稍后介绍的 **首次** 启动客户端行为。
  
> [!NOTE]
> Lync 2013 客户端体验不是 Skype for Business 2016 客户端版本或更高版本的选项。 在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保它不会以数字 16 开始;例如：16.x.x.x。 
  
## <a name="configure-the-client-experience"></a>配置客户端体验

可以使用 **Set-CSClientPolicy** cmdlet 和 EnableSkypeUI 参数指定组织中用户将看到的客户端体验：
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

其中 XdsIdentity 引用全局策略或命名站点策略。
  
以下命令为组织中受全局策略影响的所有用户选择 Skype for Business 客户端体验 (请记住，站点或用户特定的策略会覆盖全局策略) ： 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

下一个命令为组织中受全局策略影响的所有用户选择 Lync 客户端体验：
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

下一个命令为 Redmond 站点内的所有用户选择 Skype for Business 客户端体验：
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

如果要为组织中特定用户配置客户端体验，可以使用 **New-CsClientPolicy** cmdlet 创建新的用户策略，然后使用 **Grant-CsClientPolicy** cmdlet 将策略分配给特定用户。
  
例如，以下命令创建一个新的客户端策略 SalesClientUI，用于选择 Skype for Business 客户端体验：
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

下一个命令将策略 SalesClientUI 分配给销售部门的所有成员：
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>首次启动客户端行为

默认情况下，当用户首次启动 Skype for Business 2015 时，他们将始终看到 Skype for Business 用户界面，即使你已按前面所述将 EnableSkypeUI 参数的值设置为 $False 选择了 Lync 客户端体验。 几分钟后，将要求用户切换到 Lync 模式。
  
如果你想要在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请按照以下步骤在客户端更新后首次启动：
  
1. 确认 的值已  `EnableSkypeUI` 设置为 $False，如前文所述，
    
2. 更新用户计算机上系统注册表。 你应该在用户首次启动 Skype for Business 客户端之前这样做，并且你应仅执行一次此操作。 若要了解如何创建组策略对象以更新加入域的计算机的注册表，请参阅本主题稍后部分的内容。
    
    在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键中，创建新的 **Binary** 值。
    
    值 **名称** 必须为 **EnableSkypeUI**，值数据 **必须设置为** **00 00 00 00 00**。
    
    该键应如下所示：
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制欢迎屏幕教程的显示

当用户打开 Skype for Business 客户端时，默认行为是显示欢迎屏幕，其中包括  *大多数用户请求的 7* 个快速提示。 You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 DWORD (**32 位**) 值 。 值 **名称** 必须为 **IsBasicTutorialSeenByUser**， **值** 数据必须设置为 **1**。
  
该键应如下所示：
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>关闭客户端教程

如果你不希望用户能够访问本教程，可以使用以下注册表值关闭客户端教程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 DWORD (**32 位**) 值 。 值 **名称** 必须为 **TutorialFeatureEnabled**， **值** 数据必须设置为 **0**。
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

可以通过将值数据设置为 **1****来重新** 打开教程。
  
## <a name="default-client-behaviors"></a>默认客户端行为

如果你的组织同时部署了 Skype for Business Server 和 Lync Server，则客户端体验将有所不同，具体取决于服务器版本和 Skype UI 设置。 下表显示了基于服务器版本和 UI 设置的初始客户端体验：
  

|**服务器版本**|**EnableSkypeUI 设置**|**客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Server |默认  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |用户要求切换到 Lync 模式 (如果你将 UI 设置更改为 Skype for Business，用户稍后可以$true)   <br/> |
|Lync Server 2010 或 Lync Server 2013 (正确的修补程序)   <br/> |默认  <br/> |用户要求切换到 Lync 模式 (如果你将 UI 设置更改为 Skype for Business，用户稍后可以$true)   <br/> |
|Lync Server 2010 或 Lync Server 2013 (正确的修补程序)   <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 或 Lync Server 2013 (正确的修补程序)   <br/> |False  <br/> |用户要求切换到 Lync 模式 (如果你将 UI 设置更改为 Skype for Business，用户稍后可以$true)   <br/> |
|Lync Server 2010 或 Lync Server 2013 (修补程序)   <br/> |默认  <br/> |系统要求用户切换到 Lync 模式 (以后无法切换到 Skype for Business)   <br/> |
   
下表显示了管理员更改 Skype UI 体验的初始设置时客户端体验：
  

|**服务器版本**|**EnableSkypeUI 设置**|**客户端 UI = Lync**|**客户端 UI = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |要求用户切换到 Skype for Business  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync 模式  <br/> |要求用户切换到 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 (正确的修补程序)   <br/> |True  <br/> |要求用户切换到 Skype for Business  <br/> |Skype for Business  <br/> |
|Lync Server 2010 或 Lync Server 2013 (正确的修补程序)   <br/> |False  <br/> |Lync 模式  <br/> |要求用户切换到 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 (修补程序)   <br/> |默认  <br/> |Lync 模式 (无法切换到 Skype for Business)   <br/> |Lync 模式 (无法切换到 Skype for Business)   <br/> |
   
管理 Skype for Business 客户端配置所需的修补程序版本包括：
  
- Lync Server 2010 - 2015 年 2 月累积更新 (4.0.7577.710) Lync Server 2010。 有关信息，请参阅 [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - Lync Server 2013 的 2014 年 12 月累积 (5.0.8308.857) 5.0.8308.857。 有关信息，请参阅[Updates for Lync Server 2013。](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>创建组策略对象以修改加入域的计算机上注册表

用户首次启动 Skype for Business 2015 客户端时显示 Lync 客户端体验的注册表更新应仅执行一次。 如果使用组策略对象 (GPO) 更新注册表，则需要定义对象以创建新值，而不是更新值数据。 应用 GPO 时，如果新值不存在，GPO 将创建它，将值数据设置为 0。 
  
以下过程介绍如何修改注册表，以便用户首次启动 Skype for Business 2015 客户端时显示 Lync 客户端体验。 您还可以使用此过程更新注册表以禁用欢迎屏幕教程，如前面所述。
  
### <a name="to-create-the-gpo"></a>创建 GPO

1. 启动 **组策略管理控制台**。
    
    有关如何使用组策略管理控制台的信息，请参阅组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))。
    
2. 右键单击组 **策略对象节点** ，然后选择 **菜单** 上的新建。
    
3. 在"**新建 GPO"** 对话框中，输入 GPO 的名称，例如 MakeLyncDefaultUI，然后单击"确定 **"。**
    
4. 右键单击刚创建的新 GPO， **然后从菜单中** 选择"编辑"。
    
5. 在组 **策略管理编辑器** 中，展开 **"用户配置**"，展开 **"首选项"，** 展开 **"Windows** 设置"，然后选择 **"注册表"** 节点。
    
6. 右键单击注册表 **节点**，**然后选择新建**  >  **注册表项**。
    
7. 在" **新建注册表属性"** 对话框中，更新以下内容：
    
   |**Field**|**要选择或输入的值**|
   |:-----|:-----|
   |**操作** <br/> |**创建** <br/> |
   |**配置单元** <br/> | HKEY_CURRENT_USER <br/> |
   |**密钥路径** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**值名称** <br/> |EnableSkypeUI  <br/> |
   |**值类型** <br/> |REG_BINARY  <br/> |
   |**值数据** <br/> |00000000  <br/> |
   
8. 单击 **"** 确定"保存更改，然后关闭 GPO。
    
接下来，需要将创建的 GPO 链接到要为其分配策略的一组用户，例如 OU。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>使用 GPO 分配策略

1. 在组策略管理控制台中，右键单击要为其分配策略的 OU，然后选择"链接到 **现有 GPO"。**
    
2. 在"**选择 GPO"** 对话框中，选择你创建的 GPO，然后选择"确定 **"。**
    
3. 在目标用户的计算机上，打开命令提示符并键入以下命令：
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. 在命令提示符处，键入以下命令：
    
    **gpresult /r**
    
    你应该会看到"分配的组策略对象"，下面显示了你创建的 GPO 的名称。
    
您还可以通过检查注册表来验证 GPO 是否成功更新了用户计算机上注册表。 打开注册表编辑器并导航到 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 项。 如果 GPO 成功更新注册表，你将看到一个名为 EnableSkypeUI 的值，值为 0。
