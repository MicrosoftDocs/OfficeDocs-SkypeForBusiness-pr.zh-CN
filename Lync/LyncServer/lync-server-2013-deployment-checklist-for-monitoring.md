---
title: Lync Server 2013：监控的部署清单
TOCTitle: 监控的部署清单
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204874(v=OCS.15)
ms:contentKeyID: 49888414
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中监控的部署清单

 

_**上一次修改主题：** 2015-03-09_

虽然已在前端服务器上安装并启用了监视，但仍有一些步骤必须执行才能实际开始收集 Microsoft Lync Server 2013 的监视数据。以下清单中概述了这些步骤：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>阶段</p></td>
<td><p>步骤</p></td>
<td><p>角色和组成员身份</p></td>
<td><p>文档</p></td>
</tr>
<tr class="even">
<td><p><strong>安装必备硬件和软件</strong></p></td>
<td><p>在将充当要进行监视的后端数据存储的计算机上安装受支持版本的 Microsoft SQL Server。</p></td>
<td><p>还是本地管理员组的成员的域用户。</p></td>
<td><p>可支持性指南中的 <a href="lync-server-2013-supported-hardware.md">支持的适用于 Lync Server 2013 的硬件</a></p>
<p>可支持性指南中的 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的服务器软件和基础结构支持</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>创建相应的内部拓扑以支持监控</strong></p></td>
<td><p>使用 Lync Server 2013 拓扑生成器向拓扑添加监视数据库，然后发布已更新的拓扑。</p></td>
<td><p>若要定义拓扑，则为是本地用户组成员的用户。</p>
<p>若要发布拓扑，则为 Domain Administrators 组和 RTCUniversalServerAdmins 组的成员的用户。</p></td>
<td><p>部署指南中的 <a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">将监控存储与前端池关联</a></p></td>
</tr>
<tr class="even">
<td><p><strong>启用相应的监控设置</strong></p></td>
<td><p>启用全局和/或站点作用域的呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 监视。</p></td>
<td><p>为 RTCUniversalServerAdmins 组的用户，或分配有提供对 CsCdrConfiguration 和 CsQoEConfiguration cmdlet 的访问权限的 RBAC 角色的用户。</p></td>
<td><p>操作指南中的 <a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">配置呼叫详细信息记录和启用体验质量设置</a></p></td>
</tr>
</tbody>
</table>

