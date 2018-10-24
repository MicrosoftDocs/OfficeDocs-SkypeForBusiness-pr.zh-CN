---
title: Lync Server 2013：配置 DNS 负载平衡
TOCTitle: 配置 DNS 负载平衡
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398251(v=OCS.15)
ms:contentKeyID: 49312167
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置 DNS 负载平衡

 

_**上一次修改主题：** 2015-03-09_

若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

域名系统 (DNS) 负载平衡可平衡 Lync Server 2013 独有的网络流量，例如 SIP 流量和媒体流量。前端池、边缘池、控制器池和独立的中介池都支持 DNS 负载平衡。配置为使用 DNS 负载平衡的池必须定义两个完全限定的域名 (FQDN)：一个是常规池 FQDN（例如 pool1.contoso.com），由 DNS 负载平衡使用并解析为池中服务器的物理 IP；另一个 FQDN 用于池的 Web 服务（例如 web1.contoso.net），并解析为池的虚拟 IP 地址。有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)。

> [!NOTE]  
> 要使客户端能够提供 HTTPS 流量，仍然需要硬件负载平衡。



使用 DNS 负载平衡之前，必须执行以下操作：

1.  覆盖内部 Web 服务池 FQDN。
    
    > [!WARNING]
    > 如果决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须不同于任何其他前端池、控制器或控制器池。


2.  创建 DNS A 主机记录以将池 FQDN 解析为池中所有服务器的 IP 地址。

3.  启用 IP 地址随机选择，或启用循环（对于 Windows Server DNS）。
    
    > [!NOTE]  
    > 默认情况下应启用循环。
    


## 覆盖内部 Web 服务 FQDN

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在控制台树中，展开 Enterprise Edition 前端池节点。

3.  右键单击该池，单击“编辑属性”，然后单击“Web 服务”。

4.  在“内部 Web 服务”下面，选中“覆盖 FQDN”复选框。

5.  键入解析为池中服务器的物理 IP 地址的池 FQDN。

6.  在“外部 Web 服务”下面，键入解析为池的虚拟 IP 地址的外部池 FQDN，然后单击“确定”。

7.  在控制台树中，单击“Lync Server 2013”，然后在“操作”窗格中，单击“发布拓扑”。

## 为所有内部池服务器创建 DNS 主机 (A) 记录

1.  依次单击“开始”、“所有程序”、“管理工具”，然后单击“DNS”。

2.  在“DNS 管理器”中，单击管理记录的 DNS 服务器以将其展开。

3.  单击“正向查找区域”以将其展开。

4.  右键单击要向其中添加记录的 DNS 域，然后单击“新主机 (A 或 AAAA)”。

5.  在“名称”框中，键入主机记录的名称（将自动追加域名）。

6.  在 IP 地址框中，键入单个前端服务器的 IP 地址，然后选择“创建关联的指针 (PTR) 记录”或“允许所有经过身份验证的用户使用同一所有者名称更新 DNS 记录”（如果适用）。

7.  继续为将参与 DNS 负载平衡的所有成员前端服务器创建记录。
    
    例如，如果已有一个名为 pool1.contoso.com 的池和三个前端服务器，则需创建以下 DNS 条目：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>类型</th>
    <th>数据</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主机 (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主机 (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主机 (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    有关创建 DNS 主机 (A) 记录的详细信息，请参阅[配置 Lync Server 2013 的 DNS 主机记录](lync-server-2013-configure-dns-host-records.md)。

## 为 Windows Server 启用循环

1.  依次单击“开始”、“所有程序”、“管理工具”，然后单击“DNS”。

2.  展开“DNS”，右键单击要配置的 DNS 服务器，然后单击“属性”。

3.  单击“高级”选项卡，选择“启用循环”和“启用网络掩码排序”，然后单击“确定”。
    
    ![“DNS 轮循机制”对话框](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "“DNS 轮循机制”对话框")

> [!NOTE]  
> 默认情况下应启用此功能。



## 另请参阅

#### 概念

[Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)

