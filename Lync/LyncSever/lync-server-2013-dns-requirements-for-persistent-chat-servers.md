---
title: 持久聊天服务器的 DNS 要求
TOCTitle: 持久聊天服务器的 DNS 要求
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205391(v=OCS.15)
ms:contentKeyID: 49314775
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 持久聊天服务器的 DNS 要求

 

_**上一次修改主题：** 2015-03-09_

本节介绍部署持久聊天服务器所需的域名系统 (DNS) 记录。

## 持久聊天服务器的 DNS 记录

下表指定持久聊天服务器部署的 DNS 要求。

### 持久聊天服务器的 DNS 要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署方案</th>
<th>DNS 要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>一台持久聊天服务器</p></td>
<td><p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p></td>
</tr>
<tr class="even">
<td><p>持久聊天池</p></td>
<td><p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p>
<p><strong>示例</strong></p>
<p>PersistentChatServer01.contoso.com     10.10.10.1</p>
<p>PersistentChatServer02.contoso.com     10.10.10.2</p>
<p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p>
<p><strong>示例</strong></p>
<p>PersistentChatPool.contoso.com    10.10.10.1</p>
<p>PersistentChatPool.contoso.com    10.10.10.2</p></td>
</tr>
</tbody>
</table>

