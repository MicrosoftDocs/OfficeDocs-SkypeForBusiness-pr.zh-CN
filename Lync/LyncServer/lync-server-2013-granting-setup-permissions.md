---
title: Lync Server 2013：授予安装权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授予安装权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-08-27_

你可以使用**CsSetupPermission** cmdlet 向指定的 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 组添加读取、写入、ReadSPN 和 WriteSPN 权限。 然后, 该 OU 中的 RTCUniversalServerAdmins 组的成员可以在指定域中安装运行 Lync Server 2013 的服务器, 而不是域管理员组的成员。

使用**CsSetupPermission** cmdlet 验证你通过使用**CsSetupPermission** cmdlet 设置的权限。

你可以使用**CsSetupPermission** cmdlet 删除你使用**CsSetupPermission** cmdlet 授予的权限。

<div>

## <a name="to-grant-setup-permissions"></a>授予设置权限

1.  在要授予设置权限的域中登录到运行 Lync Server 2013 的计算机。 如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    你可以将 ComputerOu 参数指定为相对于指定域的默认命名上下文 (例如, CN = 计算机)。 或者, 你可以将此参数指定为完整的 OU 可分辨名称 (DN) (例如, "CN = 计算机, DC = Contoso, DC = com")。 在后一种情况下, 你必须指定与你指定的域一致的 OU DN。
    
    如果不指定 Domain 参数, 则默认值为本地域。

</div>

<div>

## <a name="to-verify-setup-permissions"></a>验证设置权限

1.  在要验证使用**CsSetupPermission** cmdlet 授予的设置权限的域中, 登录到运行 Lync Server 2013 的计算机。 如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    你可以将 ComputerOu 参数指定为相对于指定域的默认命名上下文 (例如, CN = 计算机)。 或者, 你可以将此参数指定为完整的 OU 可分辨名称 (DN) (例如, "CN = 计算机, DC = Contoso, DC = com")。 在后一种情况下, 你必须指定与你指定的域一致的 OU DN。
    
    如果不指定 Domain 参数, 则默认值为本地域。

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>撤销设置权限

1.  在要吊销**CsSetupPermission** cmdlet 授予的设置权限的域中, 登录到运行 Lync Server 2013 的计算机。 如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    你可以将 ComputerOu 参数指定为相对于指定域的默认命名上下文 (例如, CN = 计算机)。 或者, 你可以将此参数指定为完整的 OU 可分辨名称 (DN) (例如, "CN = 计算机, DC = Contoso, DC = com")。 在后一种情况下, 你必须指定与你指定的域一致的 OU DN。
    
    如果不指定 Domain 参数, 则默认值为本地域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

