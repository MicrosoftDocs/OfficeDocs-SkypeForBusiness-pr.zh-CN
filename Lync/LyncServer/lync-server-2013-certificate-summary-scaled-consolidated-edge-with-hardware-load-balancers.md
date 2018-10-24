---
title: Lync Server 2013：证书摘要 - 使用硬件负载平衡器的扩展的合并边缘
TOCTitle: 证书摘要 - 使用硬件负载平衡器的扩展的合并边缘
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398692(v=OCS.15)
ms:contentKeyID: 49313517
ms.date: 12/17/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的证书摘要 - 使用硬件负载平衡器的扩展的合并边缘

 

_**上一次修改主题：** 2016-12-15_

Microsoft Lync Server 2013 使用证书手动对其他服务器进行身份验证并对服务器到服务器与服务器到客户端的数据进行加密。证书要求与服务器关联的域名系统 (DNS) 记录和证书上的使用者名称 (SN) 和使用者替代名称 (SAN) 的名称匹配。若要成功映射服务器、DNS 记录和证书条目，您必须仔细规划服务器完全限定的域名，如 DNS 和证书的 SN 和 SAN 条目所注册的一样。

分配给 边缘服务器的外部接口的证书是从公共证书颁发机构 (CA) 请求的。下面的文章中列出了证明为 统一通信 提供证书成功的公共 CA： [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x804)。请求证书时，可使用 Lync Server 部署向导生成的证书请求或手动创建请求或通过公共 CA 提供的流程。分配证书时，证书将分配给 访问边缘服务接口、 Web 会议边缘服务 接口和音频/视频身份验证服务。音频/视频身份验证服务不应与不使用证书加密音频和视频流的 A/V 边缘服务混淆。内部 边缘服务器接口可使用内部（对您的组织而言）CA 提供的证书或公共 CA 提供的证书。内部接口证书仅使用 SN，无需或不会使用 SAN 条目。

> [!NOTE]  
> 下表显示使用者替代名称列表中的第二个 SIP 条目 (sip.fabrikam.com)，以供参考。对于组织中的每个 SIP 域，需要添加证书使用者替代名称列表中列出的对应 FQDN。



## 扩展的合并边缘（硬件负载已平衡）所需的证书


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>单一的合并 边缘服务器（外部边缘）</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>如果部署 AOL 的公共 IM 连接，则证书必须由公共 CA 提供，并且必须具有服务器 EKU 和客户端 EKU。此外，对于扩展的 边缘服务器，证书私钥必须可导出且必须将证书和私钥复制到每个 边缘服务器。证书将分配给以下组件的外部边缘接口：</p>
<ul>
<li><p>访问边缘服务</p></li>
<li><p>Web 会议边缘服务</p></li>
<li><p>A/V 边缘服务</p></li>
</ul>
<p>请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</p></td>
</tr>
<tr class="even">
<td><p>单一的合并 边缘服务器（内部边缘）</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>无需 SAN</p></td>
<td><p>证书可由公共或专用 CA 颁发，并且必须包含服务器 EKU。证书将分配给内部 边缘服务器接口。</p></td>
</tr>
</tbody>
</table>


## 证书摘要 - 公共即时消息连接


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/ 访问边缘服务</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>如果部署 AOL 的公共 IM 连接，则证书必须由公共 CA 提供，并且必须具有服务器 EKU 和客户端 EKU。证书将分配给以下组件的外部边缘接口：</p>
<ul>
<li><p>访问边缘服务</p></li>
<li><p>Web 会议边缘服务</p></li>
<li><p>A/V 边缘服务</p></li>
</ul>
<p>请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</p></td>
</tr>
</tbody>
</table>


## 可扩展消息传递和状态协议的证书摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>分配到 边缘服务器或 边缘池的 访问边缘服务</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>前三个 SAN 条目是完整 边缘服务器的正常 SAN 条目。contoso.com 是 XMPP 伙伴位于根域级别的联盟所需的条目。此条目将允许 XMPP 用于后缀为 *.contoso.com 的所有域。</p></td>
</tr>
</tbody>
</table>

