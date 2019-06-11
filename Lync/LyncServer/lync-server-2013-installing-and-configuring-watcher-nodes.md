---
title: 'Lync Server 2013: 安装和配置观察程序节点'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>在 Lync Server 2013 中安装和配置观察程序节点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-07_

*观察程序节点*是定期运行 Lync Server 合成事务的计算机。 *合成事务*是验证关键最终用户方案 (如登录系统或交换即时消息的功能) 的 Windows PowerShell cmdlet 是否按预期工作。 对于 Lync Server 2013, System Center Operations Manager 可以运行下表中所示的合成事务。 表中显示三种不同的合成事务类型:

  - **默认值**。 这些是观察程序节点默认将运行的合成事务。 当创建新的观察程序节点时, 可以选择指定节点将运行的合成事务。 (这是**CsWatcherNodeConfiguration** cmdlet 使用的测试参数的用途。)如果在创建观察程序节点时未使用 "测试" 参数, 则它将自动运行所有默认的合成事务, 并且不会运行任何非默认的合成事务。 例如, 这意味着观察程序节点将配置为运行 CsAddressBookService 测试, 但不会配置为运行测试 CsExumConnectivity 测试。

  - **非默认值**。 顾名思义, 非默认合成事务是测试观察程序节点是否默认不运行。 但是, 可以启用观察程序节点来运行任何非默认的合成事务。 你可以在创建观察程序节点时执行此操作 (使用**CsWatcherNodeConfiguration** cmdlet), 或者在此后的任何时间执行此操作。 许多非默认的合成事务都需要额外的设置步骤。 有关详细信息, 请参阅[Lync Server 2013 中的综合事务的特殊设置说明](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。

  - **扩展**。 扩展测试是一种特殊类型的非默认综合事务。 与其他合成事务不同, 扩展测试可以在每次传递期间运行多次。 这在验证一个池的多个公共交换电话网络 (PSTN) 语音路由等行为时非常有用。 只需将一个扩展测试的多个实例添加到观察程序节点即可配置此操作。

有关将其他合成事务添加到观察程序节点的过程的详细信息, 请参阅[在 Lync Server 2013 中管理观察程序节点](lync-server-2013-managing-watcher-nodes.md)。 你可以使用 Lync Server Management Shell 从观察程序节点中删除合成事务。

可用于观察程序节点的综合事务包括：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet 名称（测试名称）</th>
<th>描述</th>
<th>综合交易记录类型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>确认用户能够查找不在其联系人列表中的用户。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>确认用户能够通过 HTTP 查找不在联系人列表中的用户。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>确认用户能够发送对等即时消息。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>确认用户能够发出对等音频呼叫（仅信号）。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>确认用户能够查看其他用户的状态。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>确认用户可以登录 Lync。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>不与 Lync Server 2013 的本地版本一起使用</p></td>
<td><p>可扩展</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>确认用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。</p></td>
<td><p>非默认, 扩展</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>确认用户能够创建和参与音频/视频会议。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>确认 A/V 边缘服务器能够接受对等呼叫和电话会议的连接。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>确认用户可以参与数据协作会议 (包括活动 (如白板和投票) 的联机会议。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>确认用户可以连接到 Exchange 统一消息 (UM)。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>确认用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>确认用户能够通过 web 地址链接创建和加入计划会议。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>确认移动设备用户能够注册和发送即时消息。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>确认用户可使用持久聊天服务交换消息。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>确认可通过统一的联系人存储库访问用户的联系人。 "统一联系人存储" 为用户提供了一种维护单个联系人集的方式, 可使用 Lync 2013、Outlook 和/或 Outlook Web Access 进行访问。</p></td>
<td><p>非默认值</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>确认即时消息可以通过 XMPP (可扩展消息和状态协议) 网关发送。</p></td>
<td><p>非默认值</p></td>
</tr>
</tbody>
</table>


无需安装观察程序节点即可使用 System Center Operations Manager。 如果不安装这些节点, 则仍可在出现问题时从 Lync Server 2013 组件获取实时警报。 (组件和用户管理包不使用观察程序节点。)但是, 如果你希望通过使用活动的监视管理包监视端到端方案, 则需要观察程序节点。

<div>


> [!NOTE]  
> 管理员还可以手动运行综合事务, 而无需使用或安装 Operations Manager。 有关各种 Test-Cs cmdlet 的详细信息, 请参阅<A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlet 索引</A>。



</div>

综合事务可能会占用大量计算机内存和处理器时间, 具体取决于你的部署的大小。 因此, 我们建议你将专用计算机用作观察程序节点。 例如, 不应将前端服务器配置为充当观察程序节点。 观察程序节点应满足下列硬件规范:

<div>


> [!NOTE]  
> 旧版 Microsoft Lync Server 2010 观察程序节点不能与 Lync Server 2013 观察程序节点在同一台计算机上 collocated。 这是因为 Lync Server 2010 和 Lync Server 2013 的核心系统文件不能安装在同一台计算机上。<BR>但是, Lync Server 2013 观察程序节点可以同时监视 Lync Server 2013 和 Lync Server 2010。 这两个产品版本均支持默认的合成事务。



</div>

Lync Server 2013 观察程序节点可以部署在企业内部或外部, 以帮助验证:

  - <span></span>  
    至企业内部用户的池的连接。

  - <span></span>  
    通过外围网络连接到在企业外部工作的远程用户的连接。

  - <span></span>  
    至分支机构装置的连接。

  - <span></span>  
    在企业内和通过外围网络连接到 Lync Server 2010。

在企业内部和外部提供不同的身份验证选项, 可帮助简化管理。 有关详细信息, 请参阅[在 Lync Server 2013 中配置观察程序节点以运行合成事务](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。

若要将计算机配置为充当观察程序节点, 必须在安装 System Center Operations Manager 并导入 Lync Server 2013 管理包之后完成以下步骤。

在安装 Lync Server 2013 core 文件和 System Center agent 文件之前, 还应确保观察程序节点计算机满足安装 Lync Server 2013 的所有先决条件。 此外, 观察程序节点计算机还应安装下列项目:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>最低要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>以下两种之一：</p>
<ul>
<li><p>64 位处理器、四核、2.33 GHz 或更快</p></li>
<li><p>64 位 2 路处理器、双核、2.33 GHz 或更快</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>网络操作系统</p></td>
<td><ul>
<li><p>1个网络适配器 1 Gbps</p></li>
<li><p>Windows Server 2008 R2、Windows Server 2012 或</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - .NET Framework 4.5 的完整版本。

  - Windows Identity Foundation。

  - Windows PowerShell 3.0。

一旦满足所有这些先决条件, 您就可以通过以下方式配置观察程序节点:

  - 在观察程序节点计算机上安装 Lync Server 2013 core 文件。

  - 在观察程序节点计算机上安装 System Center Operations Manager 代理。

  - 运行 Watchernode 可执行文件。

  - 使用**CsWatcherNodeConfiguration** cmdlet 配置要由观察程序节点使用的测试用户。

</div>

<span> </span>

</div>

</div>

</div>

