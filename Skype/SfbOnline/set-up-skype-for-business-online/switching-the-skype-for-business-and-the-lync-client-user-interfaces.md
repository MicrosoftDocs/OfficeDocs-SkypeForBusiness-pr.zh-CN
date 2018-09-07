---
title: 在 Skype for Business 与 Lync 客户端用户界面之间切换
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: cde636a0919a1cc4e6c8c852e61040f6bee296eb
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857052"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>在 Skype for Business 与 Lync 客户端用户界面之间切换

对于 Skype for Business Online 组织，你可以使用 Office 365 中的 Remote PowerShell 让你的 Skype for Business 用户使用 Skype for Business 客户端或 Skype for Business (Lync) 客户端用户界面。 默认设置是让用户使用 Skype for Business 客户端用户界面。 如果您想要使用的 Lync 客户端体验，您可以管理要按照本主题后面的步骤中显示 Lync 用户界面的第一个启动客户端行为。
  
> [!NOTE]
> [!注释] Lync 2013 客户端体验不是 Skype for Business 2016 客户端版本的一个选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
> [!TIP]
> [!提示] 如果希望轻松切换用户界面，不希望执行手动步骤，请访问 [Microsoft 下载中心](https://go.microsoft.com/fwlink/?LinkId=532431)以获取 PowerShell 脚本来简化操作。
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>切换用户的 Skype for Business 用户界面

适用于 Skype for Business Online 的 Windows PowerShell 模块让你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。 有关其他信息，请参阅[为你的计算机配置 Skype for Business Online 管理](https://go.microsoft.com/fwlink/?LinkId=534539)。
  
> [!IMPORTANT]
> [!重要信息] 用于切换用户界面的  _Global_ 策略设置不会应用于已经应用了自定义设置的用户。 需要为已经应用了自定义策略的每位用户运行下面的命令，才能更改其用户界面：
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> [!警告]  _ClientPolicyEnableSkypeUI_ 策略将替换用户的现有自定义策略设置。
  
要让贵组织中的所有用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

如果策略设置正确，您将看到：
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
要让贵组织中的所有用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令： 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

如果策略设置正确，您将看到：
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
要让贵组织中的单个用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

如果策略设置正确，您将看到：
  
![Skype for Business Online - 启用 UI](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
要让贵组织中的单个用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

如果策略设置正确，您将看到：
  
![Skype for Business Online - UI 已禁用](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
要让贵组织中的多个用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

要让贵组织中的多个用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

要让贵组织中的一组用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

要让贵组织中的一组用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  [!注释]  用户的名称是应该为其分配该策略的用户帐户的名称。 可以以下列格式之一输入用户的帐户名称：>  用户的 SIP 地址>  用户的用户主体名称 (UPN)>  用户的域\\用户名>  用户的 Active Directory 显示名称
  
[使用 Windows PowerShell 管理 Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Skype for Business Online 策略设置

此表显示首次为用户应用了策略之后的用户体验：
  
|**管理员策略设置**|**显示的用户界面**|
|:-----|:-----|
|未设置策略。 |用户将继续使用 Skype for Business 客户端用户界面。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|用户将继续使用 Skype for Business 客户端用户界面。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|将请用户切换到 Skype for Business (Lync) 客户端用户界面。 他们可以以后切换。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|用户将使用 Skype for Business 客户端用户界面。 |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|将要求用户要切换到业务 (Lync) 客户端用户界面的 Skype。 管理员可以在以后更改用于将用户切换到 Skype for Business 客户端用户界面的设置。 |
   
此表显示更改了策略之后的用户体验：
  
|**管理员策略设置**|**Skype for Business (Lync) 用户界面**|**Skype for Business 用户界面**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|将请用户切换到 Skype for Business 客户端用户界面。  <br/> |用户将继续使用 Skype for Business 客户端用户界面。  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|用户将继续 Skype 用于业务 (Lync) 接口。  <br/> |将要求用户要切换到业务 (Lync) 客户端用户界面的 Skype。  <br/> |
|未设置策略。  <br/> |如果未设置策略，用户不会看到业务 (Lync) 客户端用户界面的 Skype。 他们将一直使用 Skype for Business 客户端用户界面。  <br/> |用户将继续使用 Skype for Business 客户端用户界面。  <br/> |
   
此表显示所有可用的联机自定义策略。 已创建新的策略来让管理员能够在 EnableSkypeUI 标志之间切换同时灵活保留旧的自定义策略。 请使用上面的 cmdlet 来向用户授予以下策略之一。
  
|**策略名称**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |假|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |假|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |假|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |假|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |假|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|假|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |假|

   
若要开始使用 Windows PowerShell，请参阅下列主题：
  
- [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [使用 Windows PowerShell 管理 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>首次启动客户端行为

默认情况下，当用户第一次，启动 for Business 的 Skype 他们将始终看到业务用户界面-Skype 即使选择通过将客户端策略设置为 Lync 客户端体验的 Lync 客户端体验 (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) 所述以前。 几分钟时间后，系统将要求用户切换到 Lync 模式。
  
如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：
  
1. 按照本主题前面部分中的步骤进行操作，确认客户端策略设置为禁用 Skype for Business 用户界面。
    
2. 更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。
    
    在 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** 注册表项中，创建新的" **二进制**"值。
    
    " **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。
    
    该注册表项应类似于以下内容：
    
    [HKEY_CURRENT_USER\\软件\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab"= dword:00000001
    
    "CanShareOneNoteInCollab"= dword:00000001
    
    "CanAppShareInCollab"= dword:00000001
    
    "EnableSkypeUI"= 十六进制： 00 00 00、 00
    
当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制欢迎屏幕教程的显示

当用户打开 Skype 业务客户端时的默认行为是显示欢迎屏幕包含*多数人寻求 7 导航的快速提示*。 你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：
  
在 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** 注册表项中，创建新的 **DWORD（32 位）值**。 " **值名称**"必须为 **IsBasicTutorialSeenByUser**，" **值数据**"必须设为 **1**。
  
该注册表项应类似于以下内容：
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>关闭客户端教程

如果你不希望你的用户能够访问教程，你可以使用以下注册表值关闭客户端教程：
  
在 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** 注册表项中，创建新的 **DWORD（32 位）值**。 " **值名称**"必须为 **TutorialFeatureEnabled**，" **值数据**"必须设为 **0**。
  
```
"TutorialFeatureEnabled"=dword:00000000
```

你可以通过将" **值数据**"设为 **1** 来重新打开教程。
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>创建组策略对象以修改加入域的计算机上的注册表

应仅执行一次注册表更新以在用户首次启动 Skype for Business 客户端时显示 Lync 客户端体验。 如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。 应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。
  
以下过程介绍了如何修改注册表，使得在用户首次启动 Skype for Business 时显示 Lync 客户端体验。 你还可以如前文所述，使用此过程更新注册表以禁用欢迎屏幕教程。
  
 **创建 GPO**
  
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
|**注册表项路径** <br/> |软件\\Microsoft\\Office\\Lync  <br/> |
|**值名称** <br/> |EnableSkypeUI  <br/> |
|**值类型** <br/> |REG_BINARY  <br/> |
|**值数据** <br/> |00000000  <br/> |
   
单击" **确定**"以保存更改，然后关闭 GPO。
    
接下来，你需要将你创建的 GPO 链接到你希望分配策略的用户组，比如 OU。
  
 **若要使用 GPO 分配策略**
  
1. 在组策略管理控制台中，右键单击要分配策略的 OU，然后选择" **链接到现有 GPO**"。
    
2. 在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。
    
3. 在目标用户的计算机上，打开命令提示符并键入以下命令：
    
    **gpupdate /target:user**
    
    应用 GPO 时，将显示消息"正在更新策略..."。 完成时，将显示消息"已成功完成用户策略更新"。
    
4. 在命令提示符下，键入下列命令：
    
    **gpresult /r**
    
    你将在下面看到带有你创建的 GPO 名称的"已分配的组策略对象"。
    
你可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。 打开注册表编辑器并导航至 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** 注册表项。 如果 GPO 已成功更新注册表，你将看到名为 EnableSkypeUI 的值设为 0。
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 