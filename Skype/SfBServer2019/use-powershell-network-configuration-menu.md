---
title: 使用 PowerShell 执行"网络配置"菜单上的任务
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 摘要：Skype for Business Server"网络配置"菜单的"控制面板"映射到 Cmdlet。
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626053"
---
# <a name="network-configuration"></a>网络配置

本文介绍如何使用 cmdlet 实现与旧版控制面板中的"网络配置"菜单项类似的结果。

本文介绍了以下子菜单：

- [网络配置](#network-configuration)
  - [位置策略](#location-policy)
  - [带宽策略](#bandwidth-policy)
  - [Region](#region)
  - [Site](#site)
  - [Subnet](#subnet)
  - [区域链接](#region-link)
  - [区域路由](#region-route)

## <a name="location-policy"></a>位置策略

" **位置策略** "子菜单用于应用与 E9-1-1 功能相关的设置。 位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。

让我们考虑用户可在位置策略上执行的各种任务，Skype for Business映射到的 cmdlet。 

---

> **方案 1：** 列出所有位置策略

   ![列表位置策略](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***示例***

```powershell
 Get-CsLocationPolicy
```

---

> **方案 2：** 创建新的位置策略

   ![创建位置策略](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***示例***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **方案 3：** 获取所选位置策略的详细信息

   ![获取位置策略](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***示例***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **方案 4：** 删除所选位置策略

   ![删除位置策略](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***示例***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **方案 5：** 更新位置策略

   ![更新位置策略](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***示例***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>带宽策略

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。  (在Skype for Business Server中，只能为音频和视频形式分配带宽限制。) 此 cmdlet 会为这些策略创建容器配置文件。 调用此 cmdlet 时，可以通过指定音频和视频带宽限制来定义容器内的各个策略。

让我们考虑用户可在带宽策略上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有带宽策略

   ![列出带宽策略](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***示例***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **方案 2：** 创建新的带宽策略

   ![新带宽策略](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***示例***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **方案 3：** 获取所选带宽策略的详细信息

   ![获取带宽策略](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***示例***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **方案 4：** 删除所选的带宽策略

   ![删除带宽策略](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***示例***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **方案 5：** 更新带宽策略

   ![更新带宽策略](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***示例***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>区域

网络区域将跨多个地理区域的网络的各个部分相互连接起来。 每个网络区域都必须与中央站点关联。 管理员可以使用 **"区域** "菜单管理有关一个或多个网络区域的信息，包括确定是否允许音频和视频连接使用备用路径以及将区域内的站点与媒体旁路配置相关联的中央站点和设置。

---

> **方案 1：** 列出所有区域

   ![列表区域](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***示例***

```powershell
 Get-CsNetworkRegion
```

---

> **方案 2：** 创建新区域

   ![创建区域](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***示例***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **方案 3：** 获取选定区域的详细信息

   ![获取区域](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***示例***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **方案 4：** 删除所选区域

   ![删除区域](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***示例***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **方案 5：** 更新区域

   ![更新区域](./media/network-region-5.png)

- **批注 1 - 结果**

    图像上的此批注指示结果，即检索和显示的数据。

    ***Cmdlet***

    [来自 Region 的 Get-CsNetworkSite](/powershell/module/skype/get-csnetworksite)

    ***示例***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **批注 2 - (选项)**

    图像上的此注释指示用户实现的选项，即保存网络区域。

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***示例***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Site

网络站点是指在部署了 CAC 或 E9-1-1 的每个区域中配置的办公室或位置。 **"** 网站"子菜单可帮助管理员添加、删除或管理其设置。

让我们考虑用户可在 **SITE** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有网站

   ![列表网站](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***示例***

```powershell
 Get-CsNetworkSite
```

---

> **方案 2：** 创建新网站

   ![创建网站](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***示例***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **方案 3：** 获取所选网站的详细信息

   ![获取网站](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***示例***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **方案 4：** 删除所选网站

   ![删除网站](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***示例***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **方案 5：** 更新网站

   ![更新网站](./media/network-site-5.png)

- **批注 1 - 结果**

    图像上的此批注指示结果，即检索和显示的数据。

    ***Cmdlet***

    [来自站点的 Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

    ***示例***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **批注 2 - (选项)**

    图像上的此注释指示用户实现的选项，即保存网络站点。

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***示例***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>子网

管理员可以使用 **"子网** "子菜单来创建、更新和管理网络子网。

让我们考虑用户可在 **子网** 上执行的各种任务，以及这些任务Skype for Business cmdlet 映射到的 cmdlet。

---

> **方案 1：** 列出所有子网

   ![列出子网](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***示例***

```powershell
 Get-CsNetworkSubnet
```

---

> **方案 2：** 创建新子网

   ![创建子网](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***示例***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **方案 3：** 获取所选子网的详细信息

   ![获取子网](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***示例***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **方案 4：** 删除所选子网

   ![删除子网](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***示例***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **方案 5：** 更新子网

   ![更新子网](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***示例***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>区域链接

网络内的区域通过物理 WAN 连接进行链接。管理员可以使用" **区域链接** "子菜单来创建、更新和管理网络子网。

让我们考虑用户可在"区域链接"上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有区域链接

   ![列表区域链接](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***示例***

```powershell
 Get-CsNetworkRegionLink
```

---

> **方案 2：** 创建新区域链接

   ![创建区域链接](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***示例***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **方案 3：** 获取所选区域链接的详细信息

   ![获取区域链接](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***示例***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **方案 4：** 删除所选区域链接

   ![删除区域链接](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***示例***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **方案 5：** 更新区域链接

   ![更新区域链接](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***示例***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>区域路由

CAC 配置中的每个区域都必须有某种方式以访问其他每个区域。 虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但是路由可确定连接从一个区域到另一个区域将遍历的链接路径。 管理员可以使用" **区域路由** "子菜单创建、更新和管理这些子菜单。

让我们考虑用户可在"区域路由"上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有区域路由

   ![列出区域路由](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***示例***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **方案 2：** 创建新的区域路由

   ![创建区域路由](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***示例***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **方案 3：** 获取所选区域路由的详细信息

   ![获取区域路由](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***示例***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **方案 4：** 删除所选区域路由

   ![删除区域路由](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***示例***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **方案 5：** 更新区域路由

   ![更新区域路由](./media/network-regionroute-5.png)

- **批注 1 - (选项)**

    图像上的此批注指示结果，即检索和显示的数据。

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***示例***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **批注 2 - (选项)**

    该图像上的此注释指示用户可实现的选项，即保存网络区域路由。

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***示例***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
