---
title: 将第三方协作应用程序与 Lync 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>将第三方协作应用程序与 Lync Server 2013 集成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-20_

你可以通过向注册表添加有关应用程序的信息, 将 Lync 2013 与任何第三方联机协作应用程序集成。 您可以使用 Lync 2013 启动在内部服务器、基于 Internet 的服务或两者之间托管的数据会议会话。 可以从 "联系人" 列表或从现有即时消息、语音或视频会话启动协作或数据会议会话。 Lync 2013 仅用作启动应用程序的工具。 联机协作会话开始后, 任何现有 Lync 2013 对话都将保持活动状态。

以下各部分介绍了如何将 Lync 2013 与基于 Internet 和基于服务器的协作应用程序集成。

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>将基于 Internet 的协作应用程序集成到 Lync 2013

通常情况下, 集成第三方协作应用程序涉及的步骤如下所示:

1.  有关应用程序的信息将添加到注册表中。

2.  组织者登录 Lync 2013 并选择联系人进行数据共享和协作。 或者, 组织者可能已经在对话中, 并且决定添加数据会议。

3.  Lync 2013 读取注册表, 启动协作应用程序, 然后将自定义 SIP 消息 (appINVITE) 发送给所选参与者。

4.  参与者接受邀请, 并在每个人的计算机上启动协作应用程序。 Lync 2013 使用注册表确定要使用的协作应用程序, 然后使用 appINVITE 消息中包含的参数启动该应用程序。

下表介绍了将基于 Internet 的协作应用程序与 Lync 2013 集成所需的注册表项。 这些条目放置在注册表中的以下位置:

  - HKEY\_LOCAL\_MACHINE\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\参数

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>基于 Internet 的协作应用程序的注册表项

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
<td><p>Lync 2013 菜单的应用程序名称。</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>指向16像素 x 16 像素图标、BMP 或 PNG 的路径。</p></td>
</tr>
<tr class="odd">
<td><p>路径</p></td>
<td><p>REG_SZ</p></td>
<td><p>用于启动联机协作应用程序的参与者路径。</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>用于启动联机协作应用程序的组织者路径。 此路径可以包含 "参数" 子项中定义的一个或多个自定义参数。 例如,<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>长</p></td>
<td><p>0 = 本地会话。 在本地计算机上启动应用程序。</p>
<p>1 = 两方会话 (默认值)。 Lync 2013 在本地启动应用程序, 然后将系统通知发送给另一个用户。 其他用户单击通知并在其计算机上启动指定的应用程序。</p>
<p>2 = 多方会话。 Lync 2013 在本地启动应用程序, 然后向其他用户发送系统通知, 提示用户在其自己的计算机上启动指定的应用程序。</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单的列表, 用分号分隔。 可能的值：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果未定义 ExtensibleMenu, 则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


下表描述了参数的注册表项。 这些条目\_位于 HKEY 当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\应用\\参数中。

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>基于 Internet 的协作应用程序的注册表项

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
<td><p>在标记化格式 (<code>%Parm1%</code>) 中使用, 用于将特定于用户的值添加到 OriginatorPath 注册表项。</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>请参阅 Param1。</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>请参阅 Param1。</p></td>
</tr>
</tbody>
</table>


以下示例注册表设置将 ADatum 协作客户端与 Lync 2013 集成:

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

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>将基于服务器的协作应用程序与 Lync 2013 集成

用于从 Lync 2013 中添加用于启动基于服务器的协作应用程序的命令的设置与上一节中所述, 将基于 Internet 的协作应用程序集成到 Lync 2013。 但是, OriginatorPath 不是必需的, 并且某些值已更改。 注册表项放置在以下位置:

  - HKEY\_LOCAL\_MACHINE\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\参数

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>基于服务器的协作应用程序的注册表项

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
<td><p>值 = 1。 将应用程序类型设置为 "协议"。 在此情况下, 其他可能的值不适用。 如果不存在, 则将 ApplicationType 设置为 0 (可执行文件)。</p></td>
</tr>
<tr class="odd">
<td><p>路径</p></td>
<td><p>REG_SZ</p></td>
<td><p>用于启动协作应用程序的协议。 对于 Live Meeting 2007, Path 的值设置为<code>meet:%conf-uri%</code>。</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>长</p></td>
<td><p>0 = 本地会话。 在本地计算机上启动应用程序。</p>
<p>1 = 两方会话 (默认值)。 Lync 2013 在本地启动应用程序, 然后将系统通知发送给另一个用户。 其他用户单击通知并在其计算机上启动指定的应用程序。</p>
<p>2 = 多方会话。 Lync 2013 在本地启动应用程序, 然后向其他用户发送系统通知, 提示用户在其计算机上启动指定的应用程序。</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = 服务器的类型。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>将显示此命令的菜单的列表, 用分号分隔。 可能的值：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果未定义 ExtensibleMenu, 则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</p></td>
</tr>
</tbody>
</table>


以下示例添加了从 Lync 2013 中启动 ADatum 协作客户端的命令:

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

</div>

</div>

<span> </span>

</div>

</div>

</div>

