---
title: 基于位置的路由会议的要求
TOCTitle: 基于位置的路由会议的要求
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56271162
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 基于位置的路由会议的要求

 

_**上一次修改主题：** 2016-12-08_

以下是安装和配置基于位置的路由会议应用程序时必须满足的要求：

  - 必须在您的拓扑中的所有服务器或池上部署 Lync Server 2013 累积更新 2。

> [!NOTE]  
> 如果您的拓扑中的 Lync 服务器或池未安装 Lync Server 2013 累积更新 2 或更高版本，则无法确保能够强制实施 Lync 会议的基于位置的路由。



  - Lync Server 2013 基于位置的路由是基于位置的路由会议应用程序的先决条件。有关配置 Lync Server 2013 基于位置的路由的详细信息，请参阅[配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。

  - 基于位置的路由会议应用程序的要求与 Lync Server 2013 基于位置的路由的要求相同。有关详细信息，请参阅[规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)。

## 支持的服务器

基于位置的路由会议应用程序要求在您的拓扑中的所有前端池和 Standard Edition Server 上部署 Lync Server 2013 累积更新 2。如果您的拓扑中的某些 Lync Server 上未安装 Lync Server 2013 累积更新 2，则无法对 Lync 会议和咨询呼叫转接完全强制实施基于位置的路由限制。

下表介绍了支持基于位置的路由的服务器角色和版本的组合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>前端池版本</p></td>
<td><p>中介服务器版本</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Lync Server 2013 累积更新 1</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新 1</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


## 支持的客户端

支持 Lync 会议基于位置的路由的 Lync 客户端与支持 Lync Server 2013 基于位置的路由的客户端相同。有关详细信息，请参阅[基于位置的路由的客户端和服务器支持](lync-server-2013-client-and-server-support-for-location-based-routing.md)。

## 咨询呼叫转接的中介服务器要求

基于位置的路由会议应用程序要求部署独立的中介服务器，以便对咨询呼叫转接强制实施基于位置的路由限制。

要对咨询呼叫转接强制实施基于位置的路由，中介服务器必须仅与需要基于位置的路由的网络区域中的一个中介服务器对等方（例如，PBX、SIP 网关等）相关联。如果在相同网络区域中部署了其他中介服务器对等方，则该中介服务器对等方必须与不同的中介服务器相关联。下面详细介绍了此要求：

  - 当咨询呼叫转接通过一个中介服务器路由到中介服务器对等方并且该中介服务器配置了至多个对等方（例如，PBX 和网关）的多个 SIP 中继时，多个中介服务器对等方使用单个中介服务器；如果咨询呼叫转接允许通过一些 SIP 中继执行，但不允许通过其他 SIP 中继执行，则咨询呼叫转接将被阻止，以防止 PSTN 收费绕路情形。
    
    例如，如果单个中介服务器为 PSTN 网关中介服务器对等方和 PBX 中介服务器对等方提供服务，则将观察到以下行为：
    
      - 当给定站点（如站点 1）中的 Lync 用户试图通过咨询转接将与 PSTN 终结点进行的呼叫转接给不同站点（如站点 2）中的 Lync 用户时，不允许该呼叫，以防止 PSTN 收费绕路情形。
    
      - 当给定站点（如站点 1）中的 Lync 用户试图通过咨询转接将与相同站点（如站点 1）中的 PBX 终结点进行的呼叫转接给不同站点（如站点 2）中的 Lync 用户时，即使不会发生潜在的 PSTN 收费绕路情形，也不允许该呼叫。

  - 每个中介服务器对等方使用单独的中介服务器
    
    当咨询转接的目标是中介服务器对等方时，将根据中介服务器所服务的单个中介服务器对等方对咨询转接进行评估。无论单独的中介服务器为站点中的所有其他中介服务器对等方提供服务时这些对等方如何，将根据是否可能发生 PSTN 收费绕路情形来禁止或允许呼叫。
    
    例如，如果单独的中介服务器为 PSTN 网关中介服务器对等方和 PBX 中介服务器对等方提供服务，则将观察到以下行为：
    
      - 当给定站点（如站点 1）中的 Lync 用户试图通过咨询转接将与 PSTN 终结点进行的呼叫转接给不同站点（如站点 2）中的 Lync 用户时，不允许该呼叫，以防止 PSTN 收费绕路情形。
    
      - 当给定站点（如站点 1）中的 Lync 用户试图通过咨询转接将与相同站点（如站点 1）中的 PBX 终结点进行的呼叫转接给不同站点（如站点 2）中的 Lync 用户时，如果不会发生潜在的 PSTN 收费绕路情形则允许该呼叫。

## 基于位置的路由会议应用程序不支持的功能

基于位置的路由会议应用程序不支持以下功能：

  - 不能为电话拨入式会议强制实施基于位置的路由。即使会议组织是启用了基于位置的路由的 Lync 用户，给定会议的任何拨入请求也不受基于位置的路由限制。

  - 建议不要在需要强制实施基于位置的路由的区域中设置会议访问号码。

