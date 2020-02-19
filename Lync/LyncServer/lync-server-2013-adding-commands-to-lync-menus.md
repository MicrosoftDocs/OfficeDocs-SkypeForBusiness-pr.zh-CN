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
ms.openlocfilehash: c8b4f44a1d28df4de8d79aa719f0eb1c350a27b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>在 Lync Server 2013 中向 Lync 菜单添加命令

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-04-11_

您可以向 Lync 2013 菜单中添加自定义命令，并将当前用户和所选联系人的 SIP 统一资源标识符（URI）传递给应用程序，自定义命令将启动。

您添加的自定义命令可以出现在以下一个或多个菜单上：

  - Lync 主窗口中的菜单栏上的 "工具" 菜单

  - "联系人" 列表中联系人的快捷菜单

  - 对话窗口中的 "更多选项" 菜单

  - 对话窗口参与者列表中列出的人员的快捷菜单

  - 联系人卡片中的 "选项" 菜单

您可以为两种类型的应用程序定义自定义命令，即执行下列操作之一的应用程序：

  - 仅应用于当前用户并在本地计算机上启动。

  - 涉及其他用户（如联机协作计划），并且必须在每个用户的计算机上启动。

可以通过以下方式调用自定义命令：

  - 选择一个或多个用户，然后选择 "自定义" 命令。

  - 启动两方或多方对话，然后选择 "自定义" 命令。

<div>

## <a name="to-add-a-custom-command"></a>添加自定义命令

使用下表中的注册表设置将命令添加到菜单中。 这些条目放置在注册表中的以下位置之一：

  - 对于32位 OS：\_HKEY\_LOCAL\\MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager Apps

  - 对于64位 OS：\_HKEY\_LOCAL\\MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager Apps

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
<th>Data</th>
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
<td><p>DWORD</p></td>
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
> 如果 ApplicationType 为0（可执行文件），则必须指定。


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>要与任何参数一起启动的完整路径，包括默认参数<em>% user id</em> % 和<em>% contact id%</em>。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本地会话。应用程序在本地计算机上启动。</p>
<p>1 = 两方会话（默认）。 Lync 2013 在本地启动应用程序，然后将桌面通知发送给其他用户。 另一个用户单击通知以在其计算机上启动应用程序。</p>
<p>2 = 多方会话。 Lync 2013 在本地启动应用程序，然后将桌面通知发送给其他用户。 另一个用户单击通知以在其计算机上启动指定的应用程序。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单列表，用分号分隔。 可能的值为：</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


例如，下面的注册表编辑器（。REG）文件显示在对话窗口中向 "操作" 菜单添加 Contoso Sales Contact Manager 菜单项的结果：

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

若要在添加自定义命令后对其进行访问，请执行下列操作之一，具体取决于您定义的 ExtensibleMenu 值：

  - **MainWindowActions**   在 Lync 主窗口中，单击 "**工具**"，然后单击您的自定义命令。

  - **MainWindowRightClick**   在 Lync 主窗口中，右键单击某个联系人，然后单击您的自定义命令。

  - **ConversationWindowActions**   在对话窗口中，单击 "**更多选项**" 图标，然后单击您的自定义命令。

  - **ConversationWindowRightClick**   在对话窗口中，右键单击某个联系人名称，然后单击您的自定义命令。

</div>

</div>

<span> </span>

</div>

</div>

</div>

