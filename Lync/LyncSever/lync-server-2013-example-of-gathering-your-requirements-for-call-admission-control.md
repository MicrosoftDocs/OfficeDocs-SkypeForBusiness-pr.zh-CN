---
title: Lync Server 2013：收集呼叫允许控制要求的示例
TOCTitle: 示例：收集组织的呼叫允许控制要求
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425827(v=OCS.15)
ms:contentKeyID: 49312442
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 示例：在 Lync Server 2013 中收集呼叫允许控制要求

 

_**上一次修改主题：** 2015-03-09_

此示例显示如何规划和实现呼叫允许控制 (CAC)。总体来说，包括以下活动：

1.  标识所有网络中心和网络中枢（称为 *网络区域* ）。

2.  标识将管理每个网络区域的 CAC 的 Lync Server 中央站点。

3.  标识并定义连接到每个网络区域的 *网络站点* 。

4.  对于与 WAN 的连接受带宽限制的每个网络站点，描述 WAN 连接的带宽容量，以及网络管理员为 Lync Server 媒体流量设置的带宽限制（如果适用）。不需要包括与 WAN 的连接不受带宽限制的站点。

5.  将网络中的每个子网与一个网络站点相关联。

6.  映射网络区域之间的链路。对于每个链路，描述其带宽容量，以及网络管理员对 Lync Server 媒体流量设置的任何限制。

7.  定义每对网络区域之间的路由。

## 收集所需信息

要准备呼叫允许控制，请收集以下步骤中描述的信息：

1.  标识网络区域。网络区域代表网络中枢或网络中心。
    
    网络中枢或网络中心是计算机网络基础结构的一部分，它将网络的各个部分相互连接起来，提供在不同 LAN 或子网之间交换信息的路径。网络中枢可以将各种网络关联在一起，适用范围从较小区域到广阔的地理区域。网络中枢的容量通常大于与其连接的网络的容量。
    
    示例拓扑具有三个网络区域：北美、EMEA 和 APAC。网络区域包含网络站点的集合。与网络管理员合作以定义企业的网络区域。

2.  标识每个网络区域关联的中央站点。中央站点包含至少一台 前端服务器，并且是将管理通过网络区域 WAN 连接的所有媒体流量的 CAC 的 Lync Server 部署。
    
    **分为三个网络区域的企业网络示例**
    
    ![包含 3 个网络区域的网络拓扑的示例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "包含 3 个网络区域的网络拓扑的示例")  
    
    > [!NOTE]  
    > 多协议标签交换 (MPLS) 网络应代表一个网络区域，在该网络区域中，每个物理位置都具有一个相应的网络站点。有关详细信息，请参阅规划文档中的“<a href="lync-server-2013-call-admission-control-on-an-mpls-network.md">具有 Lync Server 2013 的 MPLS 网络上的呼叫允许控制</a>”主题。
    
    
    在上述示例网络拓扑中，存在三个网络区域，每个网络区域都具有一个管理 CAC 的 Lync Server 中央站点。按地理距离选择网络区域相应的中央站点。由于网络区域内的媒体流量最多，按地理距离选择中央站点使网络区域能够独立运行，因此即使其他中央站点不可用，网络区域也可以继续正常工作。
    
    在此示例中，名为“芝加哥”的 Lync Server 部署是北美区域的中央站点。
    
    北美的所有 Lync 用户都驻留在芝加哥部署中的服务器上。下表显示了所有三个网络区域的中央站点。
    
    ### 网络区域及其关联的中央站点
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>网络区域</th>
    <th>中央站点</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>北美</p></td>
    <td><p>芝加哥</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>伦敦</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>北京</p></td>
    </tr>
    </tbody>
    </table>
    
    > [!NOTE]  
    > 根据您的 Lync Server 拓扑，同一中央站点可分配给多个网络区域。
    


3.  对于每个网络区域，标识其 WAN 连接不受带宽限制的所有网络站点（办公室或位置）。由于这些站点不受带宽限制，因此无需对其应用 CAC 带宽策略。
    
    在下表显示的示例中，有三个网络站点没有受带宽限制的 WAN 链路：纽约、芝加哥和底特律。
    
    ### 不受 WAN 带宽限制的网络站点
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>网络站点</th>
    <th>网络区域</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>纽约</p></td>
    <td><p>北美</p></td>
    </tr>
    <tr class="even">
    <td><p>芝加哥</p></td>
    <td><p>北美</p></td>
    </tr>
    <tr class="odd">
    <td><p>底特律</p></td>
    <td><p>北美</p></td>
    </tr>
    </tbody>
    </table>


4.  对于每个网络区域，标识所有通过受带宽限制的 WAN 链路连接到网络区域的网络站点。
    
    为了帮助确保音频和视频质量，我们建议这些受带宽限制的网络站点监控其 WAN，并拥有限制流入和流出网络区域的媒体（音频或视频）流量的 CAC 带宽策略。
    
    在下表显示的示例中，有三个受 WAN 带宽限制的网络站点：波特兰、里诺和阿尔伯克基。
    
    ### 受 WAN 带宽限制的网络站点
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>网络站点</th>
    <th>网络区域</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>阿尔伯克基</p></td>
    <td><p>北美</p></td>
    </tr>
    <tr class="even">
    <td><p>里诺</p></td>
    <td><p>北美</p></td>
    </tr>
    <tr class="odd">
    <td><p>波特兰</p></td>
    <td><p>北美</p></td>
    </tr>
    </tbody>
    </table>
    
    **CAC 网络区域北美拥有三个不受带宽限制的网络站点（芝加哥、纽约和底特律）和三个受 WAN 带宽限制的网络站点（波特兰、里诺和阿尔伯克基）。**
    
    ![受 WAN 带宽限制的网络站点的示例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "受 WAN 带宽限制的网络站点的示例")  

5.  对于每个受带宽限制的 WAN 链路，需确定以下事项：
    
      - 要为所有并发音频会话设置的总体带宽限制。如果新的音频会话将导致超出该限制，那么 Lync Server 将不允许该会话启动。
    
      - 要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。
    
      - 要为所有并发视频会话设置的总体带宽限制。如果新的视频会话将导致超出该限制，那么 Lync Server 将不允许该会话启动。
    
      - 要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。
    
    ### 具有 WAN 带宽限制信息（带宽单位：kbps）的网络站点
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>网络站点</th>
    <th>网络区域</th>
    <th>BW 限制</th>
    <th>音频限制</th>
    <th>音频会话限制</th>
    <th>视频限制</th>
    <th>视频会话限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>阿尔伯克基</p></td>
    <td><p>北美</p></td>
    <td><p>5,000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1,400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>里诺</p></td>
    <td><p>北美</p></td>
    <td><p>10,000</p></td>
    <td><p>4,000</p></td>
    <td><p>175</p></td>
    <td><p>2,800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>波特兰</p></td>
    <td><p>北美</p></td>
    <td><p>5,000</p></td>
    <td><p>4,000</p></td>
    <td><p>175</p></td>
    <td><p>2,800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>纽约</p></td>
    <td><p>北美</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    </tr>
    <tr class="odd">
    <td><p>芝加哥</p></td>
    <td><p>北美</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    </tr>
    <tr class="even">
    <td><p>底特律</p></td>
    <td><p>北美</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    </tr>
    </tbody>
    </table>


6.  对于网络中的每个子网，指定其关联的网络站点。
    
    > [!IMPORTANT]  
    > 即使网络站点不受带宽限制，网络中的每个子网也必须与一个网络站点相关联。这是因为呼叫允许控制使用子网信息来确定终结点所在的网络站点。确定会话双方的位置后，呼叫允许控制可以确定是否有足够的带宽来建立呼叫。当通过没有带宽限制的链路建立会话时，会生成警报。<br />
    > 如果部署音频/视频边缘服务器，则每台边缘服务器的公共 IP 地址都必须与部署边缘服务器的网络站点关联。必须将 A/V 边缘服务器的每个公共 IP 地址作为子网掩码为 32 的子网添加到网络配置设置中。例如，如果在芝加哥部署 A/V 边缘服务器，则为这些服务器的每个外部 IP 地址创建一个子网掩码为 32 的子网，并将网络站点芝加哥与这些子网相关联。有关公共 IP 地址的详细信息，请参阅规划文档中的 <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</a>。
    
    > [!NOTE]  
    > 生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点关联。该警报在 8 小时内只产生一次。相关的警报信息和示例如下所示：<br />
    <strong>来源：</strong>CS 带宽策略服务（核心）<br />
    <strong>事件编号：</strong>36034<br />
    <strong>级别 ：</strong>2<br />
    <strong>说明 ：</strong>未配置以下 IP 地址的子网，或者子网未与网络站点关联: &lt;IP 地址列表&gt;。<br />
    <strong>原因 ：</strong>网络配置设置中缺少相应 IP 地址的子网，或子网未与网络站点相关联。<br />
    <strong>解决方案 ：</strong>将与上述 IP 地址列表对应的子网添加到网络配置设置中，并将每个子网关联到网络站点。<br />
    例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题：
    <ol>
    <li><p>确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 相关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 相关联。</p></li>
    <li><p>确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点相关联。</p></li>
    </ol>
    
    
    ### 网络站点和关联子网（带宽单位：kbps）
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>网络站点</th>
    <th>网络区域</th>
    <th>BW 限制</th>
    <th>音频限制</th>
    <th>音频会话限制</th>
    <th>视频限制</th>
    <th>视频会话限制</th>
    <th>子网</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>阿尔伯克基</p></td>
    <td><p>北美</p></td>
    <td><p>5,000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1,400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>里诺</p></td>
    <td><p>北美</p></td>
    <td><p>10,000</p></td>
    <td><p>4,000</p></td>
    <td><p>175</p></td>
    <td><p>2,800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>波特兰</p></td>
    <td><p>北美</p></td>
    <td><p>5,000</p></td>
    <td><p>4,000</p></td>
    <td><p>175</p></td>
    <td><p>2,800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>纽约</p></td>
    <td><p>北美</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>芝加哥</p></td>
    <td><p>北美</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>底特律</p></td>
    <td><p>北美</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>（没有限制）</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  在 Lync Server 呼叫允许控制中，网络区域间的连接称为 *区域链路* 。对于每个区域链路，按照对网络站点执行的操作，确定以下事项：
    
      - 要为所有并发音频会话设置的总体带宽限制。如果新的音频会话将导致超出该限制，那么 Lync Server 将不允许该会话启动。
    
      - 要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。
    
      - 要为所有并发视频会话设置的总体带宽限制。如果新的视频会话将导致超出该限制，那么 Lync Server 将不允许该会话启动。
    
      - 要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。
    
    **具有关联带宽限制的网络区域链路**
    
    ![3 个区域间的限制的示例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3 个区域间的限制的示例")  
    
    ### 区域链路带宽信息（带宽单位：kbps）
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>区域链路名称</th>
    <th>第一个区域</th>
    <th>第二个区域</th>
    <th>BW 限制</th>
    <th>音频限制</th>
    <th>音频会话限制</th>
    <th>视频限制</th>
    <th>视频会话限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-LINK</p></td>
    <td><p>北美</p></td>
    <td><p>EMEA</p></td>
    <td><p>50,000</p></td>
    <td><p>20,000</p></td>
    <td><p>175</p></td>
    <td><p>14,000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-LINK</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25,000</p></td>
    <td><p>10,000</p></td>
    <td><p>175</p></td>
    <td><p>7,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  定义每对网络区域之间的路由。
    
    > [!NOTE]  
    > 北美和 APAC 区域之间的路由需要两个链路，因为没有直接连接这两个区域的区域链路。
    
    
    ### 区域路由
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>区域路由名称</th>
    <th>第一个区域</th>
    <th>第二个区域</th>
    <th>区域链路</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>北美</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-LINK</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-ROUTE</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-LINK</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ROUTE</p></td>
    <td><p>北美</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-LINK、EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  对于通过单链路（称为 *站点间* 链路）直接进行连接的每对网络站点，需确定以下事项：
    
      - 要为所有并发音频会话设置的总体带宽限制。如果新的音频会话将导致超出该限制，那么 Lync Server 将不允许该会话启动。
    
      - 要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。
    
      - 要为所有并发视频会话设置的总体带宽限制。如果新的视频会话将导致超出该限制，那么 Lync Server 将不允许该会话启动。
    
      - 要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。
    
    **CAC 网络区域北美显示里诺和阿尔伯克基之间的站点间链路的带宽容量和带宽限制。**
    
    ![受 WAN 带宽限制的网络站点的示例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "受 WAN 带宽限制的网络站点的示例")  
    
    ### 两个网络站点间的站点间链路的带宽信息（带宽单位：kbps）
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>站点间链路名称</th>
    <th>第一个站点</th>
    <th>第二个站点</th>
    <th>BW 限制</th>
    <th>音频限制</th>
    <th>音频会话限制</th>
    <th>视频限制</th>
    <th>视频会话限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-Intersite-Link</p></td>
    <td><p>里诺</p></td>
    <td><p>阿尔伯克基</p></td>
    <td><p>20,000</p></td>
    <td><p>12,000</p></td>
    <td><p>175</p></td>
    <td><p>5,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


## 后续步骤

收集所需信息之后，可使用 Lync Server 命令行管理程序或 Lync Server 控制面板执行 CAC 部署。

> [!NOTE]  
> 虽然可以使用 Lync Server 控制面板执行大多数网络配置任务，但是创建子网和站点间链路时，必须使用 Lync Server 命令行管理程序。有关详细信息，请参阅有关 <strong>New-CsNetworkSubnet</strong> cmdlet 和 <strong>New-CsNetworkIntersitePolicy</strong> cmdlet 的 Lync Server 命令行管理程序文档。


