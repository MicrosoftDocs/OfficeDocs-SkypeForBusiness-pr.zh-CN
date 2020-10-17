---
title: Lync Server 2013：核心基础结构的最佳做法
description: Lync Server 2013：核心基础结构的最佳做法。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ea7cb9c7685a3b6f7c04146ec5631bbac10fe6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552188"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Lync Server 2013 中核心基础结构的最佳做法

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-01-27_

您可能已经着手设计系统容错能力了，做法有：确保硬件冗余，防止断电，例行安装安全更新和防病毒措施，以及监控服务器活动等。 这些做法不仅受益于 Microsoft Lync Server 2013 基础结构，还受益于整个网络。 如果尚未实施这些做法，我们建议您在部署 Lync Server 2013 之前执行此操作。

为了帮助保护 Lync Server 2013 部署中的服务器，避免因意外或故意损害可能导致停机的情况，请采取以下预防措施：

  - 使用安全更新使服务器保持最新状态。 订阅 Microsoft 安全性通知服务有助于确保您收到任何 Microsoft 产品的安全公告发布的最新通知。 若要订阅，请访问 Microsoft 技术安全通知网站，网址为 [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) 。

  - 确保正确设置访问权限。

  - 将服务器部署在可防止未授权访问的物理环境中。确保在所有服务器上安装适当的防病毒软件。使用最新的病毒特征文件使软件保持最新。使用防病毒应用程序的自动更新功能使病毒特征保持最新。

  - 建议您在安装 Lync Server 2013 的计算机上禁用不需要的 Windows Server 操作系统服务。

  - 除非可以确保实现连续完整的服务器控制、完全物理隔离以及正确安全地停用更换的或有故障的磁盘驱动器，否则使用全卷加密系统对操作系统和存储数据的磁盘驱动器加密。

  - 除非可以确保严格控制对服务器的物理访问，否则禁用服务器的所有外部直接内存访问 (DMA) 端口。 可以轻松发起的基于 DMA 的攻击可能会公开非常敏感的信息，例如加密私钥。

</div>

<span> </span>

</div>

</div>

</div>

