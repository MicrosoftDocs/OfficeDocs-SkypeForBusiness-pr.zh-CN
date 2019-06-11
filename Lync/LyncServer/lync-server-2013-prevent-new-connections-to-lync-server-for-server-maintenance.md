---
title: 阻止与 Lync Server 的新连接进行服务器维护
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>阻止与 Lync Server 2013 的新连接进行服务器维护

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

Lync Server 使你能够使服务器脱机 (例如, 应用软件或硬件升级), 而不会对用户造成任何服务损失。

当你指定用于阻止新连接或呼叫池中的服务器的选项时, 一旦你执行此选项, 它将停止进行任何新的连接和调用。 这些新连接和呼叫通过池中的其他服务器路由。 阻止新连接的服务器允许现有连接上的会话继续运行, 直到它们自然结束。 当所有现有会话都已结束时, 服务器可以脱机使用。

当你阻止与前端服务器的新连接时, 某些 Lync Server 功能和服务依赖于 DNS 负载平衡来确保它正常工作。 如果你未在池上使用 DNS 负载平衡, 则通过这些服务的连接可能无法在服务器阻止新连接期间重新路由到其他服务器, 因此当服务器脱机时, 可能会中断. 依赖于 DNS 负载平衡以确保此选项正常运行的功能如下所示:

  - 助理

  - 会议通知应用程序

  - 响应组应用程序

  - 通知应用程序

  - 呼叫寄存应用程序

有关 DNS 负载平衡的详细信息, 请参阅规划文档中[Lync Server 2013 中的 "DNS 负载平衡](lync-server-2013-dns-load-balancing.md)"。

除了阻止运行 Lync Server 的服务器上的所有服务的新连接之外, 还可以阻止单个 Lync Server 服务的新连接。 例如, 此方法在你需要应用 Lync Server 更新 (不需要整个服务器关闭) 的情况下很有用。 请注意, 当你阻止一个服务的连接时, 你必须选择在服务的 Windows 列表中对其进行分组和显示的服务。 例如, Lync Server 前端服务和用于监视的数据收集代理是单独的 Lync Server 服务, 但在 Windows 服务列表中, 它们将被合并并显示为 Lync Server 前端服务。 你可以阻止 Lync Server 前端服务的新连接, 但不能单独阻止这两个单独的基础 Lync 服务器服务的新连接。

<div>


> [!IMPORTANT]
> 如果将服务器设置为阻止新连接, 然后重新启动服务器, 则默认情况下, 服务器将在启动后立即开始接受新连接。 若要防止这种情况, 请将服务器设置为仅在重新启动服务器之前暂停和手动恢复。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>若要阻止与 Lync Server 的新连接, 请执行以下操作:

1.  以 Administrators 组成员的身份登录本地计算机。

2.  打开 "服务" 管理单元控制台: 单击 "**开始**", 指向 "**所有程序**", 指向 "**管理工具**", 然后单击 "**服务**"。

3.  在列表中, 双击要阻止新连接的 Lync Server Windows 服务。

4.  在 "属性" 对话框中的 "**服务状态: 已开始**" 下, 单击 "**暂停**"。

5.  (可选, 但建议在 "**启动类型**" 旁边, 单击 "**手动**"。
    
    <div>
    

    > [!IMPORTANT]
    > 如果将服务器设置为阻止新连接, 然后重新启动服务器, 则默认情况下, 服务器将在启动后立即开始接受新连接。 若要防止这种情况, 请将服务器设置为仅在重新启动服务器之前暂停和手动恢复。

    
    </div>

6.  完成后，单击“确定”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

