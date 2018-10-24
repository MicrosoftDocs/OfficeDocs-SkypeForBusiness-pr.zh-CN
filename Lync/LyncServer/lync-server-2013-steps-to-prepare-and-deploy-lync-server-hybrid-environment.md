---
title: Lync Server 2013：准备和部署 Lync Server 混合环境的步骤
TOCTitle: 准备和部署 Lync Server 2013 混合环境的步骤
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205157(v=OCS.15)
ms:contentKeyID: 49313830
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 准备和部署 Lync Server 2013 混合环境的步骤

 

_**上一次修改主题：** 2016-12-08_

下表列出准备环境以利用 Microsoft Lync Online 和 Microsoft Office 365 实现混合部署所必需的步骤。


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
<td><p></p></td>
<td><p>创建 Office 365 租户帐户并启用 Lync Online</p></td>
<td><p>通过 <a href="http://go.microsoft.com/fwlink/?linkid=254980">Office 365</a> 了解 Office 365 和 Lync Online。</p>
<p>若要确保您的环境满足 Office 365 要求，请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=401408">系统要求</a>。</p>
<p>有关设置 Office 365 的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/?linkid=254982">Office 365 入门</a>和 <a href="http://go.microsoft.com/fwlink/?linkid=254979">设置 Office 365</a>。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>添加域并验证所有权</p></td>
<td><p>您的域有时也称为 <em>虚域</em> 。您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。这是为了确认您是域的所有者。</p>
<p>若要将您的域添加到您的 Office 365 租户中，请按照 <a href="http://go.microsoft.com/fwlink/?linkid=254983">将域添加到 Office 365 中</a>中所述的步骤操作。</p>
<p>完成主题各节中的所有步骤，包括“编辑 Office 365 服务的 DNS 记录”。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>确认环境准备就绪</p></td>
<td><p>您可以使用 Office 365 设置助理帮助部署 Office 365。有关详细信息，请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=254985">使用设置助理确定 Office 365 准备情况</a>。</p>
<p>有关使用该工具和部署 Office 365 的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 部署指南</a>。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>准备 Active Directory 同步</p></td>
<td><p>Active Directory 同步使您的内部部署 Active Directory 与 Office 365 保持连续同步。这样，您可以创建每个用户帐户和组的同步版本，同时实现从您的本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。</p>
<div>

> [!IMPORTANT]
> 您需要在本地 Lync 部署与联机 Lync 部署之间同步组织内所有 Lync 用户的 AD 帐户，即便用户未迁移到 Lync Online 也是如此。如果未能同步所有用户，组织内本地用户与联机用户之间的通信将出现问题。

</div>
<p>若要准备您的环境以进行 Active Directory 同步，请按照 <a href="http://go.microsoft.com/fwlink/?linkid=254988">Active Directory 同步：路线图</a>中所述的步骤（包括设置单一登录）操作。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>为 Active Directory 联合身份验证服务 (AD FS) 创建证书</p></td>
<td><p>您需要创建用于与 Office 365 建立联合身份验证的证书。有关详细信息，请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=285376">核对清单：使用 AD FS 实施和管理单一登录</a>的“规划和部署 AD FS 以用于单一登录”主题中的“联合服务器证书”一节。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>为 AD FS 分配证书</p></td>
<td><p>创建用于与 Office 365 建立联合身份验证的证书后，必须安装和分配它们。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>将试用用户移至 Skype for Business Online</p></td>
<td><p>完成为 Skype for Business Online 准备和配置环境的步骤后，您可以开始将试用用户移至 Lync Online。</p>
<p>请参阅 <a href="lync-server-2013-move-users-to-lync-online.md">在 Lync Server 2013 中将用户移至 Lync Online</a>。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>管理混合部署中的用户</p></td>
<td><p>有关如何管理混合部署中的用户的详细信息，请参阅 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">管理混合 Lync Server 2013 部署中的用户</a>。</p></td>
</tr>
</tbody>
</table>

