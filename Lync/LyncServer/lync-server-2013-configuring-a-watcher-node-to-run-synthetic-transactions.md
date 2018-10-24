---
title: 将观察程序节点配置为运行综合事务
TOCTitle: 将观察程序节点配置为运行综合事务
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205314(v=OCS.15)
ms:contentKeyID: 49314294
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将观察程序节点配置为运行综合事务

 

_**上一次修改主题：** 2015-03-09_

在安装 System Center 代理文件后，接下来必须配置观察程序节点本身。配置观察程序节点的步骤将因观察程序节点计算机位于外围网络内部还是外部而有所不同。

配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。Lync Server 2013 允许您选择以下两种身份验证方法中的一种：受信任的服务器或凭据身份验证。下表列出了两种方法间的差异：


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
<td><p>受信任的服务器</p></td>
<td><p>使用证书可模拟内部服务器并绕过身份验证质询。</p>
<p>这对于希望在每个观察程序节点管理单个证书而不是多个用户密码的管理员来说很有用。</p></td>
<td><p>企业内部。</p>
<p>请注意，采用这种方法时，观察程序节点必须与要监控的池位于同一个域中。如果观察程序节点与监控的池在不同的域中，请改用凭据身份验证。</p></td>
</tr>
<tr class="even">
<td><p>凭据身份验证</p></td>
<td><p>将用户名和密码安全地存储在每个观察程序节点的 Windows 凭据管理器中。</p>
<p>此模式需要更多密码管理，但它是位于企业外部的观察程序节点的唯一选择。不能将这些观察程序节点视为经过身份验证的受信任终结点。</p></td>
<td><p>企业外部。</p>
<p>企业内部。</p></td>
</tr>
</tbody>
</table>


您还应验证防火墙针对 MonitoringHost.exe 和 PowerShell.exe 具有入站规则。如果防火墙阻止这些进程，则综合事务将失败，显示 504（服务器超时）错误。

