---
title: 简介
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>简介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

Lync Server 2013 应力和性能工具 (称为 LyncPerfTool) 可模拟以下类型的用户负载:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>即时消息 (IM) 和状态</p></td>
<td><p>音频会议</p></td>
</tr>
<tr class="even">
<td><p>应用程序共享</p></td>
<td><p>IP 语音 (VoIP), 包括公共交换电话网络 (PSTN) 模拟</p></td>
</tr>
<tr class="odd">
<td><p>Web Access 客户端会议</p></td>
<td><p>Microsoft Lync 2013 助理</p></td>
</tr>
<tr class="even">
<td><p>响应组</p></td>
<td><p>通讯组列表扩展</p></td>
</tr>
<tr class="odd">
<td><p>通讯簿下载和通讯簿查询</p></td>
<td><p>增强的 9-1-1 (E9-1) 呼叫和位置配置文件 (拨号计划)</p></td>
</tr>
<tr class="even">
<td><p>重视</p></td>
<td><p>查看来自会议的多个流</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Lync Server 2013 应力和性能工具仅支持通过高级配置进行跨池负载生成和联盟。

该工具还不会模拟以下客户端的用户负载:

  - Office Live Meeting 2007

  - Lync 2013 持久聊天

因此, Lync Server 2013 应力和性能工具将不支持测试以下组件:

  - Lync 2013 持久聊天

  - Exchange 集成方案

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 应力和性能工具附带的应用程序和文件

Lync Server 2013 应力和性能工具中包含下列应用程序:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>工具</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool</p></td>
<td><p>Lync Server 2013 用户预配工具。 此工具用于创建用户和联系人。</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator</p></td>
<td><p>Lync Server 2013 加载配置工具。 此工具用于配置要模拟的用户负载的特征。</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool</p></td>
<td><p>Lync Server 2013 应力和性能工具。 LyncPerfTool 是模拟用户负载的工具。</p></td>
</tr>
<tr class="even">
<td><p>默认的 tmx</p></td>
<td><p>使用 Lync Server 2013 日志记录工具需要使用默认的 tmx。</p></td>
</tr>
<tr class="odd">
<td><p>预配脚本示例</p></td>
<td><p>这些示例用于根据特定方案配置用于运行负载测试的拓扑</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

