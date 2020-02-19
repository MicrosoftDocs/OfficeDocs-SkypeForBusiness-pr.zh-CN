---
title: Lync Server 2013：决定如何部署 Microsoft Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f1869cce980f8eb530e1541bd64ead3a7b4258
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>确定如何部署 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

在规划 Lync 时，第一个主要决策是如何部署 Microsoft Lync：在本地使用 Lync Server 2013，或在云中使用 Microsoft Office 365 的 Lync Online。

  - **Lync Server 2013 本地**版：此选择提供完整的 Lync 功能集，并在配置、自定义和操作部署方面提供了极大的灵活性。 所有服务器都是现场安装的，并且由您的组织进行维护。 本地部署提供了所有的 Lync Server 功能。

  - **云中的 Lync Online**Lync Online 专为希望提供基于云的即时消息、状态和会议的成本和灵活性优势而不牺牲 Lync Server 的业务类功能的组织而设计。 借助 Lync Online，Microsoft 将部署和维护所需的服务器基础结构，并处理日常维护、修补程序和升级。 本地部署中提供的某些功能在 Lync Online 中不可用。

最适合您的部署类型取决于您要部署的工作负载，以及您组织的地理位置和业务状态。

<div>

## <a name="lync-server"></a>Lync Server

本地 Lync Server 部署最适合以下方案：

  - **完整的企业语音功能**   如果您计划部署完整的企业语音解决方案以替换 PBX 或使用高级呼叫功能，则需要本地 Lync Server 部署。 本地部署支持与 PBX 系统和中继的直接连接以及高级电话功能（如响应组和呼叫寄存）。 Lync Online 目前不支持这些功能。

  - **媒体质量控制**   如果您希望完全范围的媒体质量保证功能（如呼叫允许控制（CAC）和服务质量（QoS）功能），您需要本地部署。

  - **持久聊天**   如果需要为您的组织部署持久聊天，则必须选择本地部署。

  - **第三方服务器应用程序**   仅本地部署可以与使用 Microsoft 统一通信托管 API （UCMA）的受信任的第三方应用程序一起使用。

  - **需要区域支持**   的多国家/地区公司如果您有多个国家或地区的数据中心，并且需要在区域的基础上部署和管理服务器，则本地部署是最佳的，因为它提供了这种类型的区域管理功能。

  - **对策略、报告和升级**   的完全控制在本地 Lync Server 部署中，您可以访问一组完整的服务器和客户端策略、监视和其他报告以及升级的时间。 Lync Online 提供了策略设置和报告的子集，并提供了用于接受升级的有限但有效的窗口。

</div>

<div>

## <a name="lync-online"></a>Lync Online

如果以上列表中的所有因素对您都不重要，您可能需要选择 Lync Online 来实现更简单的部署和管理。 Lync Online 提供了强健的 IM、状态和会议功能集，还允许在组织中的用户之间通过 IP 进行语音和视频呼叫。

</div>

</div>

<span> </span>

</div>

</div>

</div>

