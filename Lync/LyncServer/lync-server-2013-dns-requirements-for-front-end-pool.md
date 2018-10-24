---
title: Lync Server 2013：前端池的 DNS 要求
TOCTitle: 前端池的 DNS 要求
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398082(v=OCS.15)
ms:contentKeyID: 49311825
ms.date: 12/17/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中前端池的 DNS 要求

 

_**上一次修改主题：** 2016-12-15_

若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

使用 拓扑生成器发布拓扑之前需配置所需的域名系统 (DNS) 记录。此外，在 Lync Server 2013 部署的配置中使用的部分完全限定的域名 (FQDN) 是逻辑服务器 FQDN，而不是物理服务器 FQDN，因此发布前还需其他 DNS 配置。

> [!WARNING]
> Lync Server 2013 不支持单标签域。例如，支持具有名为 <strong>contoso.local</strong> 的根域的林，但不支持名为 <strong>local</strong> 的根域。有关详细信息，请参阅 Microsoft 知识库文章 300684“关于如何为使用单标签 DNS 名称的域配置 Windows 的信息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684" class="uri">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</a>。


> [!IMPORTANT]
> 指定的名称必须与在服务器上配置的计算机名称相同。默认情况下，未加入域的计算机的计算机名称是短名称，而不是 FQDN。拓扑生成器使用的是 FQDN，而不是短名称。在分配运行 Lync Server、边缘服务器和池的服务器的 FQDN 时， <strong>仅使用标准字符</strong> （包括 A–Z、a–z、0–9 和连字符）。不要使用 Unicode 字符或下划线。FQDN 中的非标准字符通常不受外部 DNS 和公共证书颁发机构 (CA) 的支持（如必须向证书中的 SN 分配 FQDN 时）。


部署拓扑后，在对其进行操作之前，应确保创建了以下 Active Directory 和 DNS 记录（根据所需的特定功能规定的需要）：

  - 每个将存在于拓扑中的服务器角色均发布为 Active Directory 对象（通过将计算机加入域可完成此任务）。

  - 每台服务器都存在 DNS A 记录。

  - 如果计划以 \_sipinternaltls\_tcp.*\<SIP domain\>* 形式使用客户端自动登录，则确保每个 SIP 域都存在 DNS SRV 记录。如果使用客户端的手动配置，则不需要此记录。

  - 每个配置的简单 URL（通常有四种：会议、拨入、LWA 和计划程序）的 DNS A 记录。此外，还有管理简单 URL，它是用于访问 Lync Server 2013 控制面板的特殊 URL。

  - 运行 SQL Server 的服务器必须加入域，且可供 拓扑生成器从中进行发布的计算机进行访问。

此表遵照规划部分中提供的参考体系结构。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

### 前端池所需的 DNS 记录

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置</th>
<th>类型</th>
<th>FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01（DNS 负载平衡）。池中每个 前端服务器的 IP 地址都需要有 DNS A 记录，并映射到池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01（硬件负载平衡器的虚拟 IP (VIP)）。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 前端服务器（节点 1）。</p>
<p>Pool01 前端服务器（节点 2）。</p>
<p>Pool01 前端服务器（节点 3）。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 前端服务器（节点 2）。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>客户端到服务器的 Web 通信的 Pool01 (VIP)。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>运行 SQL Server 2008 R2 的 Pool01 后端服务器。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>对于 Lync Phone Edition 或没有 DNS SRV 记录的客户端自动登录，以及严格域匹配而言为必需。并非在所有情况下都需要。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>假定存在第二个 SIP 域。对于 Lync Phone Edition、没有 DNS SRV 记录的客户端自动登录，以及严格域匹配而言为必需。并非在所有情况下都需要。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>内部发布的电话拨入式会议的简单 URL – 前端服务器或控制器（如果已安装）响应简单 URL 查询。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>内部发布的会议的简单 URL – 前端服务器或控制器（如果已安装）响应简单 URL 查询。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>管理</p></td>
<td><p>可选记录和内部发布的 Lync Server 2013 控制面板的简单 URL – 前端服务器或控制器（如果已安装）响应简单 URL 查询。建议只使用主机名（无域名）。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> VIP 表示硬件负载平衡器的虚拟 IP 地址



## 前端池的 DNS SRV 记录


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>位置</th>
<th>类型</th>
<th>FQDN</th>
<th>目标 FQDN</th>
<th>端口</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.contoso.com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 客户端的自动配置在内部工作时需要。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.fabrikam.com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Lync 2013 客户端的自动配置在内部工作时需要。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>支持 Lync Phone Edition 的设备所需的网络时间协议 (NTP) 源。在内部，它应指向域控制器。如果未定义域控制器，则会尝试使用 NTP 服务器 time.windows.com。</p></td>
</tr>
</tbody>
</table>

