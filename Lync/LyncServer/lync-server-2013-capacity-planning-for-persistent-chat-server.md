---
title: Lync Server 2013：持久聊天服务器的容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6bb3c7dcd8d03ffb0a57fb165fe1dba4ee933d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512799"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的容量规划

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

持久聊天服务器可以执行多用户实时聊天，可以持续进行，以便将来检索和搜索。 与在用户邮箱中保存的组即时消息 (IM) 的不同之处是，如果配置了对话历史记录，则持久聊天服务器会话将保持打开状态，并将内容保存在服务器上，同时还会在正在进行的会话中的邮件、文件、Url 和其他数据中进行保存。

容量规划是准备部署持久聊天服务器的重要部分。 本主题提供了有关受支持的持久聊天服务器拓扑和容量规划表的详细信息，您可以使用这些表来确定适用于您的部署的最佳配置。 此外，还介绍了如何最好地管理在高峰时间需要更大容量的持久聊天服务器部署。

若要下载持久聊天服务器，请参阅在上的 "Microsoft Lync Server 13 持久聊天服务器" [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。

有关安装持久聊天服务器的详细信息，请参阅部署文档中的在 [Lync server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md) 和 [在 lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md) 。

支持工具（如 Lync Server 规划工具）可以进一步帮助您进行容量规划。 有关规划工具的详细信息，请参阅规划文档中的 [开始规划 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md) 。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>持久聊天服务器支持的拓扑

您可以在单服务器或多服务器池中部署持久聊天服务器，也可以使用单一池或多池拓扑。

现在，我们还支持适用于新的 Lync Server 2013 部署的 Standard Edition server 上的持久聊天服务器。 但是，性能和规模将受到影响，由于没有适用于此新部署的高可用性选项，因此我们预计您将主要用于概念验证、评估等目的。

<div>


> [!NOTE]  
> 有关这两种拓扑的更多详细信息，请参阅部署文档中的在 lync server 2013 中的 "在 <A href="lync-server-2013-planning-for-persistent-chat-server.md">lync server 中规划持久聊天服务器</A> " 和 " <A href="lync-server-2013-deploying-persistent-chat-server.md">在 lync Server 2013 中部署持久聊天服务器</A> "。



</div>

<div>

## <a name="single-server-topology"></a>单服务器拓扑

持久聊天服务器的最小配置和最简单部署是一个持久聊天服务器前端服务器拓扑。 此部署需要运行持久聊天服务器 (的单个服务器，如果符合性已启用，则可以选择运行合规性服务) 、承载 SQL Server 数据库的服务器以及是否需要合规性，以存储合规性数据的 SQL Server 数据库为依据。

<div>


> [!IMPORTANT]  
> 您不能向作为拓扑生成器中的单个服务器部署启动的持久聊天服务器池添加其他服务器。 我们建议使用多服务器池拓扑，即使您使用的是一台服务器。 这样，你将能够在以后添加更多服务器（如有必要）。 


</div>

下图显示了符合条件的单个持久聊天服务器前端服务器的拓扑的所有必需组件和可选组件。

**单个持久聊天服务器**

![单服务器拓扑与合规性服务](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "单服务器拓扑与合规性服务")

</div>

<div>

## <a name="multiple-server-topology"></a>多服务器拓扑

若要提供更大的容量和可靠性，可以部署多服务器拓扑，如在 [Lync server 2013 中规划持久聊天服务器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。 多服务器拓扑可以包含多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许8个，但只有四个活动可以处于活动状态，并且在待机) 的其余四个。 每个服务器最多可以支持多达20000个并发用户，共80000个并发用户连接到具有4台服务器的持久聊天服务器池。 多服务器拓扑与单服务器拓扑相同，不同之处在于多个服务器承载持久聊天服务器，并且可以扩展到更高级别。 运行持久聊天服务器的多台计算机应驻留在与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。

下图显示了多个服务器拓扑的所有组件，其中包含多个运行持久聊天服务器、可选合规性服务和独立合规性数据库的计算机。

**多个持久聊天服务器**

![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")

在四个服务器的持久聊天服务器部署中，其中80000个用户可以同时登录并使用持久聊天，每个服务器在20000个用户之间平均分布负载。 如果一台服务器变得不可用，则连接到该服务器的用户将失去其对持久聊天服务器的访问权限。 断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。 此传输可能需要几分钟或更长时间，具体取决于网络上的持久聊天流量量。 由于剩余的每个服务器都可能承载多达30000个用户，因此我们建议您尽可能快地还原不可用服务器以避免性能问题。 否则，可以使用拓扑生成器或 Windows PowerShell cmdlet，将另一个持久聊天服务器设为可用， **set-cspersistentchatactiveserver**。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>持久聊天服务器容量规划

下表可帮助您对持久聊天服务器进行容量规划。 它们对更改各种持久聊天服务器设置有何影响容量功能进行了建模。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>规划持久聊天服务器的最大容量

使用下面的示例表决定可以支持的用户数。

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
<td><p><em>8 (4 必须为非活动状态;最多只能有4个活动) </em></p></td>
</tr>
<tr class="odd">
<td><p>连接的活动用户</p></td>
<td><p><em>80000</em></p></td>
</tr>
<tr class="even">
<td><p>设置的用户总数</p></td>
<td><p>150000</p></td>
</tr>
<tr class="odd">
<td><p>终结点的数目</p></td>
<td><p>120000</p></td>
</tr>
</tbody>
</table>


在上面的示例中，计划支持持久聊天服务器允许的最大用户数：持久聊天服务 (的四个服务器/实例可以有四个以上的被动服务器，它们为高可用性和灾难) 恢复提供了四个更多的被动服务器，每个服务器包含20000个用户，总共是80000个活动用户。

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>管理持久聊天室访问的容量规划

下面的示例表可帮助您规划如何在持久聊天服务器池中管理持久聊天室访问。

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
<th>中型聊天室</th>
<th>大型聊天室</th>
<th>总计</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>聊天室的大小 (连接的用户数) </p></td>
<td><p>每个会议室30个</p></td>
<td><p>每个会议室150</p></td>
<td><p>每个会议室16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>聊天室</p></td>
<td><p>32000</p></td>
<td><p>1067</p></td>
<td><p>10  </p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>大会堂的会议室百分比</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>打开的会议室的百分比</p></td>
<td><p>第三章</p></td>
<td><p>第三章</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>打开会议室 (无显式成员资格) </p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>未打开的聊天室 (带有显式成员资格的常规聊天室) </p></td>
<td><p>31040</p></td>
<td><p>1.035</p></td>
<td><p>5 </p></td>
<td><p>32080</p></td>
</tr>
<tr class="odd">
<td><p>大会堂会议室 (其他演示者条目) </p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>通过直接成员管理的聊天室</p></td>
<td><p>50%</p></td>
<td><p>10</p></td>
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
<td><p>打开聊天室的每个聊天室的成员资格列表中的用户组 (未明确指定) </p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>非打开聊天室的每个聊天室的成员资格列表中的用户</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>非打开聊天室的每个聊天室的成员资格列表中的用户组</p></td>
<td><p>第三章</p></td>
<td><p>5 </p></td>
<td><p>10  </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的管理器列表中的用户和用户组 (开放和非打开的会议室) </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每个大会堂聊天室的演示者列表中的用户和用户组打开和未打开的会议室 () </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>跨所有非开放聊天室的基于用户的成员资格实体</p></td>
<td><p>465600</p></td>
<td><p>15520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>跨所有非开放聊天室的基于用户组的成员实体</p></td>
<td><p>46560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>跨所有大会堂聊天室的基于用户和用户组的实体</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>跨所有聊天室管理器列表的基于用户和用户组的管理器实体</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的活动用户数</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每个用户的聊天室数量</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>位</em></p></td>
</tr>
<tr class="odd">
<td><p>每个聊天室成员列表中用户组的数量</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>个</em></p></td>
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
<td><p>155200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室中基于用户的成员实体数量</p></td>
<td><p>465600</p></td>
<td><p>77600</p></td>
<td><p>72000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个聊天室的管理者、演示者和范围列表中的用户和用户组数量</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>跨聊天室的管理者、演示者和范围列表中的用户和用户组</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>访问控制项数量</p></td>
<td><p>704160</p></td>
<td><p>26768</p></td>
<td><p>160</p></td>
<td><p>731088</p></td>
</tr>
<tr class="even">
<td><p>最大访问控制项数量</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2000000</p></td>
</tr>
</tbody>
</table>


在上面的示例中，当您根据建议的准则部署持久聊天服务器时，他们可以跨启用了合规性的四个服务器池处理最多80000个活动用户。

本示例显示了在任意给定时间) 、中型 (150 活动用户) 和大型 (16000 活跃用户) 中分类为 (30 个活动用户的聊天工作室。 根据以下总数计算特定大小的聊天室数量：

  - 系统中的活动用户数量

  - 给定大小的聊天室中的活动用户数量

  - 单个用户加入的给定大小的聊天室数量

对于每个聊天室，上述容量规划表指定与聊天室相关联的访问控制条目数，包括直接分配到聊天室的条目。 您可以通过使用访问控制列表 (Acl) 来控制对各个聊天室的访问。 您还可以在类别级别控制访问权限。 在 ACL 中，单个访问控制项可以是用户组（例如，安全组、通讯组列表或单个用户）。 您可以为聊天室管理者、演示者和成员定义访问控制条目。

<div>


> [!IMPORTANT]  
> 在规划管理聊天室的策略时，请记住允许的访问控制条目总数为2000000。 如果计算出的访问控制条目超过2000000，服务器性能可能会显著降低。 若要避免此问题，请尽可能确保您的访问控制项是用户组而不是单个用户。



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>管理邀请的聊天室访问的容量规划

您可以使用以下容量规划表来了解持久聊天服务器在配置为发送邀请时在持久聊天数据库中创建和存储的邀请数。 您可以使用 Lync Server 控制面板中的 " **聊天室类别设置** " 页或使用 Windows PowerShell Cmdlet 管理类别上的邀请。 **csPersistentChatCategory**。 您可以通过使用从 Lync 客户端启动的 " **会议室管理** " 页或使用 Windows PowerShell cmdlet **set-cspersistentchatroom**在 (聊天室上管理邀请，具体取决于该类别允许的) 。

下表中的示例数据假定，在所有聊天室的50% 的 **聊天室设置** 页上，" **邀请** " 选项设置为 **"是"**。

<div>


> [!IMPORTANT]  
> 如果服务器生成的邀请数的计算值超过1000000，服务器性能可能会显著降低。 若要避免此问题，请确保将配置为发送邀请的聊天室的数量减至，或限制可加入聊天室的用户数，这些聊天室已配置为发送邀请。



</div>

### <a name="chat-room-access-by-invitation-sample"></a>邀请的聊天室访问示例

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
<th>中型聊天室</th>
<th>大型聊天室</th>
<th>总计</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>可以访问聊天室的用户</p></td>
<td><p>每个会议室30个</p></td>
<td><p>每个会议室150</p></td>
<td><p>每个会议室16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>具有邀请的聊天室的百分比</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>配置为发送邀请的聊天室数量</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>可以访问聊天室的用户数</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>持久聊天服务器生成的邀请</p></td>
<td><p>960000</p></td>
<td><p>120000</p></td>
<td><p>80000</p></td>
<td><p>1160000</p></td>
</tr>
<tr class="even">
<td><p>允许的最大邀请数量</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2000000</p></td>
</tr>
<tr class="odd">
<td><p>模型 1-以预期的每天每个会议室的邮件数开头</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>每天 (每个会议室的聊天费率) </p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室每秒 (的聊天速率) </p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>模型 2-以每个用户每天发布的邮件数开头</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每个用户每天的聊天速率</p></td>
<td><p>15 </p></td>
<td><p>5 </p></td>
<td><p>0.1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>每天 (每个会议室的聊天费率) </p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1213</p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室每秒 (的聊天速率) </p></td>
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

下表介绍持久聊天服务器的用户模型。 它提供了容量规划要求的基础，并表示在四台服务器上有80000个并发用户的典型组织。

### <a name="persistent-chat-server-performance-user-model"></a>持久聊天服务器性能用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>连接的活动用户数</p></td>
<td><p>80000</p></td>
</tr>
<tr class="even">
<td><p>持久聊天服务器服务实例的数量</p></td>
<td><p>4 </p></td>
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
<td><p>16000用户</p></td>
</tr>
<tr class="even">
<td><p>聊天室的总数</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>小聊天室的数量</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>中聊天室的数量</p></td>
<td><p>1067</p></td>
</tr>
<tr class="odd">
<td><p>大聊天室的数量</p></td>
<td><p>10  </p></td>
</tr>
<tr class="even">
<td><p>每个用户的聊天室总数</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>每个用户的小聊天室数量</p></td>
<td><p>12 </p></td>
</tr>
<tr class="even">
<td><p>每个用户的中聊天室数量</p></td>
<td><p>双面</p></td>
</tr>
<tr class="odd">
<td><p>每个用户的大聊天室数量</p></td>
<td><p>双面</p></td>
</tr>
<tr class="even">
<td><p>每个用户加入的聊天室数</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>峰值加入速率</p></td>
<td><p>10/秒</p></td>
</tr>
<tr class="even">
<td><p>总聊天速率</p></td>
<td><p>24/秒</p></td>
</tr>
<tr class="odd">
<td><p>小聊天室的聊天速率</p></td>
<td><p>22.22/秒</p></td>
</tr>
<tr class="even">
<td><p>中聊天室的聊天速率</p></td>
<td><p>1.67/秒</p></td>
</tr>
<tr class="odd">
<td><p>大聊天室的聊天速率</p></td>
<td><p>~ 0.15/秒</p></td>
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
<td><p>Active Directory 域服务中的平均祖先隶属关系数</p></td>
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
<td><p>每个用户的平均可见聊天室数</p></td>
<td><p>2.25 (50%，共1个会议室，50% 为2个会议室) ;最多6个会议室打开，每个显示器一个</p></td>
</tr>
<tr class="even">
<td><p>每个时间间隔轮询的参与者数量</p></td>
<td><p>每个可见聊天室25个</p></td>
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
<td><p>6 </p></td>
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

