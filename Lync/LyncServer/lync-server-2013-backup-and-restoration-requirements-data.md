---
title: Lync Server 2013：备份和还原要求：数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8431e16e976f0ad189205f0c42c04d50e6936e90
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527039"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Lync Server 2013 中的备份和还原要求： data

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-26_

Lync Server 使用存储在数据库中的设置和配置信息，以及存储在数据库和文件存储中的数据。 本主题介绍在您的组织遇到故障或中断时，需要备份以恢复服务的数据，同时还标识了需要单独备份的 Lync Server 所使用的数据和组件。

<div>

## <a name="settings-and-configuration-requirements"></a>设置和配置要求

本主题包括备份和还原 Lync Server 服务恢复所需的设置和配置信息的过程。 配置信息位于中央管理存储或其他后端数据库或 Standard Edition 服务器上。

下表列出了备份和还原所需的设置和配置信息。

### <a name="settings-and-configuration-data"></a>设置和配置数据

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
<th>Description/何时备份</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓扑配置信息</p></td>
<td><p>中央管理存储 (数据库： Xds) </p></td>
<td><p>拓扑、策略和配置设置。</p>
<p>备份常规备份，并在使用 Lync Server 控制面板或 cmdlet 修改配置或策略之后。</p></td>
</tr>
<tr class="even">
<td><p>位置信息</p></td>
<td><p>中央管理存储 (数据库： .Lis) </p></td>
<td><p>企业语音增强型 9-1-1 (E9-1-1) 配置信息。 此信息通常是静态的。</p>
<p>使用常规备份进行备份。</p></td>
</tr>
<tr class="odd">
<td><p>响应组配置信息</p></td>
<td><p>后端服务器或 Standard Edition Server (数据库： RgsConfig) </p></td>
<td><p>响应组代理组、队列和工作流。</p>
<p>备份常规备份以及添加或更改代理组、队列或工作流之后。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>数据要求

下面列出了需要备份的 Lync Server 数据，以便在发生故障时可以还原 Lync Server 服务。

请注意，恢复时不需要某些类型的数据。 本主题不包含用于备份这些类型数据的过程，其中包括以下内容：

  - 临时用户数据，例如终结点和订阅、活动会议服务器和临时会议状态 (数据库： RtcDyn) 

  - 通讯簿数据 (数据库： Rtcab 和 Rtcab1) 。 通讯簿数据库将自动从 Active Directory 域服务中重新生成。

  -  (数据库： CpsDyn) 的呼叫寄存应用程序的动态信息

  - 临时响应组数据，如代理登录状态和呼叫等待信息 (数据库： RgsDyn) 

  - 持久聊天 (数据库： MgcComp) 的合规性数据库。 如果启用了持久聊天合规性，则在将适配器配置为从数据库读取信息并将其转换为备用格式后，持久聊天合规性数据库中的信息将是瞬态的。 因此，持久聊天的合规性数据库被认为是暂时性的。
    
    Lync Server 2013 持久聊天服务器附带有一个 XML 适配器。 您还可以安装接受此数据的自定义适配器并将其移动到其他源，如 Exchange 托管的存档。

下表标识了需要备份和还原的数据。

### <a name="data-stored-in-databases"></a>存储在数据库中的数据

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
<th>Description/何时备份</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>持久性用户数据</p></td>
<td><p>后端服务器或 Standard Edition Server (数据库： RTCXDS) </p></td>
<td><p>用户权限、用户联系人列表、服务器或池数据、安排的会议等等。 此用户数据不包括上载到会议的内容。</p>
<p>使用常规备份进行备份。 此信息是动态的，但是，如果需要还原到上一次常规备份，则更新丢失不会严重到 Lync Server。 如果 "联系人" 列表对您的组织至关重要，您可以更频繁地备份此数据。</p></td>
</tr>
<tr class="even">
<td><p>存档数据</p></td>
<td><p> (数据库的存档数据库： LcsLog) </p>
<p>如果已启用 Microsoft Exchange 集成选项，则此数据可能存储在 Exchange 2013 上。 否则，此数据将保留在 Lync Server 存档数据库中，该数据库可能与另一个 Lync Server 数据库并置，也可能独立于单独的数据库服务器。</p></td>
<td><p>即时消息 (IM) 和会议内容。</p>
<p>此数据对 Lync Server 来说并不重要，但对您的组织而言可能是管理法规的关键。 相应地确定备份计划。</p></td>
</tr>
<tr class="odd">
<td><p>监视数据</p></td>
<td><p>监视数据库 (LcsCDR 和 QoeMetrics) </p>
<p>这些数据库可以与其他 Lync Server 数据库并置，也可以独立在单独的数据库服务器上。</p></td>
<td><p> (LcsCDR) 和经验质量 (QoE) 指标 (QoeMetrics) 中的呼叫详细记录。</p>
<p>呼叫详细信息记录是动态的，可能对您的业务至关重要。 通过考虑是否出于合规性原因需要这些记录来确定备份计划。</p>
<p>体验质量信息是动态的。 QoE 数据丢失对 Lync Server 的操作并不重要，但对你的业务来说可能至关重要。 根据此信息对组织的重要性确定备份日程安排。</p></td>
</tr>
<tr class="even">
<td><p>持久聊天数据</p></td>
<td><p>持久聊天数据库 (托管) 。</p>
<p>此数据库可以与其他 Lync Server 数据库并置，也可以独立在单独的数据库服务器上。</p></td>
<td><p>持久聊天数据是在聊天室中发布的实际聊天内容。 此数据通常是关键业务。</p>
<p>您可以选择使用 SQL Server 备份，也可以使用 Lync Server 中提供的 <strong>export-cspersistentchatdata</strong> cmdlet 导出数据库。 若要恢复数据，可以导入数据库并将其还原到上次完整备份的点，这意味着无法将数据库还原到故障点。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>文件存储数据要求

在企业版部署中，Lync Server 文件存储通常位于文件服务器上。 在标准版部署中，默认情况下，Lync Server 文件存储位于 Standard Edition 服务器上。 通常情况下，为一个站点共享一个 Lync Server 文件存储。 持久聊天文件存储使用与 Lync Server 文件存储相同的文件共享。

文件存储位置标识为 \\ \\ 服务器 \\ 共享名称。 若要查找文件存储区的特定位置，请打开拓扑生成器并查看 " **文件存储** " 节点。

下表标识了需要备份和还原的文件存储区。

### <a name="file-stores"></a>文件存储

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
<th>Description/何时备份</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 文件存储</p></td>
<td><p>通常在文件服务器、文件群集或 Standard Edition 服务器上</p></td>
<td><p>会议内容、会议内容元数据、会议合规性日志、应用程序数据文件、设备更新的更新文件、响应组的音频文件、呼叫寄存以及通知应用程序，以及发布到持久聊天室中的文件。</p>
<p>使用常规备份进行备份。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>其他备份要求

为了帮助确保在发生故障时还原 Lync Server 服务的能力，您必须备份某些不属于 Lync Server 本身的必要组件。 以下组件不会作为本文档中所述的 Lync Server 备份和还原过程的一部分进行备份或还原：

  - **Active Directory 域服务**    您需要在备份 Lync Server 时使用 Active Directory 工具备份 AD DS。 务必将 AD DS 与 Lync Server 保持同步，以避免在 Lync Server 预期与 AD DS 中的联系人对象不匹配时可能出现的问题。 AD DS 存储 Lync Server 使用的以下设置：
    
      - 用户 SIP URI 和其他用户设置。
    
      - 响应组和会议助理等应用程序的 Contact 对象。
    
      - 指向中央管理存储的指针。
    
      - Kerberos 身份验证帐户 (可选的 computer 对象) 和 Lync Server 安全组。
    
    有关在 Windows Server 2008 中备份和还原 AD DS 的详细信息，请参阅 "AD DS 备份和恢复分步指南"，网址为 [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) 。

  - **证书颁发机构和证书**    使用您的组织的策略来备份证书颁发机构 (CA) 和证书。 如果使用可导出私钥，则可以备份证书和私钥，如果使用本文档中的过程还原 Lync Server，则可以对其进行导出。 如果您使用内部 CA，如果需要还原 Lync Server，则可以重新注册。 在计算机出现故障时将私钥保存在安全位置，这一点很重要。

  - **System Center Operations Manager**    如果使用 Microsoft System Center Operations Manager (以前的 Microsoft Operations Manager) 监视 Lync Server 部署，则可以选择在监视 Lync Server 时备份所创建的数据。 使用您的标准 SQL Server 备份过程来备份 System Center Operations Manager 文件。 恢复过程中不会还原这些文件。

  - **公开交换电话网络 (PSTN) 网关配置**    如果使用企业语音或 Survivable 分支设备，则需要备份 PSTN 网关配置。 有关备份和还原 PSTN 网关配置的详细信息，请参阅你的供应商。

  - **Lync server 或 Office 通信服务器**     的版本共存如果您的 Lync Server 2013 部署 coexists 使用 Lync Server 2010 或早期版本的 Office 通信服务器，则不能使用本文档中的过程来备份或还原早期版本。 相反，您必须使用专为早期版本记录的备份和还原过程。 有关备份和还原 Lync Server 2010 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) 。 有关备份和还原 Microsoft Office 通信服务器 2007 R2 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) 。

  - **基础结构信息**    您需要备份有关您的基础结构的信息，例如防火墙配置、负载平衡配置、Internet 信息服务 (IIS) 配置、域名系统 (DNS) 记录和 IP 地址，以及动态主机配置协议 (DHCP) 配置。 有关备份这些组件的详细信息，请咨询其各自的供应商。

  - **Microsoft exchange 和 Exchange 统一消息 (UM) **    备份和还原 Microsoft Exchange 和 Exchange UM，如 Microsoft Exchange 文档中所述。 有关备份和还原 Exchange Server 2013 的详细信息，请参阅 [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) 。 有关备份和还原 Exchange Server 2010 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) 。
    
    请注意，Lync Server 2013 引入了将用户联系人列表、高清晰度用户照片和存档数据存储在 Exchange 2013 中的功能。 若要了解如何备份这些类型的数据，请参阅下面的列表：
    
      - 将**高清晰度照片**作为 Exchange Server 备份的一部分进行备份。
    
      - Lync Server 2013 中引入了**统一的联系人存储库**。 统一联系人存储使用户能够将其所有联系人信息保留在 Exchange 2013 中。
        
        您应确保在用户的联系人存储在统一的联系人存储区中或在 Lync 后端服务器上，备份是最新的。 以下方案说明将用户联系人迁移到统一联系人存储区的位置可能会导致备份和还原过程中出现问题。
        
        **方案1：** 用户联系人将迁移到统一的联系人存储库，并从迁移用户联系人之前执行的 Lync Server 备份中执行还原。 在这种情况下，用户将有一个过期的联系人状态为一天，直到 Lync Server 迁移任务开始将用户联系人迁移到 Exchange。  (请注意，由于之前的用户联系人已迁移到统一联系人存储，因此将使用) 的 Exchange 联系人信息。 此方案中不需要管理员干预。
        
        **方案2：** 用户联系人以前存储在统一的联系人存储区中，但随后会回退。 当用户联系人存储在统一的联系人存储库中时，将从执行的 Lync Server 备份执行还原。 在这种情况下， `Error: Incorrect Exchange Version` 在客户端或 Lyss 服务器日志中的一条错误消息可能表明这是一个问题。 用户将能够直接从 Exchange 访问 Lync 2013 中的联系人列表，但客户端的状态将与 Lync Server 的状态不匹配。 若要解决此问题，管理员需要对受影响的用户运行 **invoke-csucsrollback** cmdlet。
    
      - **存档数据** 可以存储在 Exchange 2013 中。 此数据对 Lync Server 来说并不重要，但对您的组织而言可能是管理法规的关键。 如果存档数据存储在 Exchange 中并且对您的组织至关重要，请遵循 Exchange 备份和还原过程。 请注意，存储在 Exchange 中的存档数据不能移回到 Lync Server。 此外，无法将已存储在 Lync 存档数据库中的数据移动到 Exchange。

</div>

</div>

<span> </span>

</div>

</div>

</div>

