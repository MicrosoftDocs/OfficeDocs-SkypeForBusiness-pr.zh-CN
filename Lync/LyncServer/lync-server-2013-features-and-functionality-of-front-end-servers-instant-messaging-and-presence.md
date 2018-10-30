---
title: Lync Server 2013：前端服务器、即时消息和状态的功能
TOCTitle: 前端服务器、即时消息和状态的功能
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398109(v=OCS.15)
ms:contentKeyID: 49311877
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中前端服务器、即时消息和状态的功能

 

_**上一次修改主题：** 2013-03-17_

前端服务器提供大多数 Lync Server 功能。有两个版本可用： Lync Server Enterprise Edition，主要设计用于大型组织；和 Lync Server Standard Edition，主要设计用于需要较小硬件投资并且不需要高可用性的小型组织。两个版本都支持所有 Lync Server 工作负载，包括 IM、状态、会议和企业语音。

通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。支持双方和多方之间的 IM 会话。双方 IM 对话中的一方可以随时将第三方参与者加入对话中。发生这种情况时，对话窗口会做出相应改变以支持会议功能。

> [!IMPORTANT]
> 一对一通信中涉及的 Lync 和 Communicator 客户端通常称为对等客户端。从技术上来说，两个客户端在一对一对话中使用即时消息多点控制单元 (IMMCU) 进行通信。IMMCU 是 前端服务器 的一个组件。将 IMMCU 放在所需的通信工作流中允许进行呼叫详细信息记录和 前端服务器 启用的其他功能。通信从客户端上的动态源端口发送到 前端服务器 端口 TLS/TCP/5061（假设使用推荐的传输层安全性）。根据设计，只有当 Lync Server 和 IMMCU 处于活动状态且可用时，才可能实现对等通信（以及多方 IM）。


*状态* 向用户提供网络中其他人的状态信息。用户的状态所提供的信息有助于其他人决定是否应尝试与该用户联系，以及使用即时消息、电话还是电子邮件。只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。此状态在 Lync 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术、Microsoft Word 团队服务、门户服务器或服务以及 Microsoft Excel 电子表格软件）中显示为状态图标。状态图标表明用户当前是否有空以及是否愿意进行交流。

