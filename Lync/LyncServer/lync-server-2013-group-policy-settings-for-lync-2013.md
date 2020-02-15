---
title: Lync Server 2013： Lync 2013 的组策略设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba88fdce88280597e9e621c13267de2b9b76d0fb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的组策略设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

在早期版本的 Lync 和 Office Communicator 中，独立的 Communicator 管理模板可用于配置客户端组策略设置。 对于 Lync 2013，新的管理模板文件（admx 和 adml 文件）与 Office 组策略管理模板一起包含在一起。 Lync 2013 admx 和. adml 文件的可用性允许您下载模板并集中管理所有 Office 程序和语言包的组策略设置。 有关详细信息，请参阅 Office 2013 文档中的 "Office 2013 管理模板文件（ADMX、ADML） <http://go.microsoft.com/fwlink/p/?linkid=267516>"。

<div>

## <a name="client-bootstrapping-policies"></a>客户端引导策略

在用户首次登录到服务器之前，应该配置几个客户端引导策略。 由于这些策略在客户端登录并开始接收带内设置前生效，因此您可以使用组策略配置它们。 有关详细信息，请参阅部署文档中的在[Lync Server 2013 中配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

