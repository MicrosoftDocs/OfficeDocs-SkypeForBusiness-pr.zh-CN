---
title: 在 Skype for Business 中部署网络区域、网站和子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: '在 Skype for Business 服务器中创建或修改网络区域、网络站点和关联网络子网。 所有这些都用于高级企业语音功能: "绕过媒体"、"呼叫许可控制" 和 "基于位置的路由"。'
ms.openlocfilehash: c4fdf8649c866aa63134f7d4fa28e70e68809f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291198"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>在 Skype for Business 中部署网络区域、网站和子网

在 Skype for Business 服务器中创建或修改网络区域、网络站点和关联网络子网。 所有这些都用于高级企业语音功能: "绕过媒体"、"呼叫许可控制" 和 "基于位置的路由"。

高级企业语音功能是[call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)、[media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)、[ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)和 [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)。 这些功能全都需要您创建网络区域、网络站点和子网。 例如，所有这些功能都要求拓扑中的每个子网与特定网络站点关联，每个网络站点必须与网络区域关联。 有关这些项目的更多信息，请参阅[Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)

呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：

- 呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定带宽策略配置文件。 如果你计划部署呼叫许可控制, 则必须先[在 Skype For Business 服务器中创建带宽策略配置文件](create-bandwidth-policy-profiles.md), 然后再配置你的网络站点。

- E9-1-1 要求为每个站点指定位置策略。 如果你计划部署 E9-1, 则必须先[在 Skype For Business Server 中创建位置策略](create-location-policies.md), 然后才能配置你的网络网站。

## <a name="create-or-modify-a-network-region"></a>创建或修改网络区域

如果你已为这些功能之一创建了网络区域, 则无需创建新的网络区域;其他高级企业语音功能将使用相同的网络区域。

但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>使用 Skype for Business 服务器命令行管理程序创建网络区域

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 运行 New-CsNetworkRegion cmdlet 创建网络区域：

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    在此示例中, 你创建了一个名为 "北美洲" 的网络区域, 该区域与具有网站 ID 芝加哥的中心网站相关联。

3. 要为拓扑完成网络区域的创建，请使用每个网络区域的设置重复步骤 2。

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板创建网络区域

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“网络配置”****。

3. 单击“区域”****。

4. 单击“新建”****。

5. 在“新建区域”**** 页上，单击“名称”****，然后键入网络区域的名称。

6. 单击“中央站点”****，然后单击列表中的某个中央站点。

7. 或者，单击“说明”****，然后键入其他信息以描述此网络站点。

8. 单击“**提交**”。

9. 要为拓扑完成网络区域的创建，请使用其他区域的设置重复步骤 4 至 8。

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>使用 Skype for Business 服务器命令行管理程序修改网络区域

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 运行 Set-CsNetworkRegion cmdlet 修改现有网络区域：

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    在此示例中, 您修改了一个名为 "北美" 的现有网络区域 (使用本主题前面的过程创建), 方法是更改说明。 如果 "北美洲" 区域的说明存在, 此命令将使用此值覆盖它;如果未设置任何说明, 则此命令将设置它。

3. 要修改其他网络区域，请使用其他区域的设置重复步骤 2。

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板修改网络区域

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“网络配置”****。

3. 单击“区域”**** 导航按钮。

4. 在表中，单击要修改的网络区域。

5. 单击“编辑”****，然后单击“显示详细信息...”****。

6. 在 "**编辑区域**" 页面上, 根据需要更改此网络区域的设置的值。

7. 单击“**提交**”。

8. 要完成网络区域的修改，请使用其他区域的设置重复步骤 4 至 7。

## <a name="create-or-modify-a-network-site"></a>创建或修改网络站点

如果你已为这些功能之一创建了网络网站, 则不需要创建新的网络网站;其他高级企业语音功能将使用相同的网络站点。 但是，可能需要修改现有的网络站点定义来应用特定于功能的设置。 例如，如果已为 E9-1-1 创建了网络站点，则需要在部署呼叫允许控制的过程中修改该网络站点，以便应用带宽策略配置文件。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business 服务器命令行管理程序创建网络站点

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 运行 New-CsNetworkSite cmdlet 创建网络站点：

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    例如：

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    在此示例中, 你创建了一个名为 "芝加哥" 的网络网站, 该网站位于 "北美" 网络区域中。

    > [!NOTE]
    > 为了成功运行此命令，NorthAmerica 网络区域必须已经存在。

3. 要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 2。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板创建网络网站

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“网络配置”****。

3. 单击“站点”**** 导航按钮。

4. 单击“新建”****。

5. 在“新建站点”**** 页上，单击“名称”****，然后键入网络站点的名称。

6. 单击“区域”****，然后单击列表中的某个区域。

7. 或者，单击“带宽策略”****，然后单击列表中的某个带宽策略。

    > [!NOTE]
    > 只有在站点上部署呼叫允许控制时才需要带宽策略。

8. 或者，单击“位置策略”****，然后单击列表中的某个位置策略。

    > [!NOTE]
    > 只有在站点上部署 E9-1-1 时才需要位置策略。

9. 或者，单击“说明”****，然后键入其他信息以描述此网络站点。

10. 单击“**提交**”。

11. 要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 4 至 10。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business 服务器命令行管理程序修改网络站点

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 运行 Set-CsNetworkSite cmdlet 修改网络站点：

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    例如：

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    在此示例中, 名为 "伯克基" 的网站将被移动到 "北美" 网络区域。 要修改网络站点配置以部署呼叫允许控制、E9-1-1 或媒体旁路，请分别运行带有 BWPolicyProfileID 参数或 LocationPolicy 参数的 Set-CsNetworkSite cmdlet 来修改网络站点设置。

    > [!NOTE]
    > 尽管存在用于媒体旁路的 BypassID 参数，但强烈建议您不要覆盖自动生成的旁路 ID。您无需指定其他参数来为媒体旁路配置网络站点。

3. 要为拓扑完成网络站点的修改，请使用其他站点的设置重复步骤 2。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板修改网络站点

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“网络配置”****。

3. 单击“站点”**** 导航按钮。

4. 在表中，单击要修改的网络站点。

5. 单击“编辑”****，然后单击“显示详细信息...”****。

6. 在 "**编辑网站**" 页面上, 根据需要更改此网络网站的设置的值。

7. 单击“**提交**”。

8. 要完成网络站点的修改，请使用其他站点的设置重复步骤 4 至 7。

## <a name="associate-a-subnet-with-a-network-site"></a>将子网与网络站点相关联
<a name="BKMK_AssociateSubnets"> </a>

你的网络中的每个子网都必须与特定的网络站点相关联, 因为子网信息用于确定在启动新会话时终结点所在的网络站点。 当会话中每个方的位置已知时, 高级企业语音功能可以应用该信息来确定如何处理呼叫设置或路由。

必须将部署中音频/视频边缘服务器的所有已配置公用 IP 地址添加到网络配置设置中。 这些 IP 地址是作为掩码为 32 的子网进行添加的。 关联的网络站点应与相应的已配置网络站点相对应。 例如, 与中央站点芝加哥的 A/V 边缘服务对应的公共 IP 地址将为 NetworkSiteID 芝加哥。

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序将子网与网络站点相关联

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 运行 **New-CsNetworkSubnet** cmdlet 将子网与网络站点相关联：

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    例如：

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    在此示例中, 你在子网172.11.12.13 和网络站点 "芝加哥" 之间创建了关联。

3. 为拓扑中的所有子网重复步骤 2。

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>通过导入 CSV 文件将子网与网络站点关联

1. 创建包含要添加的所有子网的 CSV 文件。例如，创建名为 **subnet.csv** 并包含以下内容的文件：

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

3. 运行以下 cmdlet 以导入**子网 .csv**, 然后将其内容存储在 Lync Server 管理存储中:

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板将子网与网络站点相关联

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“网络配置”****。

3. 单击“子网”**** 导航按钮。

4. 单击“新建”****。

5. 在“新建子网”**** 页上，单击“子网 ID”****，然后键入由要与网络站点关联的子网定义的 IP 地址范围中的第一个地址。

6. 单击“掩码”****，然后键入要应用于子网的位掩码。

7. 单击“网络站点 ID”****，然后选择要向其中添加此子网的站点的站点 ID。

    > [!NOTE]
    > 如果尚未创建网络站点，该列表将为空。 有关过程的详细信息，请参阅 [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)。 还可以通过运行 **Get-CsNetworkSite** cmdlet 检索部署的站点 ID。 有关详细信息, 请参阅 Skype for Business 服务器管理外壳文档。

8. （可选）单击“说明”****，然后键入其他信息来说明此子网。

9. 单击“**提交**”。

重复这些步骤以向网络站点中添加其他子网。
> [!NOTE]
> 生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点相关联。 该警报在 8 小时内只产生一次。

相关的警报信息和示例如下所示：

 **来源**：CS 带宽策略服务（核心）

 **事件编号**：36034

 **级别**：2

 **说明**: 以下 ip 地址的子网: \<ip 地址\>列表未配置或子网未与网络站点关联。

 **原因**：网络配置设置中缺少相应 IP 地址的子网，或子网未与网络站点相关联。

 **解决方案**：将与 IP 地址列表对应的子网添加到网络配置设置中，并将每个子网与一个网络站点相关联。

例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题：

1. 确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 相关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 相关联。

2. 确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点相关联。

## <a name="see-also"></a>另请参阅
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

