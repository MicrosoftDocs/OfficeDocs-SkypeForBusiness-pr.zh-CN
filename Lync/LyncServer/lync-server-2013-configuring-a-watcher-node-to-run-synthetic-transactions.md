---
title: 'Lync Server 2013: 配置观察程序节点以运行合成事务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>将观察程序节点配置为在 Lync Server 2013 中运行合成事务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-07_

安装 System Center agent 文件后, 必须接下来配置观察程序节点本身。 配置观察程序节点所采取的步骤会有所不同, 具体取决于观察程序节点计算机是在外围网络内部还是在外围网络外部。

配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。 Lync Server 2013 允许你选择两种身份验证方法之一: 受信任的服务器或凭据身份验证。 下表概述了这两种方法之间的差异:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>配置</th>
<th>说明</th>
<th>支持的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>受信任服务器</p></td>
<td><p>使用证书可模拟内部服务器并绕过身份验证质询。</p>
<p>这对希望管理单个证书而不是每个观察程序节点上的多个用户密码的管理员非常有用。</p></td>
<td><p>企业内部。</p>
<p>请注意, 利用此方法, 观察程序节点必须与受监视的池位于同一个域中。 如果观察程序节点和监视的池位于不同的域中, 请改用凭据身份验证。</p></td>
</tr>
<tr class="even">
<td><p>凭据身份验证</p></td>
<td><p>将用户名和密码安全地存储在每个观察程序节点的 Windows 凭据管理器中。</p>
<p>此模式需要更多的密码管理, 但对于位于企业外的观察程序节点, 这是唯一的选择。 不能将这些观察程序节点视为经过身份验证的受信任终结点。</p></td>
<td><p>企业外部。</p>
<p>企业内部。</p></td>
</tr>
</tbody>
</table>


你还应验证你的防火墙是否具有适用于 MonitoringHost 和 PowerShell 的入站规则。 如果防火墙阻止了这些进程, 则合成事务将失败, 并出现 504 (服务器超时) 错误。

</div>

<span> </span>

</div>

</div>

</div>

