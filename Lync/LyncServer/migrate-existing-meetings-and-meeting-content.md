---
title: 迁移现有会议和会议内容
TOCTitle: 迁移现有会议和会议内容
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49888360
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移现有会议和会议内容

 

_**上一次修改主题：** 2013-02-22_

当用户帐户从 Lync Server 2010 移至 Lync Server 2013 服务器时，以下信息将随该用户帐户一起移动：

  - **用户已安排的会议**。这包括移动会议目录和会议数据。

  - **用户的个人标识号 (PIN)**。用户的当前 PIN 在到期或用户请求新 PIN 之前仍然有效。

以下用户帐户信息不会移至新服务器。

  - **会议内容**。若要移动在会议期间共享的内容（例如 PowerPoint、白板、附件或投票数据），请使用 **-MoveConferenceData** 参数作为 **Move-CsUser** cmdlet 的一部分。

