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
# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="14272-103">Lync Server 2013 中的企业语音的必备软件</span><span class="sxs-lookup"><span data-stu-id="14272-103">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14272-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="14272-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="14272-105">验证要在其中部署企业语音的基础结构是否满足以下软件先决条件：</span><span class="sxs-lookup"><span data-stu-id="14272-105">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="14272-106">在网络上安装并运行 Lync Server 2013 Standard Edition 或 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="14272-106">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="14272-107">所有边缘服务器都在外围网络中部署和运行，包括运行访问边缘服务的边缘服务器、A/V 边缘服务、Web 会议边缘服务和反向代理。</span><span class="sxs-lookup"><span data-stu-id="14272-107">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="14272-108">Microsoft Exchange Server 2007 Service Pack 3 (SP3) ，Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013 是将 Exchange 统一消息与 Lync Server 集成所必需的，并为 Lync 终结点提供丰富的通知和呼叫日志信息。</span><span class="sxs-lookup"><span data-stu-id="14272-108">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="14272-109">已为 Lync Server 创建并启用了一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="14272-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="14272-110">已成功部署 Lync 客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="14272-110">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="14272-111">拓扑生成器安装在网络上的服务器上。</span><span class="sxs-lookup"><span data-stu-id="14272-111">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="14272-112">后续步骤：验证安全性和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="14272-112">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="14272-113">验证企业语音的软件先决条件后，可以使用文档继续准备部署企业语音：</span><span class="sxs-lookup"><span data-stu-id="14272-113">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="14272-114">按照在 [Lync Server 2013 中的企业语音的安全性和配置先决条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述，验证安全性、用户配置和硬件 perquisites。</span><span class="sxs-lookup"><span data-stu-id="14272-114">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="14272-115">安装中介服务器，如在 [Lync server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)中所述，但 *仅* 当您要部署独立中介服务器或池时，因为在并置时，会将中介服务器作为前端池或 Standard Edition Server 部署过程的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="14272-115">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="14272-116">配置中继连接以提供用户的 PSTN 连接，如在 [Lync Server 2013 中配置中继中](lync-server-2013-configuring-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="14272-116">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

