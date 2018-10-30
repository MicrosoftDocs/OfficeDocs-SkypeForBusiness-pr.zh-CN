---
title: Lync Server 2013：持久聊天服务器容量规划
TOCTitle: 持久聊天服务器容量规划
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615006(v=OCS.15)
ms:contentKeyID: 49313333
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 持久聊天服务器容量规划

 

_**上一次修改主题：** 2016-12-08_

持久聊天服务器可执行能够保留以供将来检索和搜索的多用户实时聊天。与保存在用户的邮箱中的组即时消息 (IM) 不同，如果已配置对话历史记录，则 持久聊天服务器会话保持打开状态的时间更长，且内容与消息、文件、URL 以及当前对话中的其他数据一起保存在服务器上。

容量规划是准备部署 持久聊天服务器的重要部分。本主题详细介绍了支持的 持久聊天服务器拓扑和可用于确定部署的最佳配置的容量规划表，并说明了如何最好地管理在高峰期要求更大容量的 持久聊天服务器部署。

要下载 持久聊天服务器，请参阅“Microsoft Lync Server 2013 持久聊天服务器”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)。

有关安装 持久聊天服务器的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md)和 [在 Lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。

支持工具（如 Lync Server 规划工具）可进一步帮助您实施容量规划。有关规划工具的详细信息，请参阅规划文档中的 [开始 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。

## 支持 持久聊天服务器的拓扑

可以在单服务器池或多服务器池中部署 持久聊天服务器（使用单池拓扑或多池拓扑）。

对于新的 Lync Server 2013 部署，我们现在还支持在 Standard Edition Server 上部署 持久聊天服务器。但是，性能和规模将会受影响，并且由于该新部署没有高可用性选项，因此应该主要出于概念证明、评估等目的使用此部署。

> [!NOTE]  
> 有关两种拓扑的其他详细信息，请参阅本文档集中的 <a href="lync-server-2013-planning-for-persistent-chat-server.md">在 Lync Server 2013 中规划持久聊天服务器</a>和部署文档中的 <a href="lync-server-2013-deploying-persistent-chat-server.md">在 Lync Server 2013 中部署持久聊天服务器</a>。



## 单服务器拓扑

持久聊天服务器的最低配置和最简单的部署是单 持久聊天服务器前端服务器拓扑。此部署要求具有一台运行 持久聊天服务器的服务器（如果已启用合规性，该服务器可以运行合规性服务）、一台承载 SQL Server 数据库的服务器，如果有合规性要求，该 SQL Server 数据库用于存储合规性数据。

> [!IMPORTANT]  
> 您不能向作为 拓扑生成器中的单服务器部署启动的 持久聊天服务器池添加其他服务器。建议使用多服务器池拓扑（即使您使用的是单服务器），以便能在稍后根据需要添加更多服务器。


下图显示了具有合规性的单个 持久聊天服务器前端服务器拓扑的所有必需组件和可选组件。

**一台持久聊天服务器**

![带合规性服务的单服务器拓扑](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "带合规性服务的单服务器拓扑")

## 多服务器拓扑

为提供更大的容量和更强的可靠性，您可以根据 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)中的说明部署多服务器拓扑。多服务器拓扑最多可以包含四台运行 持久聊天服务器的活动计算机（高可用性和灾难恢复配置允许最多八台，其余四台处于待机状态），每台服务器可支持多达 20,000 个并发用户，4 台服务器总共可支持 80,000 个连接到 持久聊天服务器池的并发用户。多服务器拓扑与单服务器拓扑相同，只不过它有多台服务器承载 持久聊天服务器，并且缩放性更高。多台运行 持久聊天服务器的计算机应与 Lync Server 和合规性服务位于同一 Active Directory 域服务 域中。

下图显示了带有多台运行 持久聊天服务器的计算机、可选的合规性服务和单独的合规性数据库的多服务器拓扑的所有组件。

**多台持久聊天服务器**

![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")

在包含四台服务器的 持久聊天服务器部署中，80,000 个用户可以同时登录并使用 持久聊天，负载将按每台服务器 20,000 个用户平均分布。如果一台服务器不可用，连接到该服务器的用户将无法访问 持久聊天服务器。断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。该转接过程可能需要几分钟或更长时间，具体取决于网络上 持久聊天的流量大小。由于其余的每台服务器可能都正承载多达 30,000 个用户，因此我们建议您尽快还原不可用的服务器，以避免产生性能问题。或者，您可以使用 拓扑生成器或 Windows PowerShell cmdlet **set-CsPersistentChatActiveServer** 使另一台 持久聊天服务器变得可用。

## 持久聊天服务器容量规划

下面的表可帮助实施 持久聊天服务器容量规划。这些表说明了更改各种 持久聊天服务器设置如何影响容量功能。

## 规划 持久聊天服务器的最大容量

使用下面的示例表确定可以支持的用户数。

### 持久聊天服务器池最大容量示例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>活动的 持久聊天服务实例数量</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>持久聊天服务实例数量</p></td>
<td><p><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></p></td>
</tr>
<tr class="odd">
<td><p>连接的活动用户数量</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>设置的用户总数</p></td>
<td><p>150,000</p></td>
</tr>
<tr class="odd">
<td><p>终结点数量</p></td>
<td><p>120,000</p></td>
</tr>
</tbody>
</table>


在前面的示例中，计划支持 持久聊天服务器允许的最大用户数： 持久聊天服务的四台服务器/四个实例（对于高可用性和灾难恢复情形，可能具有另外四台运行 持久聊天服务器的非活动服务器）和每台服务器 20,000 个用户，总计 80,000 个活动用户。

## 管理 持久聊天聊天室访问的容量规划

下面的示例表可帮助规划管理 持久聊天服务器池中的 持久聊天聊天室访问。

### 管理聊天室访问示例

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>小聊天室</th>
<th>中聊天室</th>
<th>大聊天室</th>
<th>总</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>聊天室大小（连接的用户数）</p></td>
<td><p>每个聊天室 30 个用户</p></td>
<td><p>每个聊天室 150 个用户</p></td>
<td><p>每个聊天室 16,000 个用户</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>聊天室</p></td>
<td><p>32,000</p></td>
<td><p>1,067</p></td>
<td><p>10</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>属于大会堂的聊天室百分比</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>开放式聊天室的百分比</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>开放式聊天室数量（没有明确的成员身份）</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>非开放式聊天室数量（具有明确的成员身份的普通聊天室）</p></td>
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5</p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>大会堂聊天室数量（有更多的演示者进入）</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>按直接成员身份管理的聊天室比例</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>用户组管理的聊天室比率</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>开放式聊天室的每个聊天室成员列表中的用户组数量（未明确指定）</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>非开放式聊天室的每个聊天室成员列表中的用户数量</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>非开放式聊天室的每个聊天室成员列表中的用户组数量</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的管理者列表中的用户和用户组数量（开放式和非开放式聊天室）</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>每个大会堂聊天室的演示者列表中的用户和用户组数量（开放式和非开放式聊天室）</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>所有非开放式聊天室中基于用户的成员实体数量</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>所有非开放式聊天室中基于用户组的成员实体数量</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>所有大会堂聊天室中基于用户和用户组的实体数量</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>所有聊天室管理者列表中基于用户和用户组的管理者实体数量</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的活动用户数量</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>每个用户的聊天室数量</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>每个聊天室成员列表中用户组的数量</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>用户组管理的聊天室比率</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室中基于用户组的成员实体数量</p></td>
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>所有聊天室中基于用户的成员实体数量</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的管理者、演示者和范围列表中的用户和用户组数量</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>所有聊天室的管理者、演示者和范围列表中的用户和用户组数量</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>访问控制项数量</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>最大访问控制项数量</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


在前面的示例中，根据建议的准则部署 持久聊天服务器时，在启用合规性的情况下，最多可在包含四台服务器的池中处理 80,000 个活动用户。

该示例显示按小（在任何给定时间具有 30 个活动用户）、中（150 个活动用户）和大（16,000 个活动用户）进行分类的聊天室。根据以下总数计算特定大小的聊天室数量：

  - 系统中的活动用户数量

  - 给定大小的聊天室中的活动用户数量

  - 单个用户加入的给定大小的聊天室数量

对于每个聊天室，前面的容量规划表将指定与聊天室关联的访问控制项的数量，包括直接分配到聊天室的项。可以使用访问控制列表 (ACL) 控制对单个聊天室的访问，也可以在类别级别控制访问。在 ACL 中，单个访问控制项可以是用户组（例如，安全组、通讯组列表），也可以是单个用户。您可以为聊天室管理者、演示者和成员定义访问控制项。

> [!IMPORTANT]  
> 规划管理聊天室的策略时，请牢记允许的访问控制项总数是 200 万。如果计算出的访问控制项超过 200 万，服务器性能可能会显著降低。为避免这一问题，请尽可能确保您的访问控制项是用户组而非单个用户。


## 管理邀请的聊天室访问的容量规划

可以使用下面的容量规划表来了解当持久聊天服务器配置为发送邀请时在持久聊天数据库中创建和存储的邀请数。可以使用 Lync Server 控制面板中的“聊天室类别设置”页或使用 Windows PowerShell cmdlet **set-csPersistentChatCategory** 管理类别上的邀请。可以使用从 Lync 客户端启动的“聊天室管理”页或使用 Windows PowerShell cmdlet **set-csPersistentChatRoom** 管理聊天室上的邀请（与类别所允许的一致）。

下表中的示例数据假定在 50% 聊天室的“聊天室设置”页面上，“邀请”选项设置为“是”。

> [!IMPORTANT]  
> 如果计算出的服务器生成的邀请数量超过 100 万，服务器性能可能会显著降低。为避免这一问题，请确保将配置为发送邀请的聊天室的数量降至最低，或者限制可以加入配置为发送邀请的聊天室的用户数。


### 邀请的聊天室访问示例

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>小聊天室</th>
<th>中聊天室</th>
<th>大聊天室</th>
<th>总</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>可以访问聊天室的用户数量</p></td>
<td><p>每个聊天室 30 个用户</p></td>
<td><p>每个聊天室 150 个用户</p></td>
<td><p>每个聊天室 16,000 个用户</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>具有邀请的聊天室百分比</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>配置为发送邀请的聊天室数量</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>可以访问聊天室的用户数量</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>持久聊天服务器生成的邀请数量</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>允许的最大邀请数量</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2,000,000</p></td>
</tr>
<tr class="odd">
<td><p>模型 1 - 以每天每个聊天室的预期消息数开始</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>每个聊天室的聊天速率（每天）</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室的聊天速率（每秒）</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>模型 2 - 以每天每个用户发布的消息数开始</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>每个用户每天的聊天速率</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>每个聊天室的聊天速率（每天）</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室的聊天速率（每秒）</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


## 持久聊天服务器性能用户模型

下表描述了 持久聊天服务器的用户模型。它提供了容量规划要求的基础，并代表一个在四台服务器上拥有 80,000 个并发用户的典型组织。

### 持久聊天服务器性能用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>连接的活动用户的数量</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>持久聊天服务器服务实例的数目</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>小聊天室的大小</p></td>
<td><p>30 个用户</p></td>
</tr>
<tr class="even">
<td><p>中聊天室的大小</p></td>
<td><p>150 个用户</p></td>
</tr>
<tr class="odd">
<td><p>大聊天室的大小</p></td>
<td><p>16,000 个用户</p></td>
</tr>
<tr class="even">
<td><p>聊天室的总数</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>小聊天室的数量</p></td>
<td><p>32,000</p></td>
</tr>
<tr class="even">
<td><p>中聊天室的数量</p></td>
<td><p>1,067</p></td>
</tr>
<tr class="odd">
<td><p>大聊天室的数量</p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>每个用户的聊天室总数</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>每个用户的小聊天室数量</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>每个用户的中聊天室数量</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>每个用户的大聊天室数量</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>每个用户加入的聊天室数</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>峰值加入速率</p></td>
<td><p>10 个/秒</p></td>
</tr>
<tr class="even">
<td><p>总聊天速率</p></td>
<td><p>24 个/秒</p></td>
</tr>
<tr class="odd">
<td><p>小聊天室的聊天速率</p></td>
<td><p>22.22 个/秒</p></td>
</tr>
<tr class="even">
<td><p>中聊天室的聊天速率</p></td>
<td><p>1.67 个/秒</p></td>
</tr>
<tr class="odd">
<td><p>大聊天室的聊天速率</p></td>
<td><p>约 0.15/秒</p></td>
</tr>
<tr class="even">
<td><p>为邀请配置的聊天室的百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>直接成员身份的百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>组成员身份的百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 域服务 中上级隶属的平均数</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>每个用户的订阅联系人数</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>每个用户的平均终结点数</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>每个终结点的平均可见聊天室数</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>每个用户可见的平均聊天室数量</p></td>
<td><p>2.25（一个聊天室为 50%，两个聊天室也为 50%）；最多 6 个聊天室开放，每个监视器一个</p></td>
</tr>
<tr class="even">
<td><p>每个时间间隔轮询的参与者数量</p></td>
<td><p>每个可见聊天室 25 个</p></td>
</tr>
<tr class="odd">
<td><p>轮询间隔时长</p></td>
<td><p>5 分钟</p></td>
</tr>
<tr class="even">
<td><p>每秒钟轮询的参与者数量</p></td>
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>每个用户每小时的状态更改数量</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>每秒钟的状态更改数量</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>

