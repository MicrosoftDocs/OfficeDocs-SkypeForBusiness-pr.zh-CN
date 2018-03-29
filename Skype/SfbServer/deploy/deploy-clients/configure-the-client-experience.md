---
title: 配置 Skype for Business 的客户端体验
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要： 请阅读本主题，以了解如何配置适用于业务用户的 Skype 客户端体验。
ms.openlocfilehash: 9c1bc182c383ea7d806ce779f3d727e7925a59d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-client-experience-with-skype-for-business"></a>配置 Skype for Business 的客户端体验
 
**摘要：**阅读本主题，以了解如何配置适用于业务用户的 Skype 客户端体验。
  
Skype 为业务提供了新的用户体验，基于 Skype 使用者的产品体验。 Lync 的所有功能，除了 Skype 为业务提供新功能和简化的控件和熟悉的图标。 新的客户端体验的详细信息，请参阅[Lync 现在 Skype 业务和 #x 2014年; 最新信息，请参阅](https://go.microsoft.com/fwlink/?LinkId=529022)。
  
Skype 业务服务器支持新的 Skype 业务客户端体验以及 Lync 客户端体验。 作为管理员，你可以为用户选择首选客户端体验。 例如，可能要直到您组织中的用户将接受全面培训业务体验新的 Skype 在部署 Lync 客户端体验。 或者，如果您有尚未升级所有用户到 Skype 业务服务器，您可能希望所有用户直到所有都升级到新的服务器具有相同的客户端体验。
  
> [!IMPORTANT]
> 如果您的组织有两个 Skype 业务服务器，Lync Server 部署的默认客户端体验会随服务器版本和 UI 设置。 当用户首次启动业务的 Skype 时，他们将始终看到对于业务用户界面--Skype，即使选择了 Lync 客户端体验。 几分钟后，询问用户要切换到 Lync 模式。 有关更多信息，请参阅本主题后面部分的**首次启动客户端行为**。
  
> [!NOTE]
> Lync 2013 客户端体验不是 Skype 业务 2016年的客户端版本的选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="configure-the-client-experience"></a>配置客户端体验

您可以使用 **Set-CSClientPolicy** cmdlet 及 EnableSkypeUI 参数，指定组织内的用户将获得怎样的客户端体验：
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

其中 XdsIdentity 表示全局策略或指定站点策略。
  
下面的命令影响全球政策的组织中选择为所有用户的业务客户端体验的 Skype （请记住，站点或特定于用户的策略重写全局策略）： 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

下一步的命令组织受全球策略中选择 Lync 客户端体验的所有用户：
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

下一步的命令选择业务客户端体验雷蒙德站点内的所有用户的 Skype:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

如果您想要配置为您组织中特定用户的客户端体验，您可以通过使用**New CsClientPolicy** cmdlet，创建新的用户策略，然后通过**授予 CsClientPolicy**将策略分配给特定的用户cmdlet。
  
例如，以下命令将创建新的客户端策略，SalesClientUI，选择业务客户端体验的 Skype:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

下一条命令向销售部门的所有成员分配 SalesClientUI 策略：
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>首次启动客户端行为

默认情况下，当用户启动 Skype 业务的第一次，他们将始终看到 Skype 为业务用户界面--即使选择通过将 EnableSkypeUI 参数的值设置为 $False，如前面所述的 Lync 客户端体验. 几分钟时间后，系统将要求用户切换到 Lync 模式。
  
如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：
  
1. 确认的值`EnableSkypeUI`到 $False 中都使用前面所述的策略设置。
    
2. 更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。
    
    在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键中，创建新的“**二进制**”值。
    
    " **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。
    
    该注册表项应类似于以下内容：
    
  ```
  [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
"CanSharePptInCollab"=dword:00000001
"CanShareOneNoteInCollab"=dword:00000001
"CanAppShareInCollab"=dword:00000001
"EnableSkypeUI"=hex:00,00,00,00
  ```

当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制欢迎屏幕教程的显示

用户打开 Skype for Business 客户端时，默认行为是显示欢迎屏幕，其中包括 *人们最常请求获取的 7 条快速提示*  。 你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 **DWORD（32 位）值**。**值名称**必须为 **IsBasicTutorialSeenByUser**，**值数据**必须设为 **1**。
  
该注册表项应类似于以下内容：
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a>关闭客户端教程

如果你不希望你的用户能够访问教程，你可以使用以下注册表值关闭客户端教程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 **DWORD（32 位）值**。**值名称**必须为 **TutorialFeatureEnabled**，**值数据**必须设为 **0**。
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

您可以通过将**值数据**设为 **1** 来重新打开教程。
  
## <a name="default-client-behaviors"></a>默认客户端行为

如果您的组织有两个 Skype 业务服务器，Lync Server 部署的客户端体验会随服务器版本和 Skype 用户界面设置。 下表显示了基于服务器版本和 UI 设置的初始客户端体验：
  

|**服务器版本**|**EnableSkypeUI 设置**|**客户端体验**|
|:-----|:-----|:-----|
|Skype for Business Server 2015  <br/> |默认  <br/> |Skype for Business  <br/> |
|Skype for Business Server 2015  <br/> |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server 2015  <br/> |False  <br/> |要求用户切换到 Lync 模式 （用户可以切换到 Skype 的业务以后的用户界面设置更改为 $true）  <br/> |
|Lync Server 2010 或 Lync Server 2013 （与正确的修补程序）  <br/> |默认  <br/> |要求用户切换到 Lync 模式 （用户可以切换到 Skype 的业务以后的用户界面设置更改为 $true）  <br/> |
|Lync Server 2010 或 Lync Server 2013 （与正确的修补程序）  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 或 Lync Server 2013 （与正确的修补程序）  <br/> |False  <br/> |要求用户切换到 Lync 模式 （用户可以切换到 Skype 的业务以后的用户界面设置更改为 $true）  <br/> |
|Lync Server 2010 或 Lync Server 2013 （不带修补程序）  <br/> |默认  <br/> |要求用户切换到 Lync 模式 （用户无法切换到 Skype 的业务以后）  <br/> |
   
下表显示了客户端体验管理员更改 Skype 用户界面体验的初始设置时：
  

|**服务器版本**|**EnableSkypeUI 设置**|**客户端 UI = Lync**|**客户端 UI = Skype 业务**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server 2015  <br/> |True  <br/> |要求用户切换到 Skype 的业务  <br/> |Skype for Business  <br/> |
|Skype for Business Server 2015  <br/> |False  <br/> |Lync 模式  <br/> |要求用户切换到 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 （与正确的修补程序）  <br/> |True  <br/> |要求用户切换到 Skype 的业务  <br/> |Skype for Business  <br/> |
|Lync Server 2010 或 Lync Server 2013 （与正确的修补程序）  <br/> |False  <br/> |Lync 模式  <br/> |要求用户切换到 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 （不带修补程序）  <br/> |默认  <br/> |Lync 模式 （不能切换到 Skype 业务）  <br/> |Lync 模式 （不能切换到 Skype 业务）  <br/> |
   
管理业务客户端的 Skype 的配置所需的修补程序版本包括：
  
- Lync Server 2010-2015 2 月累积更新 (4.0.7577.710) 的 Lync Server 2010。 有关信息，请参阅[Lync Server 2010 中的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-2014 年 12 月累积更新 (5.0.8308.857) 的 Lync Server 2013。 有关信息，请参阅[更新 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>创建组策略对象以修改加入域的计算机上的注册表

应仅执行一次注册表更新以在用户首次启动 Skype for Business 客户端时显示 Lync 客户端体验。 如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。 应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。 
  
以下过程介绍了如何修改注册表，使得在用户首次启动 Skype for Business 时显示 Lync 客户端体验。 你还可以如前文所述，使用此过程更新注册表以禁用欢迎屏幕教程。
  
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
   |**配置单元** <br/> | 注册表 <br/> |
   |**键路径** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**值名称** <br/> |EnableSkypeUI  <br/> |
   |**值类型** <br/> |REG_BINARY  <br/> |
   |**值数据** <br/> |00000000  <br/> |
   
8. 单击" **确定**"以保存更改，然后关闭 GPO。
    
接下来，你需要将你创建的 GPO 链接到你希望分配策略的用户组，比如 OU。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>使用 GPO 分配策略

1. 在组策略管理控制台中，右键单击要分配策略的 OU，然后选择" **链接到现有 GPO**"。
    
2. 在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。
    
3. 在目标用户的计算机上，打开命令提示符并键入以下命令：
    
    **gpupdate /target:user**
    
    应用 GPO 时，将显示消息"正在更新策略..."。 完成时，将显示消息"已成功完成用户策略更新"。
    
4. 在命令提示符下，键入下列命令：
    
    **gpresult /r**
    
    您将在下面看到带有您创建的 GPO 名称的“已分配的组策略对象”。
    
您可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。打开注册表编辑器并导航至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键。如果 GPO 已成功更新注册表，您将看到名为 EnableSkypeUI 的值设为 0。
  

