---
title: 阻止与 Lync Server 的新连接进行服务器维护
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1881050e5226df9c36d3b92194e27e1123df13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513259"
---
# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>阻止与 Lync Server 2013 的新连接进行服务器维护

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

Lync Server 使您能够使服务器脱机 (例如，将软件或硬件升级) 应用，而不会丢失对用户的任何服务。

如果指定阻止对池中服务器的新连接或新呼叫的选项，则一旦实现此选项，服务器将停止接收任何新连接和呼叫。这些新的连接和呼叫将通过池中的其他服务器进行路由。阻止新连接的服务器允许其现有连接上的会话继续进行，直至会话自然结束。所有现有会话都结束后，即可将服务器置于脱机状态。

当您阻止与前端服务器的新连接时，某些 Lync Server 功能和服务会依赖于 DNS 负载平衡以确保其正常工作。 如果在池中没有使用 DNS 负载平衡，则服务器阻止新连接期间，通过这些服务的连接可能不会重新路由到其他服务器，因此将服务器置于脱机状态时，某些会话和呼叫可能会中断。 依赖 DNS 负载平衡以确保此选项正常运行的功能如下所示：

  - 助理版

  - 会议通知应用程序

  - 响应组应用程序

  - Announcement application － 通知应用程序

  - Call Park 应用程序

有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md) 。

除了阻止运行 Lync Server 的服务器上的所有服务的新连接之外，还可以阻止单独的 Lync Server 服务的新连接。 例如，在需要应用不要求整个服务器关闭的 Lync Server 更新的情况下，此方法非常有用。 请注意，阻止一项服务的连时，必须选择 Windows 服务列表中所属和显示的服务。 例如，Lync Server Front-End service 和用于监视的数据收集代理是单独的 Lync Server 服务，但在 Windows 服务列表中，它们将进行合并，并显示为 Lync Server 前端服务。 您可以阻止 Lync Server 前端服务的新连接，但不能单独阻止这两个单独的基础 Lync Server 服务的新连接。

<div>


> [!IMPORTANT]
> 如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>若要阻止与 Lync Server 的新连接，请执行以下操作：

1.  以 Administrators 组成员的身份登录到本地计算机。

2.  打开 "服务" 管理单元控制台：单击 " **开始**"，依次指向 " **所有程序**"、" **管理工具**"，然后单击 " **服务**"。

3.  在列表中，双击要阻止与其建立新连接的 Lync Server Windows 服务。

4.  在“属性”对话框的“服务状态: 已启动”**** 下，单击“暂停”****。

5.  或者，作为推荐选项，单击“启动类型”**** 旁边的“手动”****。
    
    <div>
    

    > [!IMPORTANT]
    > 如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。

    
    </div>

6.  完成后，单击“确定”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

