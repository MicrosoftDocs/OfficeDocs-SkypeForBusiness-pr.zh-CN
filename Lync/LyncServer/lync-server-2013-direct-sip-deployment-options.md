---
title: Lync Server 2013：直接 SIP 部署选项
description: Lync Server 2013：直接 SIP 部署选项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afe361a5522ee4869bbdb572e5016437d5580d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568238"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的直接 SIP 部署选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

本主题提供了部署直接 SIP 连接的示例拓扑。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server Stand-Alone

如果您的组织使用本节中介绍的某个部署，则可以使用 Lync Server 2013 作为组织的部分或全部的唯一电话解决方案。 本部分详细介绍了以下部署：

  - **增量部署：** 此选项假设您有一个现有的专用分支 exchange (PBX) 基础结构，您打算将企业语音增量引入组织内较小的组或团队。

  - **Lync Server 仅限 VoIP 部署：** 此选项假定您正在考虑在没有传统电话基础结构的站点上部署企业语音。

<div>

## <a name="incremental-deployment"></a>增量部署

在增量部署中，Lync Server 2013 是单个团队或部门的唯一电话解决方案，而组织中的其他用户仍在使用 PBX。 此增量部署策略提供了一种通过受控制的试点计划将 IP 电话引入到企业中的方法。 Microsoft 统一通信最能满足其通信需求的工作组将移动到企业语音，而其他用户则仍保留在现有的 PBX 中。 根据需要，可以将其他工作组迁移到企业语音。

如果您明确定义了具有共同的通信要求并借给集中管理的用户组，则建议使用 "增量" 选项。 如果您的团队或部门分布在多个地理区域上，并且在长途费用中节省的成本很高，则此选项也很有效。 实际上，此选项对于创建可能分散在全球各地的成员的虚拟团队非常有用。 您可以创建、修改或 disband 此类团队，以快速响应移动的业务需求。

下图显示了用于在 PBX 背后部署企业语音的通用拓扑。 这是增量部署的推荐拓扑。

**增量部署选项**

![部门迁移选项关系图](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部门迁移选项关系图")

<div>


> [!NOTE]  
> 如果要将 Lync Server 部署连接到认证的直接 SIP 合作伙伴，则不需要在中介服务器和 PBX 之间建立公用电话交换电话网络 (PSTN) 网关。 有关认证的直接 SIP 合作伙伴的列表，请参阅 Microsoft 统一通信开放式互操作性计划网站，网址为 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> 。



</div>

<div>


> [!NOTE]  
> 此图中所示的媒体路径启用了媒体旁路 (建议的配置) 。 如果您选择禁用媒体旁路，媒体路径将通过中介服务器进行路由。



</div>

在此拓扑中，已为企业语音启用所选部门或工作组。 PSTN 网关将 (VoIP) 的工作组中的语音 over Internet 协议链接到 PBX。 启用企业语音的用户（包括远程工作人员）在 IP 网络中进行通信。 由企业语音用户对 PSTN 和未启用企业语音的合作者的呼叫将路由到相应的 PSTN 网关。 来自位于 PBX 系统或来自 PSTN 上的呼叫者的同事的呼叫将路由到 PSTN 网关，PSTN 网关会将呼叫转发到 Lync Server 进行路由。

有两种建议的配置，用于将企业语音连接到现有的 PBX 基础结构以实现互操作性： pbx 和 Enterprise voice in PBX 前端的企业语音。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX 背后的企业语音

在 PBX 后面部署企业语音时，PSTN 中的所有呼叫都将到达 PBX，后者将呼叫企业语音用户的所有呼叫路由到 PSTN 网关，并向 PBX 呼叫 PBX 用户。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 前端的企业语音

在 PBX 前端部署企业语音时，所有呼叫都将到达 PSTN 网关，这会将企业语音用户的呼叫路由到 Lync Server，并呼叫 PBX 用户到 PBX。 从企业语音和 PBX 用户对 PSTN 的调用通过 IP 网络路由到最经济高效的 PSTN 网关。 下表显示了此配置的优点和缺点。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>在 PBX 前端部署企业语音的优点和缺点

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>优点</th>
<th>缺点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX 仍可为未启用企业语音的用户提供服务。</p></td>
<td><p>现有网关可能不支持所需的功能或容量。</p></td>
</tr>
<tr class="even">
<td><p>PBX 处理所有早期的设备。</p></td>
<td><p>需要从网关到 PBX 以及从网关到中介服务器的中继。 您可能需要来自服务提供商的更多中继。</p></td>
</tr>
<tr class="odd">
<td><p>企业语音用户保留相同的电话号码。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server VoIP-Only 部署

企业语音为现有企业提供新的企业以及新的 office 网站，并有机会实施功能齐全的 VoIP 解决方案，而无需担心 PBX 集成或导致 IP PBX 基础结构的实际部署和维护成本。 此解决方案支持现场和远程工作人员。

在此部署中，所有呼叫都通过 IP 网络进行路由。 将对 PSTN 的呼叫路由到相应的 PSTN 网关。 Lync 2013 或 Lync Phone Edition 充当 softphone。 远程呼叫控制不可用且不必要，因为没有可供用户控制的 PBX 电话。 通过 Exchange 统一消息 (UM) 的可选部署，可以使用语音邮件和自动助理服务。

<div>


> [!NOTE]  
> 除了支持 Lync Server 2013 所需的网络基础结构之外，仅 VoIP 部署还可以使用小型的合格网关来支持传真机和模拟设备。



</div>

下图显示了仅限 VoIP 部署的典型拓扑。

**仅限 VoIP 的部署选项**

![Greenfidle 部署选项](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署选项")

<div>


> [!NOTE]  
> 此图中所示的媒体路径启用了媒体旁路 (建议的配置) 。 如果您选择禁用媒体旁路，媒体路径将通过中介服务器进行路由。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

