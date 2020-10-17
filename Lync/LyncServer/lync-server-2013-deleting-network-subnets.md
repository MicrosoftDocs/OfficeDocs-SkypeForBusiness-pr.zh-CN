---
title: Lync Server 2013：删除网络子网
description: Lync Server 2013：删除网络子网。
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
ms.openlocfilehash: 6635ec99b68c4ceb10d1cda343fef35c951bf152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557878"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中删除网络子网

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

您可以使用以下过程删除子网。 在 Lync Server 控制面板中，您可以创建、修改或删除网络子网。 有关创建或修改网络子网的详细信息，请参阅 [在 Lync Server 2013 中创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)。

在 Microsoft Lync Server 2013 的大多数部署中，呼叫允许控制 (CAC) ，通常会有大量子网。 因此，通常最好从 Lync Server 命令行管理程序中配置子网。 在这里，可以将 **CsNetworkSubnet** 与 Windows PowerShell Cmdlet **导入-CSV**结合在一起调用。 通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。 有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-delete-a-network-subnet"></a>删除网络子网

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“子网”****。

4.  在“子网”**** 页上，单击要删除的子网。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个子网。为执行此操作，请按住 CTRL 键，同时选择多个子网。或者，要选择所有子网，请单击“编辑”<STRONG></STRONG>菜单上的“全选”<STRONG></STRONG>。

    
    </div>

5.  在“编辑”**** 菜单中，单击“删除”****。

6.  单击“确定”****。

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

