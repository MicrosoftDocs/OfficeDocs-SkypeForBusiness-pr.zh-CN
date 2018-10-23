---
title: Lync Server 2013：集成统一消息的功能
TOCTitle: 集成统一消息和 Lync Server 的功能
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398144(v=OCS.15)
ms:contentKeyID: 49311934
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成统一消息和 Lync Server 2013 的功能

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013企业语音使用 Exchange 统一消息 (UM) 基础结构来提供呼叫应答、呼叫通知、语音访问（包括语音邮件）和自动助理服务。

## 呼叫应答

呼叫应答是指代表呼叫未应答或忙碌的用户接收语音消息。它包括播放个人问候语、录制消息以及提交消息进行排队以传送到用户的邮箱，该邮箱存储在 Exchange 邮箱服务器上。

如果呼叫者有留言，该留言将路由到用户的收件箱中。如果呼叫者未留言，则将在用户的邮箱中存储一条未接来电通知。然后，用户可以使用 Microsoft Outlook 消息和协作客户端、Outlook Web Access、Exchange ActiveSync 技术或 Outlook Voice Access 来访问其收件箱。可以像显示电子邮件的主题和优先级一样显示呼叫的主题和优先级。

## Outlook Voice Access

使用 Outlook Voice Access， 企业语音用户通过电话界面不仅可以访问语音邮件，还可以访问 Exchange 收件箱（包括电子邮件、日历和联系人）。订阅者访问号码由 Exchange UM 管理员分配。

## 自动助理

自动助理是 Exchange UM 的一项功能，可用于配置供外部用户与公司代表联系所拨打的电话号码。尤其是，它可以提供一系列语音提示来帮助外部呼叫者导航菜单系统。可用选项的列表由 Exchange UM 管理员在 Exchange UM 服务器上配置。

## 传真服务

Exchange UM 提供了可以让用户在 Exchange 邮箱中接收传入传真的传真功能。有关详细信息，请参阅 Microsoft Exchange Server 文档中的“统一消息”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)。

> [!NOTE]  
> 由 Exchange UM 服务器提供的传真服务在与 Microsoft Exchange Server 2010、具有最新 Service Pack 的 Exchange 2010 或 Exchange 2013 集成的 Lync Server 部署中不可用。


