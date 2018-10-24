---
title: 将第三方协作应用程序与 Lync 集成
TOCTitle: 将第三方协作应用程序与 Lync 集成
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398068(v=OCS.15)
ms:contentKeyID: 52060949
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将第三方协作应用程序与 Lync 集成

 

_**上一次修改主题：** 2015-03-09_

您可以通过向注册表中添加有关任何第三方联机协作应用程序的信息，将 Lync 2013 与该应用程序集成。可以使用 Lync 2013 启动承载于内部服务器或基于 Internet 的服务上或两者上的数据会议会话。可以从联系人列表或者从现有的即时消息、语音或视频会话中启动协作或数据会议会话。Lync 2013 仅作为启动应用程序的一个工具。联机协作会话开始之后，所有现有的 Lync 2013 对话仍然保持活动状态。

以下各节介绍如何将 Lync 2013 与基于 Internet 和基于服务器的协作应用程序集成。

## 将基于 Internet 的协作应用程序与 Lync 2013 集成

一般而言，集成第三方协作应用程序的步骤如下：

1.  将有关该应用程序的信息添加到注册表中。

2.  组织者登录 Lync 2013 并选择要进行数据共享和协作的联系人。或者，组织者可能已经处于对话中，决定添加数据会议。

3.  Lync 2013 读取注册表，启动协作应用程序，然后向所选参与者发送一条自定义 SIP 消息，即一个 appINVITE。

4.  参与者接受邀请，每个人的计算机上将启动协作应用程序。Lync 2013 使用该注册表确定要使用的协作应用程序，然后使用 appINVITE 消息中包含的参数启动该应用程序。

下表介绍了将基于 Internet 的协作应用程序与 Lync 2013 集成时所需的注册表项。这些项位于注册表中的以下位置：

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### 基于 Internet 的协作应用程序的注册表项

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
<td><p>Lync 2013 菜单的应用程序名称。</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>16 像素 x 16 像素的图标（BMP 或 PNG 格式）的路径。</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>用于启动联机协作应用程序的参与者路径。</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>用于启动联机协作应用程序的组织者路径。此路径可以包含如同 Parameters 子项中定义的一个或多个自定义参数。例如，<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本地会话。应用程序在本地计算机上启动。</p>
<p>1 = 两方会话（默认）。Lync 2013 在本地启动应用程序，然后向其他用户发送一条系统通知。其他用户单击该通知，并在其计算机上启动指定的应用程序。</p>
<p>2 = 多方会话。Lync 2013 在本地启动应用程序，然后向其他用户发送系统通知，提示他们在自己的计算机上启动指定的应用程序。</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单列表，用分号分隔。可能的值为：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


下表介绍参数的注册表项。这些项位于 HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters 中。

### 基于 Internet 的协作应用程序的注册表项

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
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>以标记化的格式 (<code>%Parm1%</code>) 用于向 OriginatorPath 注册表项添加特定于用户的值。</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>请参见 Param1。</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>请参见 Param1。</p></td>
</tr>
</tbody>
</table>


下面的示例注册表设置将 ADatum Collaboration Client 与 Lync 2013 集成：

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

## 将基于服务器的协作应用程序与 Lync 2013 集成

添加用于从 Lync 2013 内启动基于服务器的协作应用程序的命令，所要进行的设置与上一节“将基于 Internet 的协作应用程序与 Lync 2013 集成”中介绍的设置类似。但是，不需要 OriginatorPath，且更改了某些值。注册表项位于以下位置：

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### 基于服务器的协作应用程序的注册表项

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
<td><p>值 = 1。将应用程序类型设置为协议。其他可能值在此情况下不适用。如果不存在，则将 ApplicationType 设置为 0（可执行）。</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>用于启动该协作应用程序的协议。对于 Live Meeting 2007，Path 的值设置为 <code>meet:%conf-uri%</code>。</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本地会话。应用程序在本地计算机上启动。</p>
<p>1 = 两方会话（默认）。Lync 2013 在本地启动应用程序，然后向其他用户发送一条系统通知。其他用户单击该通知，并在其计算机上启动指定的应用程序。</p>
<p>2 = 多方会话。Lync 2013 在本地启动应用程序，然后向其他用户发送系统通知，提示他们在自己的计算机上启动指定的应用程序。</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = 服务器的类型。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单列表，用分号分隔。可能的值为：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


以下示例添加了从 Lync 2013 内部启动 ADatum Collaboration Client 的命令。

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

