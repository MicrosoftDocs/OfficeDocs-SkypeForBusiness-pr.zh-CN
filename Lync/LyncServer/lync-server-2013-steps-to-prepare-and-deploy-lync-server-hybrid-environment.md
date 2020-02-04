---
title: Lync Server 2013：准备和部署 Lync Server 混合环境的步骤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>准备和部署 Lync Server 2013 混合环境的步骤

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-12-08_

下表列出了为具有 Skype for Business Online 和 Microsoft Office 365 的混合部署准备环境所需的步骤。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>已完成？</th>
<th>步骤</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>创建 Office 365 的租户帐户并启用 Lync Online</p></td>
<td><p>在<a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>中了解 office 365 和 Lync Online。</p>
<p>若要确保你的环境已准备好用于 Office 365，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=401408">系统要求</a>。</p>
<p>有关设置 Office 365 的详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 入门</a>和<a href="http://go.microsoft.com/fwlink/p/?linkid=254979">设置 office 365</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>添加域并验证所有权</p></td>
<td><p>您的域有时也称为 <em>虚域</em>。您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。这是为了确认您是域的所有者。</p>
<p>若要将域添加到 Office 365 租户，请按照<a href="https://go.microsoft.com/fwlink/p/?linkid=254983">将您的域添加到 office 365</a>中所述的步骤进行操作。</p>
<p>完成主题的每个部分中的所有步骤，包括&quot;编辑 Office 365 服务的 DNS 记录。&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>验证环境准备情况</p></td>
<td><p>您可以使用 Office 365 设置助理来帮助您部署 Office 365。 有关详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">使用设置助理确定 Office 365 准备情况</a>。</p>
<p>有关使用工具和部署 Office 365 的详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 部署指南</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>准备 Active Directory 同步</p></td>
<td><p>Active Directory 同步使你的本地 Active Directory 持续与 Office 365 保持同步。 这样，你可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。</p>
<div>

> [!IMPORTANT]  
> 您需要在本地和联机 Lync 部署之间同步组织中所有 Lync 用户的广告帐户，即使用户未移动到 Lync Online 也是如此。 如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。


</div>
<p>若要准备您的环境以进行 Active Directory 同步，请按照<a href="https://go.microsoft.com/fwlink/p/?linkid=254988">目录同步路线图</a>中所述的步骤进行操作，包括设置单一登录。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>为 Active Directory 联合身份验证服务（AD FS）创建证书</p></td>
<td><p>你将需要创建用于与 Office 365 的联合身份验证的证书。 有关详细信息，请参阅计划的计划和部署 AD FS 的 "联合身份验证服务器证书" 部分，以便与清单中的单一登录主题配合使用<a href="https://go.microsoft.com/fwlink/p/?linkid=285376">：使用 AD FS 实施和管理单一登录</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>为广告 FS 分配证书</p></td>
<td><p>创建用于与 Office 365 联合身份验证的证书后，必须安装和分配它们。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>将试点用户移动到 Skype for Business Online</p></td>
<td><p>完成准备和配置 Skype for business Online 环境的步骤后，您可以开始将试点用户移动到 Lync Online。</p>
<p>请参阅<a href="lync-server-2013-move-users-to-lync-online.md">在 Lync Server 2013 中将用户移动到 Lync Online</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>管理混合部署中的用户</p></td>
<td><p>有关如何在混合部署中管理用户的详细信息，请参阅<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">管理混合 Lync Server 2013 部署中的用户</a>。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

