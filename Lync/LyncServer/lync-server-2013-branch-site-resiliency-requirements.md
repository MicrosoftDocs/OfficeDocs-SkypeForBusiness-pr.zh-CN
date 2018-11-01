---
title: Lync Server 2013：分支站点恢复能力要求
TOCTitle: 分支站点恢复能力要求
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412772(v=OCS.15)
ms:contentKeyID: 49313819
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的分支站点恢复能力要求

 

_**上一次修改主题：** 2015-03-09_

本主题将帮助您为用户准备分支站点恢复能力和语音邮件生存能力，并且还会指定相关的软硬件要求。

## 为分支用户准备分支站点恢复能力

通过将用户的注册器池设置为 Survivable Branch Appliance (SBA) 或 Survivable Branch Server，为用户准备分支站点恢复能力。

## 分支用户的注册器分配

无论选择哪个分支站点恢复能力解决方案，您都需要将主注册器分配给每个用户。分支站点用户应始终在分支站点上的注册器中注册，无论该注册器位于 Survivable Branch Appliance、 Survivable Branch Server 还是独立 Lync Server 2013 Standard 或 Enterprise Edition Server 中。需要域名系统 (DNS) 服务 (SRV) 资源记录，客户端才能发现其注册器池。如果 Survivable Branch Appliance 变得无法使用，分支站点客户端将通过该记录自动发现备份注册器。

如果分支站点没有 DNS 服务器，则有两种备用方法可以配置 Survivable Branch Appliance 或 Survivable Branch Server 的发现：

  - 将分支站点的动态主机配置协议 (DHCP) 服务器上的 DHCP 选项 120 配置为指向 Survivable Branch Appliance 或 Survivable Branch Server 的完全限定域名 (FQDN)。

  - 将 Survivable Branch Appliance 或 Survivable Branch Server 配置为响应 DHCP 120 查询。

## 分支用户的语音路由

我们建议您为分支站点中的用户创建单独的用户级别 IP 语音 (VoIP) 策略。该策略应该包括一个使用 Survivable Branch Appliance 或分支服务器网关的主路由，以及一个或多个使用中央站点带公用电话交换网 (PSTN) 网关的中继的备份路由。如果主路由不可用，则将改用使用一个或多个中央站点网关的备份路由。这样，不管是在分支站点注册器还是在中央站点的备份注册器池中注册用户，用户的 VoIP 策略将始终有效。这对于处理故障转移的情况是很重要的。例如，如果您需要重命名 Survivable Branch Appliance 或将 Survivable Branch Appliance 重新配置为连接到中央站点上的备份注册器池，则在此期间，您必须将分支站点用户移到中央站点。（有关重命名或重新配置 Survivable Branch Appliance 的详细信息，请参阅部署文档中的[附录 B：在 Lync Server 2013 中管理 Survivable Branch Appliance](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md)。）如果这些用户没有制定用户级别的 VoIP 策略或用户级别的拨号计划，那么在这些用户移到其他站点时，默认情况下，中央站点的站点级别 VoIP 策略和站点级别拨号计划（而非分支站点的站点级别的 VoIP 策略和拨号计划）将会应用到这些用户。在这种情况下，除非备份注册器池所用的站点级别 VoIP 策略和站点级别拨号计划也能应用到这些分支站点用户，否则他们的呼叫将失败。例如，如果某个位于日本的分支站点上的用户移到位于雷蒙德的中央站点上，那么，其规范化规则是在所有 7 位数字呼叫之前附加 +1425 的拨号计划就可能不会采用适当的方式转换对这些用户的呼叫。

> [!IMPORTANT]  
> 创建分支机构备份路由时，建议将两个 PSTN 电话用法记录添加到分支机构用户策略中，并为每个记录分配单独的路由。第一个路由（主路由）会将呼叫定向到与 Survivable Branch Appliance (SBA) 或分支服务器关联的网关；第二个路由（备份路由）会将呼叫定向到中央站点上的网关。在定向呼叫时，SBA 或分支服务器会在尝试所有分配给第一个 PSTN 用法记录的路由后，再尝试第二个用法记录。


为了有助于确保在分支网关或 Survivable Branch Appliance 站点的 Windows 组件不可用时（例如， Survivable Branch Appliance 或分支网关停机维护时），对分支站点用户的入站呼叫能够到达这些用户，请在网关上创建故障转移路由（或与外线直拨分机 (DID) 提供商合作）将传入呼叫重定向到中央站点上的备份注册器池。在此处，呼叫将会通过 WAN 链路路由到分支用户。请确保路由会转换这些号码以符合 PSTN 网关要求或其他中继对等方接受的电话号码格式。有关创建故障转移路由的详细信息，请参阅 [在 Lync Server 2013 中配置故障转移路由](lync-server-2013-configuring-a-failover-route.md)。另外，您还可以为与分支站点网关相关联的中继创建服务级别拨号计划，以规范化传入呼叫。如果您在分支站点上有两个 Survivable Branch Appliance，则可以为它们创建一个站点级别的拨号计划，除非必须为它们各自单独创建一个拨号计划。

> [!NOTE]  
> 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点进行注册。当前对分支站点用户（包括在 Survivable Branch Appliance 中注册的用户）的数量没有限制。



我们还建议您创建一个用户级别的拨号计划和语音策略，然后将它分配给分支站点用户。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)和 [在 Lync Server 2013 中为分支用户创建 VoIP 路由策略](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)。

## 路由分机号

为分支站点用户准备拨号计划和语音策略时，务必添加与 msRTCSIP-line（或线路 URI）属性中使用的字符串和号码格式匹配的规范化规则和转换规则，以便让在分支站点用户和中央站点用户之间启用的 Lync 2013 呼叫可以正确路由，尤其是在呼叫因为 WAN 链路不可用而必须通过 PSTN 重新路由时。此外，还需要特别注意包括分机号的已拨号码，而不只是电话号码。

与包含分机号（无论是只包含一个完整的 E.164 电话号码还是包含其他的电话号码）的线路 URI 匹配的标准化规则和转换规则还有其他要求。本节介绍了为带分机号的线路 URI 路由呼叫的几种示例情况。

如果您的组织没有为单个用户配置外线直拨分机 (DID) 电话号码，并且每个用户的线路 URI *只* 配置了一个分机号，则内部用户只需拨打分机号即可相互呼叫。但是，您必须配置规范化规则，并且这些规则要能应用到与这些分机号相匹配的从分支站点用户发给中央站点用户的呼叫。

如果分支站点和中央站点之间的 WAN 链路可用，那么分支站点用户发给中央站点用户的呼叫就无需通过匹配的规范化规则来转换号码，因为该呼叫不会通过 PSTN 来路由。例如：


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
<th>规则名称</th>
<th>说明</th>
<th>号码模式</th>
<th>转换</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>不要转换 5 位数字</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>$1</p></td>
<td><p>10001 无法转换</p></td>
</tr>
</tbody>
</table>


您还必须针对特定的方案考虑分机号，如分支站点和中央站点之间的 WAN 链路不可用，以及必须通过 PSTN 路由来自分支站点的呼叫等情况。在 WAN 链路中断期间，如果分支站点用户只通过拨打中央站点用户的分机号来呼叫中央站点用户，则您必须制定一个可添加中央站点用户的完整电话号码的出站转换规则。如果用户的线路 URI 包含了组织完整的电话号码和用户唯一的分机号（非用户唯一的完整电话号码），则您必须制定改为添加组织的完整电话号码的出站转换规则。例如：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>匹配模式</th>
<th>转换</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>将 5 位数号码转换为用户的电话号码和分机号</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550123;ext=$1</p></td>
<td><p>10001 将转换为 +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>将 5 位数号码转换为组织的电话号码和用户分机号</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550100;ext=$1</p></td>
<td><p>10001 将转换为 +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


在这种情况下，如果处理 PSTN 重新路由任务的中继对等方不支持分机号，则出站转换规则还必须删除分机号。例如：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>匹配模式</th>
<th>转换</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>从包含分机号的电话号码中删除分机号</p></td>
<td><p>^\+(\d*);ext=(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 将转换为 +14255550123</p></td>
</tr>
</tbody>
</table>


无论 WAN 链路是否可用，如果组织没有为单个用户配置 DID 号码，并且用户的线路 URI 包含组织电话号码和用户唯一的分机号，则您必须为组织的电话号码线路 URI 配置可由分支站点中继对等方或 PSTN 网关接通的号码。您还必须配置组织的电话号码线路 URI，为路由到该号码的呼叫添加自己的唯一分机号。

有关在 WAN 链路不可用时中央站点用户向分支站点用户发送呼叫的详细信息，请参阅本主题后面的“准备语音邮件生存能力”。有关拨号规则和标准化规则的详细信息（包括其他示例规则），请参阅规划文档中的[Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)和部署文档中的[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)。有关出站转换规则的详细信息，请参阅规划文档中的[Lync Server 2013 中的转换规则](lync-server-2013-translation-rules.md)和部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。

## 准备语音邮件生存能力

Exchange 统一消息 (UM) 通常仅安装在中央站点上，而不会安装在分支站点上。即使分支站点和中央站点之间的 WAN 链路不可用，呼叫者也应能够留下语音邮件。因此，除了适用于相关语音邮件号码的语音策略、拨号计划和规范化规则之外，在为可向分支站点用户提供语音邮件的 Exchange UM 自动助理电话号码配置线路 URI 时也需要特别注意。

Survivable Branch Appliance (SBA) 和 Survivable Branch Server 会在 WAN 中断期间为分支用户提供语音邮件生存能力。具体来说，如果您使用的是 Survivable Branch Appliance 或 Survivable Branch Server，并且 WAN 变得无法使用，则 SBA 或 Survivable Branch Server 会通过 PSTN 将未应答的呼叫重新路由至中央站点上的 Exchange UM。通过 SBA 或 Survivable Branch Server，用户还可以在 WAN 中断期间通过 PSTN 取回语音邮件。最后，在 WAN 中断期间， Survivable Branch Appliance 或 Survivable Branch Server 会将未接来电通知进行排队，然后在 WAN 还原时将它们上载到 Exchange UM 服务器。为了有助于确保语音邮件重新路由具有良好的适应性，则一定要将中央站点池 FQDN 的条目和 边缘服务器 FQDN 的条目添加到 Survivable Branch Server 上的主机文件中。否则，在分支站点上没有 DNS 服务器的情况下，DNS 解析可能会超时。

我们建议使用以下配置为分支站点用户配置语音邮件生存能力：

  - Microsoft Exchange 管理员应将 Exchange UM 自动助理 (AA) 配置为仅接受邮件。该配置禁用所有其他常规功能（例如，转接给用户或转接给操作员）并将 AA 限制为仅接受邮件。或者，Exchange 管理员也可以使用常规 AA 或自定义 AA 将呼叫路由至操作员。

  - Lync Server 管理员应获取 AA 电话号码，并将该电话号码用作 Survivable Branch Appliance 或分支服务器的语音邮件重新路由设置中的“Exchange UM 自动助理”号码。

  - Lync Server 管理员应获取 Exchange UM 订阅者访问电话号码并将该号码用作 Survivable Branch Appliance 或 Survivable Branch Server 的语音邮件重新路由设置中的“订阅者访问”号码。

  - Lync Server 管理员应配置 Exchange UM，以便只有一个拨号计划与在 WAN 中断期间需访问语音邮件的所有分支用户关联。

  - 当 WAN 链路不可用时，向分支站点用户发送的呼叫可以路由到用户的 Exchange 统一消息 (UM) 语音邮箱，但还必须满足以下条件，即应用到该呼叫的语音策略指定的语音邮件电话号码是唯一的并且不含分机号。

## 分支站点恢复能力的软硬件要求

根据您的恢复能力解决方案，软硬件要求可能会有所不同。

## Survivable Branch Appliance 的要求

所需软硬件内置在 Survivable Branch Appliance 中。但是，我们还是建议每个分支站点部署 DHCP 服务器以获取客户端 IP 地址；否则，当 DHCP 租赁到期时，客户端将失去 IP 连接。

如果企业 DNS 服务器仅位于中央站点，则在 WAN 中断期间，分支站点用户将无法连接到这些服务器，因此，使用 DNS SRV（服务 (SRV) 资源记录）的 Lync Server 发现将失败。要确保在 WAN 中断期间提示重新路由，必须在分支站点上缓存 DNS 记录。如果分支路由器支持 DNS 缓存，则为分支路由器启用 DNS 缓存。或者，可以在分支上部署 DNS 服务器。此服务器可以是独立服务器，也可以是支持 DNS 功能的 Survivable Branch Appliance 版本。有关详细信息，请联系您的 Survivable Branch Appliance 提供商。

> [!NOTE]  
> 分支站点中不必有域控制器。 Survivable Branch Appliance 使用特殊证书对客户端进行身份验证，当客户端登录时，它会将该证书发送给客户端以响应客户端的证书请求。



Lync 客户端可使用 DHCP 选项 120（SIP 注册器选项）发现 Lync Server。可通过以下两种方法之一配置该功能：

  - 在分支站点上配置 DHCP 服务器来答复 DHCP 120 查询，这会返回 Survivable Branch Appliance 或 Survivable Branch Server 上的注册器的 FQDN。

  - 打开 Lync Server DHCP。打开该功能后， Lync Server 注册器会响应 DHCP 选项 120 查询。请注意，该注册器不会响应除 DHCP 选项 120 之外的任何 DHCP 查询。

此外，对于具有多个子网的大型分支站点，应启用 DHCP 中继代理来将 DHCP 选项 120 查询转发给 DHCP 服务器（配置 1）或注册器（配置 2）。

最后，必须为 企业语音配置分支站点用户，且必须使用适当的统一通信终结点进行设置。

## Survivable Branch Server 的要求

Survivable Branch Server 的要求与任何 前端服务器 服务器角色的要求相同。有关详细信息，请参阅规划文档中的 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

## 全面部署 Lync Server 分支站点的要求

有关详细信息，请参阅规划文档中的 [确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)。

