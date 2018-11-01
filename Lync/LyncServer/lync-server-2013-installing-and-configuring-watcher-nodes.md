---
title: 安装和配置观察程序节点
TOCTitle: 安装和配置观察程序节点
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204943(v=OCS.15)
ms:contentKeyID: 49313018
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装和配置观察程序节点

 

_**上一次修改主题：** 2015-03-09_

*观察程序节点* 是定期运行 Lync Server 综合事务的计算机。*综合事务* 是验证关键的最终用户方案（如登录系统的功能、或交换即时消息的功能）是否如期运行的 Windows PowerShell cmdlet。对于 Lync Server 2013，System Center Operations Manager 可运行下表中显示的综合事务。下表中显示了三种不同的综合事务类型：

  - **Default**。这些是默认情况下观察程序节点将运行的综合事务。创建新的观察程序节点时，您将具有指定此节点将运行的综合事务的选项。（这是 **New-CsWatcherNodeConfiguration** cmdlet 使用的 Tests 参数的目的。）如果您在创建观察程序节点时未使用 Tests 参数，则将自动运行所有默认综合事务并且不会运行任何非默认综合事务。这意味着，例如，观察程序节点将配置为运行 Test-CsAddressBookService 测试，但不会配置为运行 Test-CsExumConnectivity 测试。

  - **Non-default**。顾名思义，非默认综合事务是默认情况下观察程序节点不会运行的测试。但是，可启用观察程序节点运行任何非默认综合事务。您可在创建观察程序节点时或在创建后的任何时间执行此操作（使用 **New-CsWatcherNodeConfiguration** cmdlet）。许多非默认综合事务需要额外的设置步骤。有关详细信息，请参阅[综合事务的特殊设置说明](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。

  - **Extended**。扩展测试是特殊类型的非默认综合事务。与其他综合事务不同，扩展测试可在每次通过的情况下运行多次。这在验证一个池的多个公用电话交换网 (PSTN) 语音路由等行为时十分有用。此类测试可通过向观察程序节点添加多个扩展测试的实例来配置。

有关向观察程序节点添加其他综合事务的过程的详细信息，请参阅[管理观察程序节点](lync-server-2013-managing-watcher-nodes.md)。您可使用 Lync Server 命令行管理程序删除观察程序节点中的综合事务。

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
<th>综合事务类型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>确保用户能够查找不在其联系人列表内的用户。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>确保用户能够通过 HTTP 查找不在其联系人列表内的用户。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>确保用户能够发送对等即时消息。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>确保用户能够发出对等音频呼叫（仅信号）。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>确保用户能够查看其他用户的状态。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>确保用户能够登录 Lync。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>不能与本地版本的 Lync Server 2013 一起使用</p></td>
<td><p>扩展</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>确保用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。</p></td>
<td><p>非默认，扩展</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>确保用户能够创建和参与音频/视频会议。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>确保 A/V 边缘服务器能够接受对等呼叫和会议呼叫的连接。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>确保用户可参与数据协作会议（包含白板和投票等活动的联机会议）。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>确保用户可连接到 Exchange 统一消息 (UM)。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>确保用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。</p></td>
<td><p>默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>确保用户能够创建会议并能通过 Web 地址链接加入计划的会议。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>确保移动设备用户能够注册和发送即时消息。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>确保用户可使用持久聊天服务交换消息。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>确保可通过统一的联系人存储库访问用户的联系人。用户可利用统一的联系人存储库这种方式保留可使用 Lync 2013、Outlook 和/或 Outlook Web Access 访问的一组联系人。</p></td>
<td><p>非默认</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>确保可通过 XMPP（可扩展消息传递和状态协议）网关发送即时消息。</p></td>
<td><p>非默认</p></td>
</tr>
</tbody>
</table>


若要使用 System Center Operations Manager，您不必安装观察程序节点。如果您未安装这些节点，则仍可在事件发生时通过 Lync Server 2013 组件获取实时通知。（组件和用户管理包不会使用观察程序节点。）但是，如果要使用主动监控管理包监控端到端的方案，则需要观察程序节点。

> [!NOTE]  
> 管理员还可手动运行综合事务，无需使用或安装 Operations Manager。有关各种 Test-Cs cmdlet 的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps">Lync Server 2013 Cmdlet 索引</a>。



综合事务可能使用大量计算机内存和处理器时间，具体取决于您的部署规模。为此，建议您使用专用计算机作为观察程序节点。例如，您不应配置前端服务器充当观察程序节点。观察程序节点应符合以下硬件规格：

> [!NOTE]  
> 无法在带有 Lync Server 2013 观察程序节点的同一计算机上并置旧的 Microsoft Lync Server 2010 观察程序节点。这是因为 Lync Server 2010 和 Lync Server 2013 的核心系统文件无法安装在同一计算机上。<br />
但是，Lync Server 2013 观察程序节点可同时监控 Lync Server 2013 和 Lync Server 2010。这两个产品版本上均支持默认的综合事务。



可在企业的内部或外部部署 Lync Server 2013 观察程序节点以帮助验证：

   至企业内部用户的池的连接。

   通过在企业外部工作的远程用户的外围网络的连接。

   至分支机构装置的连接。

   至企业内部和通过外围网络的 Lync Server 2010 的连接。

企业内部和企业外部有不同的身份验证选项可用以帮助管理。有关详细信息，请参阅[将观察程序节点配置为运行综合事务](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。

若要配置计算机充当观察程序节点，您必须在安装 System Center Operations Manager 和导入 Lync Server 2013 管理包后完成下列步骤。

安装 Lync Server 2013 核心文件和 System Center 代理文件之前，您还应确保观察程序节点计算机满足安装 Lync Server 2013 的所有先决条件。此外，观察程序节点计算机还应安装下列项：


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
<li><p>1 个网络适配器 1 Gbps</p></li>
<li><p>Windows Server 2008 R2、Windows Server 2012 或</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - 完整版的 .NET Framework 4.5。

  - Windows Identity Foundation。

  - Windows PowerShell 3.0。

只要满足所有这些先决条件，就能通过下列方式配置观察程序节点：

  - 在观察程序节点计算机上安装 Lync Server 2013 核心文件。

  - 在观察程序节点计算机上安装 System Center Operations Manager 代理。

  - 运行 Watchernode.msi 可执行文件。

  - 使用 **CsWatcherNodeConfiguration** cmdlet 配置观察程序节点要使用的测试用户。

