---
title: 迁移中介服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3478bb3bb837e44ed33597f72738b181b4c67561
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>迁移中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

当运行 "合并向导" 时，中介服务器将合并到 Lync Server 2013 试点拓扑中。 但是，你可以配置 Lync Server 2013 中介服务器，因为 Office 通信服务器 2007 R2 池无法与 Lync server 2013 中介服务器通信，因此在迁移所有用户后。 在并行迁移期间，Lync Server 2013 池与 Office 通信服务器 2007 R2 中介服务器通信。

当您配置 Lync Server 2013 中介服务器时，您还必须升级或替换您的 Office 通信服务器 2007 R2 网关。 Office 通信服务器 2007 R2 网关不支持 Lync Server 2013 中介服务器。 你需要部署已认证的适用于 Lync Server 2013 的网关，并将其与 Lync Server 2013 中介服务器相关联。 必须先执行此步骤，然后才能完全停止 Office 通信服务器 2007 R2 部署。

本部分中的主题介绍了在完成 Lync Server 2013 中介服务器的迁移后需要执行的配置任务。 将 collocated 中介服务器转换为独立的中介服务器是一种可选任务。

  - [配置中介服务器](configure-mediation-server.md)

  - [将语音路由更改为使用新的 Lync Server 2013 中介服务器](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [将 collocated 中介服务器转换为独立的中介服务器（可选）](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

