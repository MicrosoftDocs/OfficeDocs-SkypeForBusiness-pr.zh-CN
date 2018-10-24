---
title: 备份和还原要求：数据
TOCTitle: 备份和还原要求：数据
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202194(v=OCS.15)
ms:contentKeyID: 52061167
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份和还原要求：数据

 

_**上一次修改主题：** 2016-12-08_

Lync Server 使用数据库中存储的设置和配置信息以及数据库和文件存储中存储的数据。本主题介绍为了能够在贵组织遇到故障或中断时还原服务而需要备份的数据，还标识了 Lync Server 使用的需要单独备份的数据和组件。

## 设置和配置要求

本主题包括用于备份和还原恢复 Lync Server 服务所需的设置和配置信息的过程。此配置信息位于中央管理存储或其他后端数据库或 Standard Edition Server 中。

下表标识需要备份和还原的设置和配置信息。

### 设置和配置数据

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>数据类型</th>
<th>存储位置</th>
<th>描述/备份时间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓扑配置信息</p></td>
<td><p>中央管理存储（数据库：Xds.mdf）</p></td>
<td><p>拓扑、策略和配置设置。</p>
<p>在使用 Lync Server 控制面板或 cmdlet 修改配置或策略后使用常规备份进行备份。</p></td>
</tr>
<tr class="even">
<td><p>位置信息</p></td>
<td><p>中央管理存储（数据库：Lis.mdf）</p></td>
<td><p>企业语音增强 9-1-1 (E9-1-1) 配置信息。此信息通常是静态的。</p>
<p>使用常规备份进行备份。</p></td>
</tr>
<tr class="odd">
<td><p>响应组配置信息</p></td>
<td><p>后端服务器或 Standard Edition Server（数据库：RgsConfig.mdf）</p></td>
<td><p>响应组代理组、队列和工作流。</p>
<p>在添加或更改代理组、队列或工作流之后使用常规备份进行备份。</p></td>
</tr>
</tbody>
</table>


## 数据要求

下面是为了能够在出现故障时还原 Lync Server 服务而需要备份的 Lync Server 数据的列表。

请注意，某些类型的数据不需要进行恢复。本主题不包含备份这些类型的数据的过程，其中包括以下数据：

  - 临时用户数据，如终结点和订阅、活动会议服务器和临时会议状态（数据库：RtcDyn.mdf）

  - 通讯簿数据（数据库：Rtcab.mdf 和 Rtcab1.mdf）。通讯簿数据库是从 Active Directory 域服务中自动重新生成的。

  - 呼叫寄存应用程序的动态信息（数据库：CpsDyn.mdf）

  - 临时响应组数据，如代理登录状态和呼叫等待信息（数据库：RgsDyn.mdf）

  - 持久聊天的合规性数据库（数据库：MgcComp.mdf）。如果您已启用持久聊天合规性，则只要您将适配器配置为读取数据库中的信息将其转换为备用格式，持久聊天合规性数据库中的信息就是临时的。因此将认为持久聊天的合规性数据库是临时的。
    
    Lync Server 2013 持久聊天服务器附带一个 XML 适配器。您还可以安装使用此数据并将其移动到其他源（如承载 Exchange 的存档）的自定义适配器。

下表标识需要备份和还原的数据。

### 数据库中存储的数据

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>数据类型</th>
<th>存储位置</th>
<th>描述/备份时间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>永久用户数据</p></td>
<td><p>后端服务器或 Standard Edition Server（数据库：RTCXDS.mdf）</p></td>
<td><p>用户权限、用户联系人列表、服务器或池数据、计划内会议等。此用户数据不包含上载到会议的内容。</p>
<p>使用常规备份进行备份。此信息是动态的，但如果需要还原到最新常规备份，则丢失更新对 Lync Server 而言并不是灾难性的。如果联系人列表对您的组织十分重要，可以更频繁地备份此数据。</p></td>
</tr>
<tr class="even">
<td><p>存档数据</p></td>
<td><p>存档数据库（数据库：LcsLog.mdf）</p>
<p>如果您已启用 Microsoft Exchange 集成选项，则此数据可能存储在 Exchange 2013 上。否则，此数据将保存在 Lync Server 存档数据库中，该数据库可能与其他 Lync Server 数据库并置，或者在单独的数据库服务器上是独立的。</p></td>
<td><p>即时消息 (IM) 和会议内容。</p>
<p>此数据对 Lync Server 并不重要，但出于管理目的，它可能对您的组织十分重要。请据此确定您的备份计划。</p>
<p>对于存档数据库，Lync Server 仅支持简单恢复模式。使用简单恢复模式，数据库将恢复到上次完整备份点，这意味着，您无法将数据库还原到故障点或特定时间点。</p></td>
</tr>
<tr class="odd">
<td><p>监控数据</p></td>
<td><p>监控数据库（LcsCDR.mdf 和 QoeMetrics.mdf）</p>
<p>这些数据库可能与其他 Lync Server 数据库并置，或者在单独的数据库服务器上是独立的。</p></td>
<td><p>呼叫详细信息记录 (LcsCDR.mdf) 和体验质量 (QoE) 指标 (QoeMetrics.mdf)。</p>
<p>呼叫详细信息记录是动态的，可能对您的业务十分重要。请在确定备份计划时考虑是否会出于管理原因需要这些记录。</p>
<p>用户体验质量信息是动态的。丢失 QoE 数据对 Lync Server 的操作并不十分重要，但它可能对您的业务十分重要。请根据此信息对您的组织的重要程度来确定备份计划。</p>
<p>对于监控数据库，Lync Server 仅支持简单恢复模式。使用简单恢复模式，数据库将恢复到上次完整备份点，这意味着，您无法将数据库还原到故障点或特定时间点。</p></td>
</tr>
<tr class="even">
<td><p>持久聊天数据</p></td>
<td><p>持久聊天数据库 (mgd.mdf)。</p>
<p>此数据库可能与其他 Lync Server 数据库并置，或者在单独的数据库服务器上是独立的。</p></td>
<td><p>持久聊天数据是聊天室中发布的实际聊天内容。此数据通常是业务关键的。</p>
<p>您可以选择使用 SQL Server 备份，或者使用 Lync Server 中提供的 <strong>Export-CsPersistentChatData</strong> cmdlet 导出数据库。若要恢复数据，您可以将数据库导入并还原到上次完整备份点，这意味着您无法将数据库还原到故障点。</p></td>
</tr>
</tbody>
</table>


## 文件存储数据要求

在 企业版 部署中，Lync Server 文件存储通常位于文件服务器上。在 标准版 部署中，Lync Server 文件存储默认位于 Standard Edition Server 上。通常，存在一个对网站共享的 Lync Server 文件存储。持久聊天文件存储与 Lync Server 文件存储使用相同的文件共享。

文件存储位置被标识为 \\\\server\\share name。若要查找您的文件存储的特定位置，请打开拓扑生成器，然后在“文件存储”节点中查看。

下表标识需要备份和还原的文件存储。

### 文件存储

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>数据类型</th>
<th>存储位置</th>
<th>描述/备份时间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 文件存储</p></td>
<td><p>通常在文件服务器、文件群集或 Standard Edition Server 中</p></td>
<td><p>会议内容，会议内容元数据，会议合规性日志，应用程序数据文件，设备更新的更新文件，响应组、呼叫寄存和通知应用程序的音频文件，以及发布到持久聊天室中的文件。</p>
<p>使用常规备份进行备份。</p></td>
</tr>
</tbody>
</table>


## 其他备份要求

为确保您能够在发生故障时还原 Lync Server 服务，您必须备份一些并非 Lync Server 本身的一部分的必要组件。以下组件不会作为本文档中介绍的 Lync Server 备份和还原过程的一部分进行备份或还原：

  - **Active Directory 域服务**   您需要在备份 Lync Server 的同时使用 Active Directory 工具备份 AD DS。应使 AD DS 与 Lync Server 保持同步，以避免在 Lync Server 需要的联系对象与 AD DS 中的不匹配时可能出现的问题，这一点十分重要。AD DS 存储 Lync Server 使用的以下设置：
    
      - 用户 SIP URI 和其他用户设置。
    
      - 应用程序（如响应组和会议助理）的联系对象。
    
      - 中央管理存储的指针。
    
      - Kerberos 身份验证帐户（可选的计算机对象）和 Lync Server 安全组。
    
    有关在 Windows Server 2008 中备份和还原 AD DS 的详细信息，请参阅 <http://go.microsoft.com/fwlink/?linkid=209105> 上的“AD DS 备份和恢复分步指南”。

  - **证书颁发机构和证书**   使用贵组织用于备份证书颁发机构 (CA) 和证书的策略。如果使用可导出私钥，则可备份证书和私钥，然后导出它们（如果使用本文档中的过程来还原 Lync Server）。如果使用内部 CA，则可在需要还原 Lync Server 时重新注册。请妥善保管私钥，以便在计算机出现故障时使用，这一点十分重要。

  - **System Center Operations Manager**   如果使用 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager）监控 Lync Server 部署，则可在监控 Lync Server 的同时备份它创建的数据（可选）。请使用标准 SQL Server 备份过程来备份 System Center Operations Manager 文件。在恢复过程中，不会还原这些文件。

  - **公用电话交换网 (PSTN) 网关配置**   如果使用企业语音或 Survivable Branch Appliance，则需要备份 PSTN 网关配置。有关备份和还原 PSTN 网关配置的详细信息，请咨询您的供应商。

  - **Lync Server 或 Office Communications Server 的共存版本**   如果您的 Lync Server 2013 部署与 Lync Server 2010 或早期版本的 Office Communications Server 共存，则无法使用本文档中的过程来备份或还原早期版本。相反，您必须使用专门为您的早期版本记录的备份和还原过程。有关备份和还原 Lync Server 2010 的详细信息，请参阅 <http://go.microsoft.com/fwlink/?linkid=265417>。有关备份和还原 Microsoft Office Communications Server 2007 R2 的详细信息，请参阅 <http://go.microsoft.com/fwlink/?linkid=168162>。

  - **基础结构信息**   您需要备份有关您的基础结构的信息，如防火墙配置、负载平衡配置、Internet Information Services (IIS) 配置、域名系统 (DNS) 记录和 IP 地址，以及动态主机配置协议 (DHCP) 配置。有关备份这些组件的详细信息，请咨询其各自的供应商。

  - **Microsoft Exchange 和 Exchange 统一消息 (UM)**   备份和还原 Microsoft Exchange 和 Exchange UM，如 Microsoft Exchange 文档中所述。有关备份和还原 Exchange Server 2013 的详细信息，请参阅 <http://go.microsoft.com/fwlink/?linkid=285384>。有关备份和还原 Exchange Server 2010 的详细信息，请参阅 <http://go.microsoft.com/fwlink/?linkid=209179>。
    
    请注意，Lync Server 2013 引入了将用户联系人列表、高清晰度的用户照片以及存档数据存储在 Exchange 2013 中的功能。请参阅下表了解如何备份这些类型的数据：
    
      - **高清晰度照片**作为 Exchange Server 备份的一部分进行备份。
    
      - **统一联系人存储**是在 Lync Server 2013 中引入的。统一联系人存储使用户能够将其所有联系人信息保存在 Exchange 2013 中。
        
        您应根据用户的用户联系人是存储在统一联系人存储还是 Lync 后端服务器上，来确保用户备份是最新的。以下方案显示了从哪些位置将用户联系人迁移到统一联系人存储可能会导致备份和还原过程中的问题。
        
        **方案 1：** 用户联系人已迁移到统一联系人存储，且在迁移用户联系人之前从发生的 Lync Server 备份中执行了还原。在此方案中，用户的过时联系人的状态将最多保持一天时间，直到 Lync Server 迁移任务开始将用户联系人迁移到 Exchange。（请注意，因为用户联系人之前已迁移到统一联系人存储，所以将使用 Exchange 联系人信息。）此方案中不需要任何管理员干预。
        
        **方案 2：** 用户联系人之前存储在统一联系人存储中，但稍后进行了回滚。当用户联系人存储在统一联系人存储中时从 Lync Server 备份中执行了还原。在此方案中，客户端或 Lyss 服务器日志中的错误消息 `Error: Incorrect Exchange Version` 可能会将此指示为问题。用户将能够在 Lync 2013 中直接从 Exchange 访问其联系人列表，但客户端的状态将无法与 Lync Server 状态相匹配。若要修复此问题，管理员将需要为受影响的用户运行 **Invoke-CsUCSRollback** cmdlet。
    
      - **存档数据**可以存储在 Exchange 2013 中。此数据对 Lync Server 并不重要，但出于管理目的，它可能对您的组织十分重要。如果存档数据存储在 Exchange 中且对您的组织十分重要，则遵循 Exchange 备份和还原过程。请注意，存储在 Exchange 中的存档数据无法移回 Lync Server。此外，无法将已存储在 Lync 存档数据库中的数据移动到 Exchange。

