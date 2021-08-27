---
title: 在站点部署网络区域、站点和Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 创建或修改网络区域、网络站点，并关联网络Skype for Business Server。 所有这些功能都用于高级企业语音功能：媒体旁路、呼叫允许控制和基于位置的路由。
ms.openlocfilehash: 5c9105dd49afaaeeba1925859357b801cb252cb4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604251"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>在站点部署网络区域、站点和Skype for Business

创建或修改网络区域、网络站点，并关联网络Skype for Business Server。 所有这些功能都用于高级企业语音功能：媒体旁路、呼叫允许控制和基于位置的路由。

高级企业语音包括[呼叫允许](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)控制、[媒体旁](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)路、基于位置的[路由](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)和[E9-1-1。](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md) 这些功能都要求创建网络区域、网络站点和子网。 例如，所有这些功能都要求拓扑中的每个子网与特定网络站点关联，并且每个网络站点必须与一个网络区域关联。 有关这些术语详细信息，请参阅 network [settings for the advanced 企业语音 features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)。

呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：

- 呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定带宽策略配置文件。 如果计划部署呼叫允许控制，则必须在部署网络[](create-bandwidth-policy-profiles.md)站点Skype for Business Server创建带宽策略配置文件。

- E9-1-1 要求为每个站点指定位置策略。 如果计划部署 E9-1-1，则必须在部署[](create-location-policies.md)网络站点Skype for Business Server创建位置策略。

## <a name="create-or-modify-a-network-region"></a>创建或修改网络区域

如果已经为这些功能之一创建了网络区域，则无需创建新的网络区域;其他高级企业语音功能将使用相同的网络区域。

但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server网络区域

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 运行 New-CsNetworkRegion cmdlet 创建网络区域：

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    此示例创建了一个称为"NorthAmerica"的网络区域，该区域与站点 ID 为 CHICAGO 的中央站点相关联。

3. 要为拓扑完成网络区域的创建，请使用每个网络区域的设置重复步骤 2。

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>使用控制面板创建Skype for Business Server区域

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“网络配置”。

3. 单击“区域”。

4. 单击“新建”。

5. 在“新建区域”页上，单击“名称”，然后键入网络区域的名称。

6. 单击“中央站点”，然后单击列表中的某个中央站点。

7. 或者，单击“说明”，然后键入其他信息以描述此网络站点。

8. 单击“提交”。

9. 要为拓扑完成网络区域的创建，请使用其他区域的设置重复步骤 4 至 8。

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server网络区域

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 运行 Set-CsNetworkRegion cmdlet 修改现有网络区域：

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    在此示例中，您修改了一个称为"NorthAmerica"的现有网络区域 (使用本主题前面介绍的过程通过更改) 创建的区域。 如果"NorthAmerica"区域存在说明，此命令会用此值覆盖它;如果尚未设置说明，则此命令将设置它。

3. 要修改其他网络区域，请使用其他区域的设置重复步骤 2。

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>使用控制面板修改Skype for Business Server区域

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“网络配置”。

3. 单击“区域”导航按钮。

4. 在表中，单击要修改的网络区域。

5. 单击“编辑”，然后单击“显示详细信息...”。

6. 在 **"编辑区域** "页上，根据情况更改此网络区域设置的值。

7. 单击“提交”。

8. 要完成网络区域的修改，请使用其他区域的设置重复步骤 4 至 7。

## <a name="create-or-modify-a-network-site"></a>创建或修改网络站点

如果已针对这些功能之一创建了网络站点，则无需创建新的网络站点;其他高级企业语音功能将使用相同的网络站点。 但是，可能需要修改现有的网络站点定义来应用特定于功能的设置。 例如，如果已为 E9-1-1 创建网络站点，则需要在部署呼叫允许控制的过程中修改该网络站点，以便应用带宽策略配置文件。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序创建Skype for Business Server站点

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 运行 New-CsNetworkSite cmdlet 创建网络站点：

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    例如：

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    本示例中，您创建了一个称为"Chicago"的网络站点，该站点位于"NorthAmerica"网络区域。

    > [!NOTE]
    > 为了成功运行此命令，NorthAmerica 网络区域必须已经存在。

3. 要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 2。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用控制面板创建Skype for Business Server站点

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“网络配置”。

3. 单击“站点”导航按钮。

4. 单击“新建”。

5. 在“新建站点”页上，单击“名称”，然后键入网络站点的名称。

6. 单击“区域”，然后单击列表中的某个区域。

7. 或者，单击“带宽策略”，然后单击列表中的某个带宽策略。

    > [!NOTE]
    > 只有在站点上部署呼叫允许控制时才需要带宽策略。

8. 或者，单击“位置策略”，然后单击列表中的某个位置策略。

    > [!NOTE]
    > 只有在站点上部署 E9-1-1 时才需要位置策略。

9. 或者，单击“说明”，然后键入其他信息以描述此网络站点。

10. 单击“提交”。

11. 要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 4 至 10。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序修改Skype for Business Server站点

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 运行 Set-CsNetworkSite cmdlet 修改网络站点：

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    例如：

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    此示例中，名为"Albuquerque"的站点将移动到"NorthAmerica"网络区域。 要修改网络站点配置以部署呼叫允许控制、E9-1-1 或媒体旁路，请分别运行带有 BWPolicyProfileID 参数或 LocationPolicy 参数的 Set-CsNetworkSite cmdlet 来修改网络站点设置。

    > [!NOTE]
    > 尽管存在用于媒体旁路的 BypassID 参数，但强烈建议您不要覆盖自动生成的旁路 ID。您无需指定其他参数来为媒体旁路配置网络站点。

3. 要为拓扑完成网络站点的修改，请使用其他站点的设置重复步骤 2。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用控制面板修改Skype for Business Server站点

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“网络配置”。

3. 单击“站点”导航按钮。

4. 在表中，单击要修改的网络站点。

5. 单击“编辑”，然后单击“显示详细信息...”。

6. 在 **"编辑站点** "页上，根据情况更改此网络站点的设置的值。

7. 单击“提交”。

8. 要完成网络站点的修改，请使用其他站点的设置重复步骤 4 至 7。

## <a name="associate-a-subnet-with-a-network-site"></a>将子网与网络站点关联
<a name="BKMK_AssociateSubnets"> </a>

网络内每个子网都必须与特定网络站点关联，因为子网信息用于确定启动新会话时终结点所在的网络站点。 当会话每一方的位置已知时，高级企业语音功能可以应用该信息来确定如何处理呼叫设置或路由。

必须将部署中音频/视频边缘服务器的所有已配置公共 IP 地址添加到网络配置设置中。 这些 IP 地址是作为掩码为 32 的子网进行添加的。 关联的网络站点应与相应的已配置网络站点相对应。 例如，与中央站点芝加哥的 A/V 边缘服务对应的公用 IP 地址是 NetworkSiteID Chicago。

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序将子网与Skype for Business Server关联

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 运行 **New-CsNetworkSubnet** cmdlet 将子网与网络站点相关联：

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    例如：

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    此示例在子网 172.11.12.13 和网络站点"Chicago"之间创建了关联。

3. 为拓扑中的所有子网重复步骤 2。

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>通过导入 CSV 文件将子网与网络站点关联

1. 创建包含要添加的所有子网的 CSV 文件。例如，创建名为 **subnet.csv** 并包含以下内容的文件：

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

3. 运行以下 cmdlet 以导入 **subnet.csv，** 然后将其内容存储在 Lync Server 管理存储中：

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用控制面板将子网与网络站点Skype for Business Server关联

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“网络配置”。

3. 单击“子网”导航按钮。

4. 单击“新建”。

5. 在“新建子网”页上，单击“子网 ID”，然后键入由要与网络站点关联的子网定义的 IP 地址范围中的第一个地址。

6. 单击“掩码”，然后键入要应用于子网的位掩码。

7. 单击“网络站点 ID”，然后选择要向其中添加此子网的站点的站点 ID。

    > [!NOTE]
    > 如果尚未创建网络站点，该列表将为空。 有关过程的详细信息，请参阅[Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)。 还可以通过运行 **Get-CsNetworkSite** cmdlet 检索部署的站点 ID。 有关详细信息，请参阅 Skype for Business Server命令行管理程序文档。

8. （可选）单击“说明”，然后键入其他信息来说明此子网。

9. 单击“提交”。

重复这些步骤以向网络站点中添加其他子网。
> [!NOTE]
> 生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点相关联。 该警报在 8 小时内只产生一次。

相关的警报信息和示例如下所示：

 **源**：CS 带宽策略服务（核心）

 **事件数**：36034

 **级别**：2

 **说明**：未配置以下 IP 地址的子网，或者 \<List of IP Addresses\> 子网未与网络站点关联。

 **原因**：网络配置设置中缺少相应 IP 地址的子网，或子网未与网络站点相关联。

 **解决方案**：将与 IP 地址列表对应的子网添加到网络配置设置中，并将每个子网与一个网络站点相关联。

例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题：

1. 确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 相关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 相关联。

2. 确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点关联。

## <a name="see-also"></a>另请参阅
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)