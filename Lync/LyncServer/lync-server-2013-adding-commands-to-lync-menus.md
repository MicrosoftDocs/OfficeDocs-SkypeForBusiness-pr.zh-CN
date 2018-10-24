---
title: 向 Lync 菜单中添加命令
TOCTitle: 向 Lync 菜单中添加命令
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412788(v=OCS.15)
ms:contentKeyID: 52061088
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向 Lync 菜单中添加命令

 

_**上一次修改主题：** 2016-04-11_

您可以将自定义命令添加到 Lync 2013 菜单中，并将当前用户和所选联系人的 SIP 统一资源标识符 (URI) 传递给自定义命令启动的应用程序。

您添加的自定义命令可显示在以下一个或多个菜单上：

  - Lync 主窗口中菜单栏上的“工具”菜单

  - 联系人列表中的联系人快捷菜单

  - “对话”窗口中的“更多选项”菜单

  - “对话”窗口参与者列表中列出的人员快捷菜单

  - 联系人卡片中的选项菜单

您可以为执行以下操作之一的两种应用程序定义自定义命令：

  - 仅应用于当前用户且在本地计算机上启动。

  - 涉及其他用户（例如，联机协作程序）且必须在每个用户的计算机上启动。

可以用以下方式调用自定义命令：

  - 选择一个或多个用户，然后选择自定义命令。

  - 启动双方或多方对话，然后选择自定义命令。

## 添加自定义命令

使用下表中的注册表设置将命令添加到菜单中。这些项位于注册表中的以下位置：

HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\CustomCommands

### 自定义命令注册表项

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
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>显示在菜单上的应用程序的名称。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 可执行文件（默认）</p>
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
> 如果 ApplicationType 为 0（可执行文件），则必须指定完整路径。


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>要与所有参数一起启动的完整路径，其中包括默认参数 <em>%user-id%</em> 和 <em>%contact-id%</em>。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本地会话。应用程序在本地计算机上启动。</p>
<p>1 = 两方会话（默认）。Lync 2013 在本地启动应用程序，然后向其他用户发送桌面通知。其他用户单击该通知，以在其计算机上启动应用程序。</p>
<p>2 = 多方会话。Lync 2013 在本地启动应用程序，然后向其他用户发送桌面通知。其他用户单击通知在自己的计算机上启动指定应用程序。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单列表，用分号分隔。可能的值为：</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


例如，以下注册表编辑器 (.REG) 文件显示将“Contoso 销售联系人管理器”菜单项添加到“对话”窗口中的“操作”菜单的结果：

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\CustomCommands\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

## 访问自定义命令

要在添加自定义命令后访问该自定义命令，请根据您定义的 ExtensibleMenu 值执行以下操作之一：

  - **MainWindowActions** 在 Lync 主窗口中，单击“工具”，然后单击自定义命令。

  - MainWindowRightClick   在 Lync 主窗口中，右键单击一个联系人，然后单击自定义命令。

  - **ConversationWindowActions** 在“对话”窗口中，单击“更多选项”图标，然后单击自定义命令。

  - **ConversationWindowRightClick** 在“对话”窗口中，右键单击联系人名称，然后单击自定义命令。

  - **ContactCardMenu** 在人员的联系人卡片中，单击自定义命令。

