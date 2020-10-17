---
title: Lync Server 2013：为 VDI 准备环境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bf8480a0905184d7259a9f0c3aa79725453f59d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506799"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>为 VDI 准备 Lync Server 2013 环境

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

若要为 Lync VDI 插件准备环境，管理员必须执行以下步骤。

1.  在 Lync Server 2013 中，确保所有 VDI 用户的 EnableMediaRedirection 设置为 TRUE。 有关详细信息，请参阅 [set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 和 [Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。

2.  在数据中心计算机上，在所有虚拟机上安装 Lync 2013 客户端。

3.  在本地计算机上，安装 Lync VDI 插件。

</div>

<span> </span>

</div>

</div>

</div>

