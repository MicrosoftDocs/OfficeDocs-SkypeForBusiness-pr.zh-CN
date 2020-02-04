---
title: Lync Server 2013：创建或修改网络子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络子网

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

为了确定属于该子网的主机的地理位置，网络子网必须与网络站点相关联。 可以使用 Lync Server "控制面板" 配置子网。 从 Lync Server 控制面板中，您可以创建、修改或删除网络子网。 有关删除网络子网的详细信息，请参阅[在 Lync Server 2013 中删除网络子网](lync-server-2013-deleting-network-subnets.md)。

在大多数部署呼叫许可控制（CAC）的 Microsoft Lync Server 2013 中，通常会有大量子网。 因此，通常最好从 Lync Server 命令行管理程序中配置子网。 从这里，你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。 通过将这些 cmdlet 结合使用，你可以从逗号分隔值（.csv）文件中读取子网设置，并同时创建多个子网。 有关如何从 .csv 文件创建子网的示例，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-create-a-network-subnet"></a>创建网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。

4.  在 "**子网**" 页面上，单击 "**新建**"。

5.  在 "**新建子网**" 中，在 "**子网 ID** " 字段中输入值。 这必须是 IP 地址（例如，174.11.12.0），并且它必须是子网定义的 IP 地址范围中的第一个地址。

6.  在 "**掩码**" 字段中，输入从1到32的数字值。
    
    <div>
    

    > [!NOTE]  
    > 此值是要应用到正在创建的子网的位掩码。

    
    </div>

7.  在 "**网络站点 ID**" 中，选择此子网所属的站点。

8.  可选在 "**说明**" 字段中键入一个值，以提供有关无法单独以名称表示的该子网的详细信息。

9.  单击“**提交**”。

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>修改网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。

4.  在 "**子网**" 页面上，单击要修改的子网。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑子网**" 页面上，您可以修改位掩码、关联的网络站点或说明。 如果您修改了位掩码，请记住子网 ID 必须仍然是子网定义的 IP 地址范围中的第一个地址。

7.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除网络子网](lync-server-2013-deleting-network-subnets.md)  


[关于 Lync Server 2013 中的网络区域、站点和子网](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

