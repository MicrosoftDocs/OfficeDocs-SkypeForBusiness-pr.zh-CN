---
title: 在 Lync Server 2013 中配置 Skype for Business 客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a78e229b54ec165897d920d8f04db49451eac9b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>配置 Skype for Business 的客户端体验

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-09-17_

**摘要：** 本主题介绍如何在 Lync Server 2013 环境中为 Skype for business 客户端用户配置客户端体验。 仅当您使用12月2014累积更新（5.0.8308.857）或更高版本安装了运行 Lync Server 2013 时，才能配置客户端体验。 有关更新 Lync Server 2013 的信息，请参阅[Lync server 2013 更新](https://go.microsoft.com/fwlink/p/?linkid=532651)。

Skype for Business 提供了基于 Skype 消费者产品体验的全新用户体验。 除 Lync 的所有功能外，Skype for Business 还提供了具有简化的控件和熟悉的图标的新功能。 有关新的客户端体验的详细信息，请参阅[Lync 现在为 Skype For business--了解新增功能](https://go.microsoft.com/fwlink/?linkid=529022)。

Lync Server 2013 支持新的 Skype for Business 客户端体验和 Lync 客户端体验。 作为管理员，你可以为你的用户选择首选的客户端体验。 例如，您可能希望部署 Lync 客户端体验，直到贵组织中的用户在新的 Skype for Business 体验中进行了全面培训。 或者，如果尚未将所有用户升级到 Skype for Business Server 2015，您可能希望所有用户都具有相同的客户端体验，直至所有用户都已升级到新服务器。

<div>


> [!IMPORTANT]  
> 如果你的组织同时部署了 Skype for Business Server 2015 和 Lync Server 2013，则默认的客户端体验会有所不同，具体取决于服务器版本和 UI 设置。 当用户首次启动 Skype for business 时，他们将始终看到 Skype for Business 用户界面，即使您已选择 Lync 用户界面也是如此。 几分钟后，系统会要求用户切换到 Lync 模式。 有关详细信息，请参阅本主题后面的<STRONG>首次启动客户端行为</STRONG>。



</div>

<div>


> [!NOTE]  
> Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。 在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保其不以数字16开头;例如： x.x.x。



</div>

<div>

## <a name="configure-the-client-experience"></a>配置客户端体验

您可以通过将**set-csclientpolicy** Cmdlet 与 EnableSkypeUI 参数一起使用，指定组织中的用户将看到的客户端体验。 以下命令为组织中受全局策略影响的所有用户选择 Skype for Business 客户端体验（请记住，站点或用户特定的策略会覆盖全局策略）：

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

下一条命令为组织中受全局策略影响的所有用户选择 Lync 客户端体验：

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

下一个命令为 Redmond 站点内的所有用户选择 Skype for Business 客户端体验：

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

如果要为组织中的特定用户配置客户端体验，可以使用**set-csclientpolicy** cmdlet 创建新的用户策略，然后使用**set-csclientpolicy** cmdlet 将策略分配给特定用户。

例如，以下命令将创建一个新的客户端策略 SalesClientUI，该策略选择 Skype for Business 客户端体验：

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

下一个命令将策略 SalesClientUI 分配给销售部门的所有成员：

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>首次启动客户端行为

默认情况下，当用户首次启动 Skype for business 时，他们将始终看到 Skype for Business 用户界面，即使您已通过将 EnableSkypeUI 参数的值设置为 $False （如上文所述）选择了 Lync 客户端体验，也是如此. 几分钟后，系统会要求用户切换到 Lync 模式。

如果您想要在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在更新客户端后第一次启动时，按照以下步骤操作：

1.  确认 "" 的`EnableSkypeUI`值设置为 "在您正在使用的策略中 $False"，如上文所述。

2.  更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，并且应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面的部分。
    
    在 " ** \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\Lync\] **密钥" 中，创建新的**二进制**值。
    
    **值名称**必须为**EnableSkypeUI**，并且**值数据**必须设置为**00 00 00 00**。
    
    该注册表项应类似于以下内容：
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

在用户首次启动 Skype for Business 客户端时，将显示 Lync 用户界面。

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制欢迎屏幕教程的显示

当用户打开 Skype for Business 客户端时，默认行为是显示欢迎屏幕，其中包括*大多数用户要求的7条快速提示*。 您可以关闭欢迎屏幕的显示，但仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：

在 " ** \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中，创建新的**DWORD （32位）值**。 **值名称**必须为**IsBasicTutorialSeenByUser**，并且**值 data**必须设置为**1**。

该注册表项应类似于以下内容：

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>关闭客户端教程

如果您不希望您的用户能够访问教程，则可以使用以下注册表值关闭客户端教程：

在 " ** \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中，创建新的**DWORD （32位）值**。 **值名称**必须为**TutorialFeatureEnabled**，并且**值 data**必须设置为**0**。

    "TutorialFeatureEnabled"=dword:00000000

您可以通过将**值数据**设置为**1**来重新打开教程。

</div>

</div>

<div>

## <a name="default-client-experiences"></a>默认客户端体验

如果你的组织同时部署了 Skype for Business Server 2015 和 Lync Server，则客户端体验会有所不同，具体取决于服务器版本和 Skype UI 设置。 下表显示了基于服务器版本和 UI 设置的初始客户端体验：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>服务器版本</p></th>
<th><p>EnableSkypeUI 设置</p></th>
<th><p>客户端体验</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>默认值</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>用户需要切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在稍后切换到 Skype for Business）</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</p></td>
<td><p>默认值</p></td>
<td><p>用户需要切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在稍后切换到 Skype for Business）</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</p></td>
<td><p>False</p></td>
<td><p>用户需要切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在稍后切换到 Skype for Business）</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （无修补程序）</p></td>
<td><p>默认值</p></td>
<td><p>用户要求切换到 Lync 客户端体验（用户稍后无法切换到 Skype for Business）</p></td>
</tr>
</tbody>
</table>


下表显示管理员更改 Skype UI 体验的初始设置时的客户端体验：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>服务器版本</p></th>
<th><p>Skype UI 设置</p></th>
<th><p>客户端 UI = Lync</p></th>
<th><p>客户端 UI = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>用户需要切换到 Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>用户要求切换到 Lync UI</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</p></td>
<td><p>True</p></td>
<td><p>用户需要切换到 Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>用户要求切换到 Lync UI</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （无修补程序）</p></td>
<td><p>默认值</p></td>
<td><p>Lync 模式（无法切换到 Skype for Business）</p></td>
<td><p>Lync UI （无法切换到 Skype for Business）</p></td>
</tr>
</tbody>
</table>


管理 Skype for Business 客户端的配置所需的修补程序版本包括：

  - Lync Server 2010-Lync Server 2010 的二月份2015累积更新（4.0.7577.710）。 有关信息，请参阅[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-Lync Server 2013 的12月2014累积更新（5.0.8308.857）。 有关信息，请参阅[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?linkid=532772)。

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>创建组策略对象以修改加入域的计算机上的注册表

在用户首次启动 Skype for Business 客户端时，要显示 Lync 客户端体验的注册表更新应仅执行一次。 如果使用组策略对象（GPO）更新注册表，则需要定义对象以创建新值，而不是更新值数据。 应用 GPO 时，如果新值不存在，GPO 将创建它并将值数据设置为0。

以下过程介绍如何修改注册表，以便在用户首次启动 Skype for Business 时显示 Lync 客户端体验。 您还可以使用此过程更新注册表以禁用欢迎屏幕教程（如上文所述）。

**创建 GPO**

1.  启动 "**组策略管理控制台**"。
    
    有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](https://go.microsoft.com/fwlink/?linkid=532759)。

2.  右键单击 "**组策略对象**" 节点，然后在菜单上选择 "**新建**"。

3.  在 "**新建 GPO** " 对话框中，输入 GPO 的名称，例如 "**例如 makelyncdefaultui**"，然后单击 **"确定"**。

4.  右键单击刚创建的新 GPO，然后从菜单中选择 "**编辑**"。

5.  在**组策略管理编辑器**中，展开 **"用户配置**"，展开 "**首选项**"，展开 " **Windows 设置**"，然后选择 "**注册表**" 节点。

6.  右键单击 "**注册表**" 节点，然后选择 "**新建** \> **注册表项**"。

7.  在 "**新建注册表属性**" 对话框中，更新以下内容：
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>字段</th>
    <th>要选择或输入的值</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>操作</strong></p></td>
    <td><p><strong>创建</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>配置单元</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>键路径</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>值名称</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>值类型</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>值数据</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  单击 **"确定"** 以保存所做的更改，然后关闭该 GPO。

接下来，您需要将您创建的 GPO 链接到您要为其分配策略的用户组，例如 OU。

**使用 GPO 分配策略**

1.  在组策略管理控制台中，右键单击要为其分配策略的 OU，然后选择 "**链接到现有 GPO**"。

2.  在 "**选择 gpo** " 对话框中，选择您创建的 GPO，然后选择 **"确定"**。

3.  在目标用户的计算机上，打开命令提示符并键入以下命令：
    
    **gpupdate/target： user**
    
    邮件 "正在更新策略 ..."在应用 GPO 时显示。 完成后，将显示消息 "已成功完成用户策略更新"。

4.  在命令提示符处，键入以下命令：
    
    **gpresult/r**
    
    您应该会看到 "分配的组策略对象"，其名称如下所示：您创建的 GPO 的名称。

您还可以通过检查注册表来验证 GPO 是否已成功更新用户计算机上的注册表。 打开注册表编辑器并导航到** \[\_HKEY CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\] ** key。 如果 GPO 已成功更新注册表，您将看到一个名为 EnableSkypeUI 的值，值为0。

</div>

</div>

<span> </span>

</div>

</div>

</div>

