---
title: Lync Server 2013：配置基于位置的路由
TOCTitle: 配置基于位置的路由
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994036(v=OCS.15)
ms:contentKeyID: 52061040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置基于位置的路由

 

_**上一次修改主题：** 2015-03-09_

Lync Server 2013 CU1 基于位置的路由是企业语音的一项功能。基于位置的路由是一项呼叫管理功能，控制 Lync Server 2013 CU1 如何路由呼叫。它强制实施有关是否可以基于 Lync 呼叫者的位置将呼叫路由到 PBX 或 PSTN 目标的限制。基于位置的路由基于呼叫者的网络位置对 PSTN 呼叫应用呼叫授权规则。呼叫者的位置基于与呼叫者所连接的网络子网相关联的网络站点进行确定。配置基于位置的路由要求首先部署企业语音，然后配置网络区域、站点和子网。这为基于位置的路由奠定基础。

在部署基于位置的路由之前，您必须首先部署企业语音，配置网络区域、站点，并将网络子网与您的网络站点相关联。完成后，您可以配置基于位置的路由。有关如何配置网络区域、站点和子网的步骤，请参阅[在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

此部分通过以下示例指导您如何配置基于位置的路由。

![企业语音基于位置的路由示例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "企业语音基于位置的路由示例")

  
下表代表此示例中定义的用户。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>终结点类型</th>
<th>位置</th>
<th>用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>德里公司办公室</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>海德拉巴公司办公室</p></td>
<td><p>HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>未知（如酒店）</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>德里公司办公室</p></td>
<td><p>DEL-PBX-1、DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>海德拉巴公司办公室</p></td>
<td><p>HYD-PBX-1、HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>未知</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

下表代表此示例环境中阐释的系统。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>系统</th>
<th>位置</th>
<th>名称</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 池</p></td>
<td><p>任意</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1、中介服务器</p></td>
<td><p>任意</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 网关 1</p></td>
<td><p>德里</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 网关 2</p></td>
<td><p>海德拉巴</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>德里</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>海德拉巴</p></td>
<td><p>RED-PBX</p></td>
</tr>
</tbody>
</table>


## 本部分内容

  - [在 Lync Server 2013 中配置企业语音](lync-server-2013-configuring-enterprise-voice.md)

  - [在 Lync Server 2013 中部署网络区域、站点和子网](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [在 Lync Server 2013 中启用基于位置的路由](lync-server-2013-enabling-location-based-routing.md)

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

