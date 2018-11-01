---
title: Lync Server 2013：DNS 摘要 - 反向代理
TOCTitle: DNS 摘要 - 反向代理
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204781(v=OCS.15)
ms:contentKeyID: 49312405
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DNS 摘要 - 反向代理

 

_**上一次修改主题：** 2015-03-09_

可以在反向代理中配置两个网络适配器，如下所示：

## 反向代理网络适配器要求

  - **网络适配器 1（内部接口）** 示例
    
    分配有 172.25.33.40 的内部接口。
    
    未定义默认网关。
    
    确保存在从包含反向代理内部接口的网络到任何包含 Lync Server  前端池服务器的网络的路由（例如，从 172.25.33.0 到 192.168.10.0）。

  - **网络适配器 2（外部接口）** 示例
    
    至少为此网络适配器分配了一个公用 IP 地址。
    
    定义网关以指向外围中的路由器或集成防火墙。（在方案示例中为 10.45.16.1）

### 反向代理所需的 DNS 记录

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN</th>
<th>IP 地址</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>来自内部部署的外部 Web 服务。可以为将使用此反向代理且已定义外部 Web 服务的任何 SIP 域的所有池和各个服务器定义和创建附加记录。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>您的部署中 控制器或 控制器池的外部 Web 服务。有多少不同的 控制器，您就可以定义多少 控制器，它们可能与其他 SIP 域关联。</p>
<div>

> [!IMPORTANT]
> 定义 控制器 的 DNS 记录并发布控制器不由前端池或 控制器决定。如果您使用的是 控制器，则必须定义并同时发布 控制器和 前端池外部 Web 服务。特定通信类型（用于身份验证和其他用途）将首先发送给 控制器（如果在拓扑中定义了它）。

</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>在外部发布的电话拨入式会议</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>在外部发布的会议</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>为 Office Web Apps Server 分配的侦听器</p></td>
<td><p>在内部或外围部署并发布用于外部客户端访问的 Office Web Apps Server</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>外部发布的自动发现的 Lync 发现外部记录，并包括移动性、 Microsoft Lync Web App 和计划程序 Web 应用程序</p></td>
</tr>
</tbody>
</table>

