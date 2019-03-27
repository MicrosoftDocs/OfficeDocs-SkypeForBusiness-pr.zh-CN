---
title: 配置与业务 2015年的 Skype 的客户端体验
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要： 阅读本主题可了解如何配置 Skype 业务用户的客户端体验。
ms.openlocfilehash: b8d258236a5254aa1dab5e86edb9586ea514c689
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875790"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>配置与业务 2015年的 Skype 的客户端体验
 
**摘要：** 阅读本主题可了解如何配置 Business 2015 用户 Skype 的客户端体验。
  
Skype 的业务 2015年提供基于 Skype 使用者产品体验的新用户体验。 Lync 的所有功能，除了 for Business 的 Skype 提供了简化的控件与熟悉的图标的新功能。 有关新的客户端体验的详细信息，请参阅[浏览 for Business 的 Skype](https://go.microsoft.com/fwlink/?LinkId=529022)。
  
Skype 业务服务器支持的商业客户端体验，以及 Lync 客户端体验的新 Skype。 作为管理员，你可以为用户选择首选客户端体验。 例如，您可能想要部署 Lync 客户端体验，直到您的组织中的用户进行完全培训中商业体验的新的 Skype。 或者，如果您具有尚未升级所有用户到 Skype 业务服务器，您可能希望所有用户都相同的客户端体验，直到所有都升级到新服务器。
  
> [!IMPORTANT]
> 如果您的组织有两个 Skype 业务 server 和 Lync Server 部署，将根据服务器版本和 UI 设置不同默认客户端体验。 当用户首次启动 for Business 的 Skype 时，它们始终会看到业务用户界面-Skype，即使您所选择的 Lync 客户端体验。 几分钟后，询问用户要切换到 Lync 模式。 有关更多信息，请参阅本主题后面部分的**首次启动客户端行为**。
  
> [!NOTE]
> Lync 2013 客户端体验不业务 2016年客户端版本或更高版本的 Skype 选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="configure-the-client-experience"></a>配置客户端体验

您可以使用 **Set-CSClientPolicy** cmdlet 及 EnableSkypeUI 参数，指定组织内的用户将获得怎样的客户端体验：
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

其中 XdsIdentity 表示全局策略或指定站点策略。
  
下面的命令组织受全局策略中选定的所有用户的商业客户端体验的 Skype （请记住，站点或特定于用户策略将覆盖全局策略）： 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

下一个命令选择受全局策略在组织中的所有用户的 Lync 客户端体验：
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

下一个命令选择为 Redmond 站点内的所有用户的商业客户端体验的 Skype:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

如果您想要配置组织内的特定用户的客户端体验，您可以使用**New-csclientpolicy** cmdlet 创建一个新用户策略，然后使用**Grant-csclientpolicy**将策略分配给特定用户cmdlet。
  
例如，以下命令创建新的客户端策略，SalesClientUI，选择业务客户端体验的 Skype 的：
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

下一条命令向销售部门的所有成员分配 SalesClientUI 策略：
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>首次启动客户端行为

默认情况下，当用户启动的业务 2015 Skype 第一次，他们将始终看到业务用户界面-Skype 即使选择通过将 EnableSkypeUI 参数的值设置为 $False，如下所述的 Lync 客户端体验以前。 几分钟时间后，系统将要求用户切换到 Lync 模式。
  
如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：
  
1. 确认的值`EnableSkypeUI`设置为 $False 中使用如前面所述的策略。
    
2. 更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。
    
    在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键中，创建新的“**二进制**”值。
    
    " **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。
    
    该注册表项应类似于以下内容：
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制欢迎屏幕教程的显示

当用户打开 Skype 业务客户端时的默认行为是显示欢迎屏幕包含*多数人寻求 7 导航的快速提示*。 你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 **DWORD（32 位）值**。**值名称**必须为 **IsBasicTutorialSeenByUser**，**值数据**必须设为 **1**。
  
该键应类似于以下内容：
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>关闭客户端教程

如果您不希望您的用户能够访问教程，您可以使用以下注册表值关闭客户端教程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 **DWORD（32 位）值**。**值名称**必须为 **TutorialFeatureEnabled**，**值数据**必须设为 **0**。
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

您可以通过将**值数据**设为 **1** 来重新打开教程。
  
## <a name="default-client-behaviors"></a>默认客户端行为

如果您的组织有两个 Skype 业务 server 和 Lync Server 部署，客户端体验将将有所不同具体取决于服务器版本和 Skype UI 设置。 下表显示了基于服务器版本和 UI 设置的初始客户端体验：
  

|**服务器版本**|**EnableSkypeUI 设置**|**客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Server |默认值  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |要求用户切换到 Lync 模式 （用户可以切换到 for Business 更高版本的 Skype 如果将 UI 设置更改为 $true）  <br/> |
|Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）  <br/> |默认值  <br/> |要求用户切换到 Lync 模式 （用户可以切换到 for Business 更高版本的 Skype 如果将 UI 设置更改为 $true）  <br/> |
|Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）  <br/> |False  <br/> |要求用户切换到 Lync 模式 （用户可以切换到 for Business 更高版本的 Skype 如果将 UI 设置更改为 $true）  <br/> |
|Lync Server 2010 或 Lync Server 2013 （不带修补程序）  <br/> |默认值  <br/> |要求用户切换到 Lync 模式 （用户无法切换到 Skype for Business 更高版本）  <br/> |
   
下表显示了客户端体验时管理员变化的 Skype UI 体验的初始设置：
  

|**服务器版本**|**EnableSkypeUI 设置**|**客户端 UI = Lync**|**客户端 UI = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |要求用户要切换到 Skype for Business  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync 模式  <br/> |要求用户切换到 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）  <br/> |True  <br/> |要求用户要切换到 Skype for Business  <br/> |Skype for Business  <br/> |
|Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）  <br/> |False  <br/> |Lync 模式  <br/> |要求用户切换到 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 （不带修补程序）  <br/> |默认值  <br/> |Lync 模式 （不能切换到 for Business 的 Skype）  <br/> |Lync 模式 （不能切换到 for Business 的 Skype）  <br/> |
   
管理业务客户端 Skype 的配置所需的修补程序版本是：
  
- Lync Server 2010-Lync Server 2010 的 2015 年 2 月版累积更新 (4.0.7577.710)。 有关信息，请参阅[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-Lync Server 2013 的 2014 年 12 月累积更新 (5.0.8308.857)。 有关信息，请参阅[Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>创建组策略对象以修改加入域的计算机上的注册表

要显示的 Lync 客户端体验第一次用户启动业务 2015年客户端 Skype 的注册表更新应仅执行一次。 如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。 应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。 
  
以下过程介绍如何修改注册表，以使 Lync 客户端体验显示第一次用户启动业务 2015年客户端 Skype。 你还可以如前文所述，使用此流程更新注册表以禁用欢迎屏幕教程。
  
### <a name="to-create-the-gpo"></a>创建 GPO

1. 启动" **组策略管理控制台**"。
    
    有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](https://go.microsoft.com/fwlink/?LinkId=532759)。
    
2. 右键单击" **组策略对象**"节点，然后选择菜单上的" **新建**"。
    
3. 在" **新建 GPO**"对话框中，输入 GPO 的名称，例如 MakeLyncDefaultUI，然后单击" **确定**"。
    
4. 右键单击你刚创建的新 GPO，然后在菜单上选择" **编辑**"。
    
5. 在" **组策略管理编辑器**"中，依次展开" **用户配置**"、" **首选项**"、" **Windows 设置**"，然后选择" **注册表**"节点。
    
6. Right-click on the **Registry** node, and then select **New** > **Registry Item**.
    
7. 在" **新建注册表属性**"对话框上，更新以下内容：
    
   |**字段**|**要选择或输入的值**|
   |:-----|:-----|
   |**操作** <br/> |**创建** <br/> |
   |**配置单元** <br/> | HKEY_CURRENT_USER <br/> |
   |**键路径** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**值名称** <br/> |EnableSkypeUI  <br/> |
   |**值类型** <br/> |REG_BINARY  <br/> |
   |**值数据** <br/> |00000000  <br/> |
   
8. 单击" **确定**"以保存更改，然后关闭 GPO。
    
接下来，您需要将您创建的 GPO 链接到您希望分配策略的用户组，比如 OU。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>使用 GPO 分配策略

1. 在组策略管理控制台中，右键单击要分配策略的 OU，然后选择“**链接到现有 GPO**”。
    
2. 在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。
    
3. 在目标用户的计算机上，打开命令提示符并键入以下命令：
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. 在命令提示符下，键入下列命令：
    
    **gpresult /r**
    
    您将在下面看到带有您创建的 GPO 名称的“已分配的组策略对象”。
    
您可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。打开注册表编辑器并导航至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键。如果 GPO 已成功更新注册表，您将看到名为 EnableSkypeUI 的值设为 0。
  

