---
title: Lync Server 2013：将命令添加到 Lync 菜单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1cbce99116159d119eaa604b7000764913b3cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>在 Lync Server 2013 中将命令添加到 Lync 菜单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-04-11_

你可以将自定义命令添加到 Lync 2013 菜单，并将当前用户和所选联系人的 SIP 统一资源标识符（URI）传递给自定义命令启动的应用程序。

你添加的自定义命令可以显示在以下一个或多个菜单中：

  - Lync 主窗口中的菜单栏上的 "工具" 菜单

  - 联系人列表中联系人的快捷菜单

  - 对话窗口中的 "更多选项" 菜单

  - 对话窗口参与者列表中列出的人员的快捷菜单

  - 联系人卡片中的 "选项" 菜单

你可以为两种类型的应用程序定义自定义命令，即执行以下任一操作的应用程序：

  - 仅应用于当前用户并在本地计算机上启动。

  - 涉及其他用户（如联机协作程序），并且必须在每个用户的计算机上启动。

可通过以下方式调用自定义命令：

  - 选择一个或多个用户，然后选择 "自定义" 命令。

  - 启动两方或多方对话，然后选择 "自定义" 命令。

<div>

## <a name="to-add-a-custom-command"></a>添加自定义命令

使用下表中的注册表设置将命令添加到菜单。 这些条目放置在注册表中的以下位置之一：

  - 对于32位操作系统：\_HKEY\_本地\\计算机\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager 应用

  - 对于64位操作系统：\_HKEY\_LOCAL\\MACHINE\\软件\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager 应用

### <a name="custom-command-registry-entries"></a>自定义命令注册表项

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>类型</th>
<th>数据</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>REG_SZ</p></td>
<td><p>显示在菜单上的应用程序的名称。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>长</p></td>
<td><p>0 = 可执行文件（默认值）</p>
<div>

> [!NOTE]  
> 需要 ApplicationInstallPath。


</div>
<p>1 = 协议</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>可执行文件的完整路径。</p>
<div>

> [!NOTE]  
> 如果 ApplicationType 为0（可执行），则必须指定。


</div></td>
</tr>
<tr class="even">
<td><p>路径</p></td>
<td><p>REG_SZ</p></td>
<td><p>要与任何参数一起启动的完整路径，包括默认参数<em>% user id%</em>和<em>% contact id%</em>。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>长</p></td>
<td><p>0 = 本地会话。 在本地计算机上启动应用程序。</p>
<p>1 = 两方会话（默认值）。 Lync 2013 在本地启动应用程序，然后将桌面通知发送给另一个用户。 其他用户单击通知以在其计算机上启动应用程序。</p>
<p>2 = 多方会话。 Lync 2013 在本地启动应用程序，然后向其他用户发送桌面通知。 其他用户单击通知以在其计算机上启动指定的应用程序。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单的列表，用分号分隔。 可能的值：</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


例如，下面的注册表编辑器（。REG）文件显示在对话窗口中将 Contoso 销售联系人管理器菜单项添加到 "操作" 菜单的结果：

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>访问自定义命令

若要在添加自定义命令后访问它，请根据你定义的 ExtensibleMenu 值执行下列操作之一：

  - **MainWindowActions**   在 Lync 主窗口中，单击 "**工具**"，然后单击您的自定义命令。

  - **MainWindowRightClick**   在 Lync 主窗口中，右键单击某个联系人，然后单击您的自定义命令。

  - **ConversationWindowActions**   在对话窗口中，单击 "**更多选项**" 图标，然后单击您的自定义命令。

  - **ConversationWindowRightClick**   在对话窗口中，右键单击联系人姓名，然后单击您的自定义命令。

</div>

</div>

<span> </span>

</div>

</div>

</div>

