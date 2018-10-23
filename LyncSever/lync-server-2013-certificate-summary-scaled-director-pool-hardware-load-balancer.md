---
title: Lync Server 2013：证书摘要 - 扩展的控制器池、硬件负载平衡器
TOCTitle: 证书摘要 - 扩展的控制器池、硬件负载平衡器
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204846(v=OCS.15)
ms:contentKeyID: 49312709
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器

 

_**上一次修改主题：** 2015-03-09_

带有硬件负载平衡器的 控制器的证书要求会将具有使用者名称和使用者替代名称的默认证书用于 控制器池可接收的服务。将为池中的每个 控制器请求一个证书。此外，每台服务器上还安装了用于进行服务器到服务器身份验证的 OAuth Token 证书。

### 使用硬件负载平衡器的缩放控制器的证书

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
<p>控制器会响应来自外围的反向代理或来自 边缘服务器的请求。</p>
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

