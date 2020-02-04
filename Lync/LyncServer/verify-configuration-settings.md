---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fcb7f577719ad14a04c89250bfab66e6cc9de3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>验证配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-06_

你可以通过在中央管理存储所在的内部计算机上运行 Lync Server 2013 cmdlet，或在已加入的任何加入了 Lync Server 2013 核心组件（OcsCore）的计算机上运行 Lync Server **CsManagementStoreReplicationStatus** cmdlet 来验证配置信息到边缘服务器的复制。

初始结果可能表明状态为 "False"，而不是 "True" 用于复制。 如果是这样，请运行**CsManagementStoreReplication** cmdlet 并等待复制完成，然后再再次运行**Get CsManagementStoreReplicationStatus** 。

</div>

<span> </span>

</div>

</div>

</div>

