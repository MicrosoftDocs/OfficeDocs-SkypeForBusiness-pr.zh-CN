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
ms.openlocfilehash: 1e1aa407fbb1d7d8a006698d30545165352386b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configure the client experience with Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-09-17_

**摘要：** 本主题介绍了如何在 Lync Server 2013 环境中配置 Skype for Business 客户端用户的客户体验。 只有在安装了12月2014累积更新（5.0.8308.857）或更高版本的情况运行 Lync Server 2013 时，才能配置客户端体验。 有关更新 Lync Server 2013 的详细信息，请参阅[Lync server 2013 更新](http://go.microsoft.com/fwlink/p/?linkid=532651)。

Skype for business 提供基于 Skype 消费者产品体验的全新用户体验。 除了 Lync 的所有功能之外，Skype for Business 还通过简化的控件和熟悉的图标提供新功能。 有关新的客户体验的详细信息，请参阅[Lync 现在是 Skype for business--查看新增功能](http://go.microsoft.com/fwlink/?linkid=529022)。

Lync Server 2013 支持全新的 Skype for Business 客户端体验以及 Lync 客户端体验。 作为管理员，你可以为用户选择首选客户端体验。 例如，你可能希望部署 Lync 客户端体验，直到你组织中的用户在新的 Skype for Business 体验中进行了全面培训。 或者，如果尚未将所有用户升级到 Skype for business Server 2015，你可能希望所有用户都具有相同的客户体验，直到所有用户都升级到新服务器。

<div>


> [!IMPORTANT]  
> 如果你的组织同时部署了 Skype for business Server 2015 和 Lync Server 2013，则默认的客户端体验会有所不同，具体取决于服务器版本和 UI 设置。 当用户首次启动 Skype for business 时，他们将始终看到 Skype for business 用户界面，即使您已选择 Lync 用户界面也是如此。 几分钟后，系统会要求用户切换到 Lync 模式。 有关更多信息，请参阅本主题后面部分的<STRONG>首次启动客户端行为</STRONG>。



</div>

<div>


> [!NOTE]  
> Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。



</div>

<div>

## <a name="configure-the-client-experience"></a>Configure the client experience

你可以通过**将 set-csclientpolicy** Cmdlet 与 EnableSkypeUI 参数一起使用来指定你的组织中的用户将看到的客户体验。 以下命令为组织中受全局策略影响的所有用户选择 Skype for Business 客户端体验（请记住，网站或特定于用户的策略替代全局策略）：

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

"下一步" 命令为组织中受全局策略影响的所有用户选择 Lync 客户端体验：

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

下一个命令为 Redmond 网站中的所有用户选择 Skype for Business 客户端体验：

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

如果你想要为你的组织内的特定用户配置客户端体验，你可以使用**set-csclientpolicy** cmdlet 创建新的用户策略，然后使用**set-csclientpolicy** cmdlet 将策略分配给特定用户。

例如，以下命令将创建一个新的客户端策略 SalesClientUI，该策略将选择 Skype for Business 客户端体验：

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

下一条命令向销售部门的所有成员分配 SalesClientUI 策略：

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>首次启动客户端行为

默认情况下，当用户第一次启动 Skype for business 时，他们将始终看到 Skype for business 用户界面，即使你已选择了 EnableSkypeUI 参数的值（如前面所述），也可通过将参数的值设置为 $False 来查看 Lync 客户端体验。. 几分钟时间后，系统将要求用户切换到 Lync 模式。

如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：

1.  确认的值`EnableSkypeUI`是否设置为在你使用的策略中 $False，如上文所述。

2.  更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。
    
    在 " ** \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\Lync\] **密钥" 中，创建一个新的**二进制**值。
    
    " **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。
    
    该注册表项应类似于以下内容：
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制欢迎屏幕教程的显示

当用户打开 Skype for Business 客户端时，默认行为是显示 "欢迎" 屏幕，其中包含*大多数人所要求的7个快速提示*。 你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：

在 " ** \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中，创建一个新的**DWORD （32位）值**。 " **值名称**"必须为 **IsBasicTutorialSeenByUser**，" **值数据**"必须设为 **1**。

该注册表项应类似于以下内容：

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>关闭客户端教程

如果你不希望你的用户能够访问教程，你可以使用以下注册表值关闭客户端教程：

在 " ** \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中，创建一个新的**DWORD （32位）值**。 " **值名称**"必须为 **TutorialFeatureEnabled**，" **值数据**"必须设为 **0**。

    "TutorialFeatureEnabled"=dword:00000000

你可以通过将" **值数据**"设为 **1** 来重新打开教程。

</div>

</div>

<div>

## <a name="default-client-experiences"></a>默认客户体验

如果你的组织同时部署了 Skype for business Server 2015 和 Lync Server，则客户体验将有所不同，具体取决于服务器版本和 Skype UI 设置。 下表显示了基于服务器版本和 UI 设置的初始客户端体验：


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
<td><p>用户要求切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在以后切换到 Skype for Business）</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 或 Lync Server 2013 （有正确的修补程序）</p></td>
<td><p>默认值</p></td>
<td><p>用户要求切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在以后切换到 Skype for Business）</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （有正确的修补程序）</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 或 Lync Server 2013 （有正确的修补程序）</p></td>
<td><p>False</p></td>
<td><p>用户要求切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在以后切换到 Skype for Business）</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （没有修补程序）</p></td>
<td><p>默认值</p></td>
<td><p>用户要求切换到 Lync 客户端体验（用户稍后无法切换到 Skype for Business）</p></td>
</tr>
</tbody>
</table>


下表显示了管理员更改 Skype UI 体验的初始设置时的客户体验：


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
<td><p>用户要求切换到 Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>用户要求切换到 Lync UI</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （有正确的修补程序）</p></td>
<td><p>True</p></td>
<td><p>用户要求切换到 Skype for Business</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 或 Lync Server 2013 （有正确的修补程序）</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>用户要求切换到 Lync UI</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 或 Lync Server 2013 （没有修补程序）</p></td>
<td><p>默认值</p></td>
<td><p>Lync 模式（无法切换到 Skype for Business）</p></td>
<td><p>Lync UI （无法切换到 Skype for Business）</p></td>
</tr>
</tbody>
</table>


管理 Skype for Business 客户端的配置所需的修补程序版本如下：

  - Lync Server 2010-Lync Server 2010 的2月2015累积更新（4.0.7577.710）。 有关信息，请参阅[Lync Server 2010 更新](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-Lync Server 2013 的2014累积更新（5.0.8308.857）。 有关信息，请参阅[Lync Server 2013 更新](http://go.microsoft.com/fwlink/p/?linkid=532772)。

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>创建组策略对象以修改加入域的计算机上的注册表

应仅执行一次注册表更新以在用户首次启动 Skype for Business 客户端时显示 Lync 客户端体验。 如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。 应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。

以下过程介绍了如何修改注册表，使得在用户首次启动 Skype for Business 时显示 Lync 客户端体验。 你还可以如前文所述，使用此过程更新注册表以禁用欢迎屏幕教程。

**创建 GPO**

1.  启动" **组策略管理控制台**"。
    
    有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](http://go.microsoft.com/fwlink/?linkid=532759)。

2.  右键单击" **组策略对象**"节点，然后选择菜单上的" **新建**"。

3.  在“**新建 GPO**”对话框中，输入 GPO 的名称，例如 **MakeLyncDefaultUI**，然后单击“**确定**”。

4.  右键单击您刚创建的新 GPO，然后在菜单上选择“**编辑**”。

5.  在" **组策略管理编辑器**"中，依次展开" **用户配置**"、" **首选项**"、" **Windows 设置**"，然后选择" **注册表**"节点。

6.  右键单击 "**注册表**" 节点，然后选择 "**新建** \> **注册表项**"。

7.  在“**新建注册表属性**”对话框上，更新以下内容：
    
    
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


8.  单击" **确定**"以保存更改，然后关闭 GPO。

接下来，你需要将你创建的 GPO 链接到你希望分配策略的用户组，比如 OU。

**使用 GPO 分配策略**

1.  在组策略管理控制台中，右键单击要分配策略的 OU，然后选择" **链接到现有 GPO**"。

2.  在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。

3.  在目标用户的计算机上，打开命令提示符并键入以下命令：
    
    **gpupdate /target:user**
    
    应用 GPO 时，将显示消息"正在更新策略..."。 完成时，将显示消息"已成功完成用户策略更新"。

4.  在命令提示符下，键入下列命令：
    
    **gpresult /r**
    
    你将在下面看到带有你创建的 GPO 名称的"已分配的组策略对象"。

你可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。 打开注册表编辑器并导航到** \[\_HKEY 当前\_用户\\软件\\Microsoft\\Office\\Lync\] **密钥。 如果 GPO 已成功更新注册表，你将看到名为 EnableSkypeUI 的值设为 0。

</div>

</div>

<span> </span>

</div>

</div>

</div>

