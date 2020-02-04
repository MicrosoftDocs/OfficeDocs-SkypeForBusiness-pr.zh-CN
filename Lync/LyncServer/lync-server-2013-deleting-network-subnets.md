---
title: Lync Server 2013：删除网络子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中删除网络子网

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

可以使用以下过程删除子网。 从 Lync Server 控制面板中，您可以创建、修改或删除网络子网。 有关创建或修改网络子网的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)。

在大多数部署呼叫许可控制（CAC）的 Microsoft Lync Server 2013 中，通常会有大量子网。 因此，通常最好从 Lync Server 命令行管理程序中配置子网。 从这里，你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。 通过将这些 cmdlet 结合使用，你可以从逗号分隔值（.csv）文件中读取子网设置，并同时创建多个子网。 有关如何从 .csv 文件创建子网的示例，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-delete-a-network-subnet"></a>删除网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**子网**"。

4.  在 "**子网**" 页面上，单击要删除的子网。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个子网。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个子网。 或者，若要选择所有子网，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  在 "**编辑**" 菜单上，单击 "**删除**"。

6.  单击“**确定**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

