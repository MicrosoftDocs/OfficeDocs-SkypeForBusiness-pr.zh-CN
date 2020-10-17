---
title: Lync Server 2013：企业语音的软件先决条件
description: Lync Server 2013：企业语音的软件先决条件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23d21f40e275431f0384448341aa25ecb628ebf9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558968"
---
# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企业语音的必备软件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

验证要在其中部署企业语音的基础结构是否满足以下软件先决条件：

  - 在网络上安装并运行 Lync Server 2013 Standard Edition 或 Enterprise Edition。

  - 所有边缘服务器都在外围网络中部署和运行，包括运行访问边缘服务的边缘服务器、A/V 边缘服务、Web 会议边缘服务和反向代理。

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3) ，Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013 是将 Exchange 统一消息与 Lync Server 集成所必需的，并为 Lync 终结点提供丰富的通知和呼叫日志信息。

  - 已为 Lync Server 创建并启用了一个或多个用户。

  - 已成功部署 Lync 客户端和设备。

  - 拓扑生成器安装在网络上的服务器上。

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>后续步骤：验证安全性和配置先决条件

验证企业语音的软件先决条件后，可以使用文档继续准备部署企业语音：

1.  按照在 [Lync Server 2013 中的企业语音的安全性和配置先决条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述，验证安全性、用户配置和硬件 perquisites。

2.  安装中介服务器，如在 [Lync server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)中所述，但 *仅* 当您要部署独立中介服务器或池时，因为在并置时，会将中介服务器作为前端池或 Standard Edition Server 部署过程的一部分安装。

3.  配置中继连接以提供用户的 PSTN 连接，如在 [Lync Server 2013 中配置中继中](lync-server-2013-configuring-trunks.md)所述。

</div>

</div>

<span> </span>

</div>

</div>

</div>

