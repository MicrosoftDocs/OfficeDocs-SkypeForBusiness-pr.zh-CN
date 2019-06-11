---
title: 'Lync Server 2013: 持久聊天服务器的容量规划'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af60947a1132d26d5e8ba015d54cdbea80b8b54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的容量规划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

持久聊天服务器可以执行可持续进行的多用户实时聊天, 以便将来检索和搜索。 与保存在用户邮箱中的组即时消息 (IM) 不同, 如果已配置对话历史记录, 持久聊天服务器会话将保持打开状态, 并将内容保存在服务器上, 以及邮件、文件、Url 和其他属于正在进行的对话。

容量规划是准备部署持久聊天服务器的重要部分。 本主题提供了有关受支持的持久聊天服务器拓扑和容量计划表的详细信息, 可用于为你的部署确定最佳配置。 它还介绍了如何最好地管理在高峰时段需要更大容量的持久聊天服务器部署。

若要下载持久聊天服务器, 请参阅 "Microsoft Lync Server 13 持久聊天服务器[http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)"。

有关安装持久聊天服务器的详细信息, 请参阅在[Lync server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md)和在部署文档的[lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。

支持工具 (如 Lync Server 规划工具) 可以通过容量规划进一步帮助您。 有关规划工具的详细信息, 请参阅规划文档中的[Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>持久聊天服务器支持的拓扑

你可以在单服务器或多服务器池中部署持久聊天服务器, 并通过单个池或多池拓扑进行部署。

现在, 我们还支持适用于新 Lync Server 2013 部署的标准版服务器上的持久聊天服务器。 但是, 性能和规模将受到影响, 并且由于没有适用于此新部署的高可用性选项, 因此我们希望你主要用于概念证明、评估等目的。

<div>


> [!NOTE]  
> 有关这两种拓扑的其他详细信息, 请参阅本文档中的 "<A href="lync-server-2013-planning-for-persistent-chat-server.md">在 lync server 2013 中规划持久聊天服务器</A>" 和 "部署文档" 中的<A href="lync-server-2013-deploying-persistent-chat-server.md">lync server 2013 中的 "部署持久</A>聊天服务器"。



</div>

<div>

## <a name="single-server-topology"></a>单服务器拓扑

持久聊天服务器的最低配置和最简单的部署是单个持久聊天服务器前端服务器拓扑。 此部署需要运行持久聊天服务器的单个服务器 (可选择运行合规性服务)、托管 SQL Server 数据库的服务器以及是否需要合规性、SQL Server 数据库 (用于存储合规性数据。

<div>


> [!IMPORTANT]  
> 不能将其他服务器添加到在拓扑生成器中作为单服务器部署启动的持久聊天服务器池。 我们建议使用多服务器池拓扑, 即使您使用的是单个服务器也是如此。 这样, 您就可以在以后添加更多的服务器 (如果需要)。 


</div>

下图显示了具有合规性的单个持久聊天服务器前端服务器的拓扑的所有必需和可选组件。

**单个持久聊天服务器**

![具有合规性服务的单服务器拓扑](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有合规性服务的单服务器拓扑")

</div>

<div>

## <a name="multiple-server-topology"></a>多服务器拓扑

为了提供更大的容量和可靠性, 你可以部署多服务器拓扑, 如在[Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)中所述。 多服务器拓扑可以包括多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许八个, 但只有四个可以激活, 并且其余四个处于待机状态)。 每台服务器可支持多达20000并行用户, 总共可支持连接到具有4台服务器的持久聊天服务器池的80000个并发用户。 多服务器拓扑与单服务器拓扑相同, 不同之处在于多台服务器托管持久聊天服务器, 并且可以更高的比例。 运行持久聊天服务器的多台计算机应位于与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。

下图显示多服务器拓扑的所有组件, 其中包含运行持久聊天服务器的多台计算机、可选合规性服务和单独的合规性数据库。

**多个持久聊天服务器**

![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")

在四台服务器持久聊天服务器部署 (其中80000用户可以同时登录和使用持久聊天) 中, 每个服务器的20000用户均会平均分配负载。 如果一台服务器不可用, 连接到该服务器的用户将失去其永久聊天服务器的访问权限。 断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。 根据网络上持久聊天流量的数量, 此传输可能需要几分钟或更长时间。 由于其余每个服务器都可能托管为多达30000用户, 因此我们建议尽快还原不可用的服务器, 以避免性能问题。 否则, 你可以使用拓扑生成器或 Windows PowerShell cmdlet ( **CsPersistentChatActiveServer**) 来使另一个持久聊天服务器可用。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>持久聊天服务器容量规划

下表可帮助你对持久聊天服务器进行容量规划。 他们对更改各种持久聊天服务器设置有何影响, 从而影响容量功能。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>规划持久聊天服务器的最大容量

使用下面的示例表确定可以支持的用户数。

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>持久聊天服务器池最大容量示例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>活动的持久聊天服务实例</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>持久聊天服务实例</p></td>
<td><p><em>8 (4 必须处于非活动状态, 最多只能有4个活动)</em></p></td>
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


在前面的示例中, 计划支持持久聊天服务器允许的最大用户数: 四个服务器/持久聊天服务实例 (可以有四个更多的被动服务器, 运行持久聊天服务器以获得高可用性和灾难恢复) 和每台服务器20000用户, 共80000个活动用户。

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>管理持久的聊天室访问的容量计划

下面的示例表可帮助你计划管理持久聊天服务器池中的持久聊天室访问。

### <a name="managing-chat-room-access-sample"></a>管理聊天室访问示例

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
<th>总计</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>聊天室大小（连接的用户数）</p></td>
<td><p>每个聊天室 30 个用户</p></td>
<td><p>每个聊天室 150 个用户</p></td>
<td><p>每个聊天室 16,000 个用户</p></td>
<td></td>
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
<td></td>
</tr>
<tr class="even">
<td><p>开放式聊天室的百分比</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
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
<td></td>
</tr>
<tr class="even">
<td><p>按直接成员身份管理的聊天室比例</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>用户组管理的聊天室比率</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>开放式聊天室的每个聊天室成员列表中的用户组数量（未明确指定）</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>非开放式聊天室的每个聊天室成员列表中的用户数量</p></td>
<td><p>大约</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>非开放式聊天室的每个聊天室成员列表中的用户组数量</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的管理者列表中的用户和用户组数量（开放式和非开放式聊天室）</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每个大会堂聊天室的演示者列表中的用户和用户组数量（开放式和非开放式聊天室）</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>所有非开放式聊天室中基于用户的成员实体数量</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有非开放式聊天室中基于用户组的成员实体数量</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>所有大会堂聊天室中基于用户和用户组的实体数量</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室管理者列表中基于用户和用户组的管理者实体数量</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的活动用户数量</p></td>
<td><p><em>大约</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每个用户的聊天室数量</p></td>
<td><p><em>至</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>utf-16</em></p></td>
</tr>
<tr class="odd">
<td><p>每个聊天室成员列表中用户组的数量</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>岁</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>用户组管理的聊天室比率</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>所有聊天室中基于用户组的成员实体数量</p></td>
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室中基于用户的成员实体数量</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的管理者、演示者和范围列表中的用户和用户组数量</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室的管理者、演示者和范围列表中的用户和用户组数量</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
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
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


在前面的示例中, 当你根据推荐的指南部署持久聊天服务器时, 他们最多可以在启用了合规性的四个服务器池中处理最多80000个活动用户。

该示例显示按小（在任何给定时间具有 30 个活动用户）、中（150 个活动用户）和大（16,000 个活动用户）进行分类的聊天室。 根据以下大小的 "聊天室" 的总数计算:

  - 系统中的活动用户数量

  - 给定大小的聊天室中的活动用户数量

  - 单个用户加入的给定大小的聊天室数量

对于每个聊天室，前面的容量规划表将指定与聊天室关联的访问控制项的数量，包括直接分配到聊天室的项。可以使用访问控制列表 (ACL) 控制对单个聊天室的访问，也可以在类别级别控制访问。在 ACL 中，单个访问控制项可以是用户组（例如，安全组、通讯组列表），也可以是单个用户。您可以为聊天室管理者、演示者和成员定义访问控制项。

<div>


> [!IMPORTANT]  
> 规划管理聊天室的策略时，请牢记允许的访问控制项总数是 200 万。如果计算出的访问控制项超过 200 万，服务器性能可能会显著降低。为避免这一问题，请尽可能确保您的访问控制项是用户组而非单个用户。



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>通过邀请管理聊天室访问的容量计划

当配置为发送邀请时, 可以使用以下容量规划表了解持久聊天服务器在持久聊天数据库中创建和存储的邀请数。 通过使用 Lync Server 控制面板中的 "**聊天室类别设置**" 页面或使用 Windows PowerShell cmdlet **csPersistentChatCategory**, 可在类别上管理邀请。 通过使用从 Lync 客户端启动的**聊天室管理**页面或使用 Windows PowerShell cmdlet **csPersistentChatRoom**, 您可以在聊天室 (使用类别允许的情况下) 管理邀请。

下表中的示例数据假定在 50% 聊天室的“**聊天室设置**”页面上，“**邀请**”选项设置为“**是**”。

<div>


> [!IMPORTANT]  
> 如果计算出的服务器生成的邀请数量超过 100 万，服务器性能可能会显著降低。 若要避免此问题, 请确保将配置为发送邀请的聊天室的数量减到最少, 或者限制可加入聊天室的用户数, 这些聊天室已配置为发送邀请。



</div>

### <a name="chat-room-access-by-invitation-sample"></a>通过邀请的聊天室访问示例

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
<th>总计</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>可以访问聊天室的用户数量</p></td>
<td><p>每个聊天室 30 个用户</p></td>
<td><p>每个聊天室 150 个用户</p></td>
<td><p>每个聊天室 16,000 个用户</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>具有邀请的聊天室百分比</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>配置为发送邀请的聊天室数量</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>可以访问聊天室的用户数量</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>持久聊天服务器生成的邀请</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>允许的最大邀请数量</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
<tr class="odd">
<td><p>模型 1 - 以每天每个聊天室的预期消息数开始</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
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
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个用户每天的聊天速率</p></td>
<td><p>岁</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>名</p></td>
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


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>持久聊天服务器性能用户模型

下表介绍持久聊天服务器的用户模型。 它提供了容量规划要求的基础，并代表一个在四台服务器上拥有 80,000 个并发用户的典型组织。

### <a name="persistent-chat-server-performance-user-model"></a>持久聊天服务器性能用户模型

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
<td><p>持久聊天服务器服务实例数</p></td>
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
<td><p>utf-16</p></td>
</tr>
<tr class="odd">
<td><p>每个用户的小聊天室数量</p></td>
<td><p>至</p></td>
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
<td><p>全</p></td>
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
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>中聊天室的聊天速率</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>大聊天室的聊天速率</p></td>
<td><p>~0.15/second</p></td>
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
<td><p>Active Directory 域服务中上级隶属关系的平均数量</p></td>
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


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

