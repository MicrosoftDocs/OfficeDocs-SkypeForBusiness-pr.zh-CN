---
title: Lync Server 2013：移动的证书要求
TOCTitle: 移动的证书要求
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690044(v=OCS.15)
ms:contentKeyID: 49314050
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中移动的证书要求

 

_**上一次修改主题：** 2015-03-09_

如果您部署移动功能并支持移动客户端的自动发现，则您需要在证书上包含某些使用者替代名称条目，以支持来自移动客户端的安全连接。

您需要在以下证书上包含使用者替代名称条目以实现自动发现：

  - 控制器池

  - 前端池

  - 反向代理

本节介绍了实现自动发现所需的证书上的使用者替代名称条目。

> [!NOTE]  
> 使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但向反向代理所使用的公共证书中添加多个使用者替代名称条目的成本很高。如果您具有多个 SIP 域（这会导致添加使用者替代名称的成本很高），则您可将反向代理配置为对初始自动发现服务请求使用 HTTP，而不是使用 HTTPS（默认配置）。有关详细信息，请参阅 <a href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中的移动性技术要求</a>。



### 控制器池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscover.&lt;sip 域&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 或者，您可以使用 SAN=*.&lt;sipdomain&gt;



### 前端池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscover.&lt;sip 域&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 或者，您可以使用 SAN=*.&lt;sipdomain&gt;



### 反向代理（公共 CA）证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscover.&lt;sip 域&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 将此 SAN 分配给为反向代理上的 SSL 侦听器分配的证书。



> [!NOTE]  
> 您的反向代理侦听器将具有外部 Web 服务 URL（例如，如果已部署可选的 控制器，则 SAN=lyncwebextpool01.contoso.com 和 dirwebexternal.contoso.com）的使用者替代名称。


