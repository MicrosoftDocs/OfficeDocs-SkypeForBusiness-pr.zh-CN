---
title: Lync Server 2013：直接 SIP 部署选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的直接 SIP 部署选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

本主题提供了部署直接 SIP 连接的示例拓扑。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server 独立版

如果你的组织使用本部分中介绍的部署之一, 则可以使用 Lync Server 2013 作为组织的部分或全部的唯一电话服务解决方案。 本部分详细介绍以下部署:

  - **增量部署:** 此选项假设你有现有的专用分支 exchange (PBX) 基础结构, 并且想要将企业语音增量引入组织内较小的组或团队。

  - **Lync Server VoIP-仅限 VoIP 部署:** 此选项假设你正在考虑在没有传统的电话基础结构的网站上部署企业语音。

<div>

## <a name="incremental-deployment"></a>增量部署

在增量部署中, Lync Server 2013 是单个团队或部门的唯一电话服务解决方案, 而组织中的其他用户仍在使用 PBX。 此增量部署策略提供了一种通过受控试点计划在企业中引入 IP 电话的方法。 Microsoft 统一通信最适合使用其通信需求的工作组被移动到企业语音, 而其他用户则保留在现有 PBX 上。 可根据需要将其他工作组迁移到企业语音。

如果明确定义的用户组具有共同的通信要求, 并且该用户组适用于集中管理, 则建议使用 "增量" 选项。 如果你有团队或部门分布在地理区域上方, 而您的长途费用成本可能很大, 此选项也很有效。 实际上, 此选项对于创建其成员可能分散在全球各地的虚拟团队非常有用。 你可以创建、修改或解散此类团队, 以便快速响应对业务需求的变化。

下图显示了用于在 PBX 背后部署企业语音的一般拓扑。 这是增量部署的推荐拓扑。

**增量部署选项**

![部门迁移选项图表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部门迁移选项图表")

<div>


> [!NOTE]  
> 如果您将 Lync Server 部署连接到认证的直接 SIP 合作伙伴, 则不需要在中介服务器和 PBX 之间使用公共交换式电话网络 (PSTN) 网关。 有关认证直接 SIP 合作伙伴的列表, 请参阅 Microsoft 统一通信打开互操作性计划网站<A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>。



</div>

<div>


> [!NOTE]  
> 此图所示的媒体路径启用了媒体旁路 (推荐配置)。 如果选择禁用 "绕过媒体", 则媒体路径将通过中介服务器进行路由。



</div>

在此拓扑中, 将为企业语音启用选定的部门或工作组。 PSTN 网关将启用了 Internet 协议 (VoIP) 的工作组的语音链接到 PBX。 已启用企业语音的用户 (包括远程工作人员) 通过 IP 网络进行通信。 通过企业语音用户呼叫 PSTN 和未启用企业语音的同事将路由到相应的 PSTN 网关。 来自仍在 PBX 系统或来自 PSTN 的呼叫者的同事的呼叫将路由到 PSTN 网关, 该网关会将呼叫转发到 Lync 服务器进行路由。

有两种推荐配置, 可用于将企业语音连接到现有 PBX 基础结构以实现互操作: 在 PBX 前面的 PBX 和企业语音背后的企业语音。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX 背后的企业语音

当企业语音部署在 PBX 背后时, PSTN 的所有调用都将到达 PBX, 它将呼叫企业语音用户到 PSTN 网关, 并与 pbx 用户通话。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 前面的企业语音

如果在 PBX 前面部署了企业语音, 所有通话都将进入 PSTN 网关, 该网关会将企业语音用户的呼叫路由到 Lync Server, 并将 PBX 用户与 PBX 通话。 从企业语音和 PBX 用户到 PSTN 的通话均通过 IP 网络路由到最经济高效的 PSTN 网关。 下表显示了此配置的优点和缺点。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>在 PBX 前面部署企业语音的优点和缺点

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>最终</th>
<th>一些</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX 仍可为未启用企业语音的用户提供服务。</p></td>
<td><p>现有网关可能不支持所需的功能或容量。</p></td>
</tr>
<tr class="even">
<td><p>PBX 处理所有较早的设备。</p></td>
<td><p>需要从 PBX 到 PBX 以及从网关到中介服务器的网关之间的主干。 您可能需要来自服务提供商的更多中继。</p></td>
</tr>
<tr class="odd">
<td><p>企业语音用户保持相同的电话号码。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server 仅 VoIP 部署

企业语音为现有企业提供新的企业和新的 office 网站, 从而实现了一个功能完备的 VoIP 解决方案, 而无需担心 PBX 集成或导致真正的部署和维护。IP PBX 基础结构的成本。 此解决方案支持现场和远程工作人员。

在此部署中, 所有通话都通过 IP 网络进行路由。 对 PSTN 的调用将路由到相应的 PSTN 网关。 Lync 2013 或 Lync Phone Edition 用作 softphone。 远程呼叫控制不可用, 因为没有可供用户控制的 PBX 手机。 通过 Exchange 统一消息 (UM) 的可选部署提供语音邮件和自动助理服务。

<div>


> [!NOTE]  
> 除了支持 Lync Server 2013 所需的网络基础结构之外, 仅有 VoIP 的部署可以使用小型的合格网关来支持传真机和模拟设备。



</div>

下图显示了仅限 VoIP 的部署的典型拓扑。

**仅限 VoIP 的部署选项**

![Greenfidle 部署选项](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署选项")

<div>


> [!NOTE]  
> 此图所示的媒体路径启用了媒体旁路 (推荐配置)。 如果选择禁用 "绕过媒体", 则媒体路径将通过中介服务器进行路由。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

