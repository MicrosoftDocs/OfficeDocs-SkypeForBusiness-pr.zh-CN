---
title: Lync Server 2013 客户端
TOCTitle: Lync Server 的客户端
ms:assetid: e143ce9b-3624-4066-942d-6c86ad99be91
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398996(v=OCS.15)
ms:contentKeyID: 49314521
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的客户端

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 支持几种可部署到组织用户的客户端软件，其中包括计算机上安装的客户端软件、基于 Web 的客户端以及移动设备。本主题概述了您可以使用的不同客户端。有关对 Lync Server 2013 客户端提供的功能进行比较的详细信息，请参阅 [Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)。

## Lync 2013

Lync 2013 是 Lync Server 的全功能客户端。 Lync 2013 用户界面经过完全重新设计，包括了新集成的功能，如 持久聊天（ Lync 2010 有针对聊天功能的单独客户端）、选项卡式对话、视频预览和多方视频。有关变更摘要，请参阅 [Lync Server 2013 中面向客户端的新内容](lync-server-2013-what-s-new-for-clients.md)。

Lync 2013 客户端安装程序是安装介质上 Office 安装程序的一部分。

## Lync 2013 联机会议外接程序

Lync 2013 联机会议外接程序 支持从 Microsoft Outlook 消息和协作客户端中管理会议。 Lync 2013 联机会议外接程序 软件会自动随 Lync 2013 一起安装。

## Lync Web 计划程序

Lync Web 计划程序是基于 Web 的会议计划和管理工具，适用于没有权限访问 Microsoft Outlook 或使用未基于 Windows 的操作系统的用户。利用 Lync Web 计划程序，用户可以创建新会议、修改现有会议和使用他们首选的电子邮件程序发送邀请。

## Lync Web App

Lync Web App 是用于 Lync Server 2013 会议的基于 Web 的会议客户端。在此版本中， Lync Web App 增加了计算机音频和视频，这为没有在本地安装 Lync 客户端的用户提供了完整的会议体验。与会者有权访问所有协作和共享功能以及演示者会议控制。

如果用户的计算机上未安装 Lync 2013 并且用户单击了会议请求中的会议链接，将打开 Lync Web App。您还可以配置会议加入页面以允许用户使用早期版本的客户端加入会议；请参阅部署文档中的 [在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)。

由于对 Lync Web App 进行了增强，更新版本的 Microsoft Lync 2010 Attendee 不可用于 Lync Server 2013。 Lync Web App 是组织外部参与者的客户端选择。使用 Lync Web App 时，无需安装本地客户端，但首次使用时，音频、视频和共享功能需要安装插件。

## Lync 2013 基本

Lync 2013 Basic 是可下载的客户端，适用于拥有授权的本地 Lync Server 2013 部署的客户以及订阅了不包括完整 Lync 2013 客户端的 Microsoft Office 365 计划的客户。 Lync Basic 客户端包括增强的状态、联系人、即时消息 (IM)、 Lync 会议和基本语音功能。 Lync Basic 不支持的功能包括多方视频、OneNote 集成、虚拟桌面基础结构 (VDI) 支持、技能搜索、录音、企业语音功能和高级呼叫处理（例如，呼叫转接和团队呼叫）。有关详细信息，请参阅 [Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)。

## Lync Windows 应用商店应用

Lync Windows 应用商店应用是专为 Windows 8.1、Windows 8 和 Windows RT 设计的触控优化的 Lync 应用。用户可以通过搜索“Lync”从 Windows 应用商店中下载应用。有关详细信息，请参阅[Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)、[Lync Windows Store 应用程序要求](lync-server-2013-lync-windows-store-app-requirements.md)和[部署 Lync Windows 应用商店应用](lync-server-2013-deploying-lync-windows-store-app.md)。

## 适用于移动设备的 Lync 2013

Lync 2013 移动应用程序现在包括 IP 语音 (VoIP) 和 IP 视频功能，此外，还包括联系人、状态和 IM 功能。移动用户可以选择使用 Wi-Fi 或其蜂窝数据连接来通过 IM、语音呼叫或视频呼叫来与其他用户进行通信。只需单击日历项目中的会议链接，移动用户即可加入语音和视频会议。有关 Lync 2013 移动应用程序的详细信息，请参阅 [在 Lync Server 2013 中规划移动客户端](lync-server-2013-planning-for-mobile-clients.md)。

## 支持的早期版本的客户端

Lync Server 2013 支持早期服务器版本的以下客户端。您可以在用户加入会议时将特定早期客户端提供给他们。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)。

  - **Lync 2010**    Lync 2010 提供了完整的桌面体验，包括 IM、增强的状态、语音、视频、共享和电话。然而，在将用户的客户端升级到 Lync 2013 之前， Lync Server 2013 中引入的任何新功能均无法使用。

  - **Lync 2010 Mobile**   Lync Server 2013 支持所有 Microsoft Lync 2010 Mobile 移动应用程序。Microsoft Lync 2010 Mobile 为您的组织中从智能手机或运行 Windows Mobile Professional Edition 的电话进行连接的用户提供 IM、增强状态和电话服务。您可以指导用户进入其移动电话的应用程序市场来安装 Microsoft Lync 2010 Mobile。有关详细信息，请参阅 Lync Server 2010 文档中的“规划移动客户端”，网址为 <http://go.microsoft.com/fwlink/?linkid=235955>。

  - **Lync Phone Edition**   用于智能 IP 电话（例如，通过 USB 连接的电话）的 Lync Phone Edition 软件尚未针对 Lync Server 2013 更新。 Lync Phone Edition 在发出和接收呼叫、增强状态和会议的客户端音频功能等方面继续得到支持。

  - **Lync 2010 Attendant**    Microsoft Lync 2010 Attendant 是集成式呼叫管理程序，前台接待员可利用它通过快速呼叫处理、IM 和屏幕上路由同时管理多个对话。

## 另请参阅

#### 概念

[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)

