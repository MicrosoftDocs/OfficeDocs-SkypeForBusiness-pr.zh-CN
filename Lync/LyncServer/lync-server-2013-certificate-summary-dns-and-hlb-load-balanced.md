---
title: Lync Server 2013：证书摘要 - 已进行 DNS 和 HLB 负载平衡
TOCTitle: 证书摘要 - 已进行 DNS 和 HLB 负载平衡
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205047(v=OCS.15)
ms:contentKeyID: 49313434
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡

 

_**上一次修改主题：** 2015-03-09_

针对具有 DNS 负载平衡的 控制器和硬件负载平衡器的证书要求将使用具有 控制器可接收的服务的使用者名称和使用者替代名称的默认证书。将为池中的每个 控制器请求一个证书。请务必记住，硬件负载平衡器仅对来自反向代理的流量进行负载平衡。此外，还有安装在每台服务器上用于服务器到服务器身份验证的 OAuth 令牌证书。

### 控制器的证书

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
<th>使用者名称 (SN)</th>
<th>使用者替代名称 (SAN)</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（可选）*.contoso.com</p></td>
<td><p>可从在内部管理的证书颁发机构或从公共 CA 请求 控制器证书。</p>
<p>控制器会响应来自外围的反向代理或来自 边缘服务器的请求。内部客户端不会使用 控制器。</p>
<p>或者，简单 URL 的通配符条目</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>无条目</p></td>
<td><div>

> [!IMPORTANT]  
> 请注意，最小密钥长度为 1024，但您可能收到一条警告，告知建议的最小密钥长度为 2048 位。

</div>
<p>OAuthTokenIssuer 证书是单用途证书，用于在大型环境中对服务器进行身份验证，并且可从内部 CA 或公共 CA 请求。此证书是必需的。</p></td>
</tr>
</tbody>
</table>

