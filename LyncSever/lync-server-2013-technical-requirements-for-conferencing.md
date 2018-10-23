---
title: Lync Server 2013 会议技术要求
TOCTitle: 会议技术要求
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425889(v=OCS.15)
ms:contentKeyID: 49312565
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的会议技术要求

 

_**上一次修改主题：** 2016-12-08_

对于 Lync Server 2013，电话拨入式会议、A/V 会议、即时消息 (IM) 会议和 Web 会议功能始终在 前端服务器上运行。

本节详细介绍这些服务器的软硬件要求，以及支持的并置。

电话拨入式会议是包含各种组件的功能。一些组件是特定于电话拨入式会议的，一些组件是 企业语音组件。本节介绍特定于电话拨入式会议的组件的要求。有关 中介服务器和公用电话交换网 (PSTN) 网关要求的详细信息，请参阅规划文档中的 [Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)和 [Lync Server 2013 中中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md)。

## 硬件要求

由于 Web 会议和 A/V 会议与 前端服务器并置，因此服务器硬件要求与 前端服务器相同。有关硬件要求的详细信息，请参阅可支持性文档中的 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。电话拨入式会议必需的以下组件也与 前端服务器具有相同的硬件要求：

  - 应用程序服务

  - 会议助理应用程序

  - 会议通知应用程序

前端服务器与 Lync Server 2013 中的许多其他服务器角色具有相同的硬件要求，如下表所述。

## 软件要求

由于 Web 会议和 A/V 会议与 前端服务器并置，因此这两个会议与 前端服务器具有相同的服务器软件要求。有关软件要求的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

对于 Web 会议， Lync Server 2013 还要求 Office Web Apps 和 Office Web Apps Server（以前称为 WAC 服务器）处理 PowerPoint 演示文稿。有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

对于电话拨入式会议， 应用程序服务、 会议助理应用程序和 会议通知应用程序的操作系统要求与 前端服务器相同。有关软件要求的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

会议助理应用程序和 会议通知应用程序要求在 前端服务器上安装 Windows Media Format Runtime。Windows Media Format Runtime 是播放用于保持音乐、录制的名称和提示的 Windows Media 音频 (WMA) 文件所必需的。运行安装程序时，会作为 Windows 桌面体验的一部分自动安装 Windows Media Format Runtime，但您可能需要重新启动计算机（Windows Server 2012 和 Windows Server 2012 R2 除外）。因此，建议您在运行安装程序之前，作为 Windows 桌面体验的一部分安装，它包含 Windows Media Format Runtime。Windows Server 2012 和 Windows Server 2012 R2 需要 Microsoft 媒体基础。

## 电话拨入式会议的端口要求

下表介绍了电话拨入式会议所使用的端口。如果使用负载平衡器，请确保已为将在池中运行的应用程序所使用的端口配置负载平衡器。

这些端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 更改。有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

> [!NOTE]  
> 池中同一应用程序的所有实例都采用同一个 SIP 侦听端口。


### 电话拨入式会议所使用的端口

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>端口号</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>由 会议助理应用程序用于 SIP 侦听请求</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>由 会议通知应用程序用于 SIP 侦听请求</p></td>
</tr>
</tbody>
</table>


## 电话拨入式会议支持的客户端

您可以使用以下客户端安排支持拨入访问的内部会议：

  - Lync 2013 联机会议外接程序（安装 Lync 2013 或 与会者 时自动安装）

## 电话拨入式会议设置页要求

电话拨入式会议设置页支持下表所述的操作系统和 Web 浏览器的组合。

> [!NOTE]  
> 但支持 32 位和 64 位版本的操作系统。


### 支持的操作系统和 Web 浏览器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>操作系统</th>
<th>Web 浏览器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


## 电话拨入式会议的音频文件要求

Lync Server 2013 不支持自定义电话拨入式会议的语音提示和音乐。但是，如果您有迫切的业务需求，需要更改默认的音频文件，请参阅 Microsoft 知识库文章 961177 [如何在 Microsoft Office Communications Server 2007 R2 中自定义电话拨入式音频会议的语音提示或音乐文件](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。

您还可以使用 [Microsoft Lync Server 会议助理自定义语音提示](http://go.microsoft.com/fwlink/p/?linkid=396880)管理实用工具，它使管理员能够将电话呼叫者加入 Lync 会议时使用的默认语音提示替换为自定义提示，以提供不同的会议进入体验。自定义语音提示可以安装在运行 Lync Server 2010 或 Lync Server 2013（Enterprise 或 Standard Edition）的服务器上。

会议助理应用程序和 会议通知应用程序对保持音乐、录制的名称和音频提示文件有以下要求：

  - Windows Media 音频 (WMA) 文件格式

  - 16 位单声道

  - 48 kbps 2-pass CBR（恒定比特率）

  - 语音级别 - 24DB

## 电话拨入式会议的用户要求

电话拨入式会议用户必须为其帐户分配唯一的电话号码或分机。该要求支持在电话拨入式会议期间进行身份验证。企业用户（即组织中具有 Active Directory 域服务 凭据和 Lync Server 帐户的用户）输入他们的电话号码（或分机）和个人标识号 (PIN)，作为经过身份验证的用户拨号加入会议。

