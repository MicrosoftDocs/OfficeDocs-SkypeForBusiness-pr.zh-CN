---
title: Lync Server 2013：Lync 客户端软件支持
TOCTitle: Lync 客户端软件支持
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412781(v=OCS.15)
ms:contentKeyID: 49313834
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Lync 客户端软件支持

 

_**上一次修改主题：** 2016-12-08_

本节总结了 Lync 2013 和 Lync 2013 联机会议外接程序的软件支持。

> [!NOTE]  
> 支持在 Outlook 消息和协作客户端中进行会议管理的 Lync 2013 联机会议外接程序 将自动随 Lync 2013 一起安装。



### Lync 2013 和 Lync 2013 联机会议外接程序的软件要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>系统组件</th>
<th>最低要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 操作系统</p></td>
<td><p>Windows 8.1</p>
<p>Windows 8</p>
<p>Windows 7 操作系统</p>
<p>带有最新 Service Pack 的 Windows Server 2008 R2</p>
<div>

> [!NOTE]  
> 在 Windows Vista 或 Windows XP（任何版本）上不支持 Lync 2013 和 Lync 2013 联机会议外接程序


</div></td>
</tr>
<tr class="even">
<td><p>安装和更新</p></td>
<td><p>管理员权限</p></td>
</tr>
<tr class="odd">
<td><p>浏览器</p></td>
<td><p>Windows Internet Explorer 10 Internet 浏览器</p>
<p>Internet Explorer 9 Internet 浏览器</p>
<p>Internet Explorer 8 Internet 浏览器</p>
<p>Internet Explorer 7 Internet 浏览器</p>
<p>Mozilla Firefox Web 浏览器</p>
<div>

> [!NOTE]  
> 如果将 Lync 与 Microsoft Exchange Online 一起使用，并且您的组织已部署身份验证 HTTP 代理，则需要 Internet Explorer 9 或 Internet Explorer 8。


</div></td>
</tr>
<tr class="even">
<td><p>Microsoft Office 集成</p></td>
<td><p>要获得全套集成功能：</p>
<ul>
<li><p>Outlook 2013 消息和协作客户端</p></li>
<li><p>Outlook 2010 消息和协作客户端</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Microsoft Exchange 集成</p></td>
<td><p>要获得全套集成功能：</p>
<ul>
<li><p>Microsoft Exchange Server 2013</p></li>
<li><p>Microsoft Exchange Server 2010</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Macintosh 操作系统

Lync 2013 仅适用于 Windows。但是，Lync Server 2013 在运行 Mac OS 10.5.8 或最新 Service Pack 或版本（基于 Intel）操作系统（当前不支持 Mac OS 10.9 操作系统）的计算机上支持以下客户端。有关支持的功能的详细信息，请参阅[Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)。

  - Microsoft Lync for Mac 2011（请参阅“Lync for Mac 2011 部署指南”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=268786](http://go.microsoft.com/fwlink/p/?linkid=268786)）

  - Microsoft Communicator for Mac 2011（请参阅“Communicator for Mac 2011 部署指南”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=268787](http://go.microsoft.com/fwlink/p/?linkid=268787)）

## Lync Web App 浏览器

Lync Web App 支持操作系统和浏览器的特定组合。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中 Lync Web App 支持的平台](lync-server-2013-lync-web-app-supported-platforms.md)。

## Microsoft Office 可支持性

Lync Server 2013 客户端支持与各种版本的 Microsoft Office 进行集成，如本节中所概括。

  - Outlook 2013 和 Microsoft Outlook 2010 上支持 Lync 2013 集成功能。

  - Microsoft Exchange Server 2013 和 Microsoft Exchange Server 2010 上支持 Lync 2013 集成功能。

  - Office 2013 和 Microsoft Office 2010 支持 Lync 2013 的联机会议加载项。

## 使用必需的配置文件

如果用户计划使用 Lync 2013 会议功能，他们不应使用 Active Directory 域服务 必需的配置文件登录到 Lync 2013 客户端。因为必需的配置文件是只读用户配置文件，所以 Lync 2013 会议所需的公钥基础结构 (PKI) 密钥无法保存到该配置文件中。有关详细信息，请参阅 Microsoft 知识库文章 2552221“当用户使用必需的用户配置文件登录时，Lync 2010 会议功能失败”，网址为 [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x804)。

## 另请参阅

#### 概念

[Lync Server 2013 中的 Lync 客户端硬件支持](lync-server-2013-lync-client-hardware-support.md)  
[Lync Server 2013 的 Lync 客户端视频要求](lync-server-2013-lync-client-video-requirements.md)  
[Lync Server 2013 先前部署中支持的客户端](lync-server-2013-supported-clients-from-previous-deployments.md)

