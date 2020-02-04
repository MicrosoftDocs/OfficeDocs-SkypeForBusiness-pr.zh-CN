---
title: Lync Server 2013：将用户移动到另一个池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>在 Lync Server 2013 中将用户移动到另一个池中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2018-02-09_

可以使用 Lync Server 控制面板将用户分配到特定的服务器或池。

<div>


> [!TIP]  
> 将所有现有用户从运行 Lync Server 2010 或更早版本的源池中移动到复杂的 Active Directory 环境中的 Lync Server 2013 目标池可能会导致 Active Directory 复制速度较慢。 为避免这种情况，您可以使用搜索筛选器从运行 Lync Server 2010 或更早版本的池中移动用户，也可以使用 Lync Server Management Shell 将用户与 cmdlet 一起移动。 此外，筛选器功能适用于 Lync Server 2013 用户。



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>将所选用户移动到其他服务器或池

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**搜索用户**" 框中，键入所需用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。

5.  在表中，选择列表中的特定用户或用户。

6.  在 "**操作**" 菜单上，单击 "**将所选用户移至池**"。

7.  在 "**移动用户**" 中，选择要将用户移动到 "**目标注册机构" 池中**的池。

8.  可选如果目标服务器或池不可用，请选中 "**强制**" 复选框。
    
    <div>
    

    > [!Caution]  
    > 如果您选择 "<STRONG>强制</STRONG>"，则用户帐户将被移动，但相关联的用户数据（如计划的会议和联系人）不会移动。

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>将所有用户从一个服务器或池移动到另一个服务器或池

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**操作**" 菜单上，单击 "**将所有用户移至池**"。

5.  在 "**移动用户**" 中，选择包含要在**源注册机构池中**移动的用户帐户的池。

6.  在 "**目标注册机构" 池中**，选择要将用户移动到的池。

7.  可选如果目标服务器或池不可用，请选中 "**强制**" 复选框。
    
    <div>
    

    > [!Caution]  
    > 如果您选择 "<STRONG>强制</STRONG>"，则用户帐户将被移动，但相关联的用户数据（如计划的会议和联系人）不会移动。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>使用筛选器将用户从一个池移动到另一个池

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**用户搜索**" 中，单击 "**搜索**"，然后单击 "**添加筛选器**"。

5.  在搜索条件中，选择 "**注册机构池**"，选择 "**等于**"，选择 "**当前池 FQDN**"，然后单击 "**查找**"。

6.  在 "**操作**" 菜单上，单击 "**将所有用户移至池**"。
    
    <div>
    

    > [!NOTE]  
    > 将筛选器应用于现有用户集时，选项 "<STRONG>将所有用户移至池中</STRONG>" 将位于已筛选的用户子集的上下文中，而不是<STRONG><EM>所有</EM></STRONG>可能的用户。

    
    </div>

7.  在 "**移动用户**" 中，选择包含要在**源注册机构池中**移动的用户帐户的池。

8.  在 "**目标注册机构" 池中**，选择要将用户移动到的池。

9.  可选如果目标服务器或池不可用，请选中 "**强制**" 复选框。
    
    <div>
    

    > [!Caution]  
    > 如果您选择 "<STRONG>强制</STRONG>"，则用户帐户将被移动，但相关联的用户数据（如计划的会议和联系人）不会移动。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 将用户从一个池移动到另一个池

1.  根据你运行的 Windows PowerShell 命令（本地或远程）的运行方式，你需要以正确的 Lync Server 2013 管理角色的成员身份登录，如下所示：
    
    1.  如果你在本地计算机上运行命令（例如，直接登录到前端服务器），请按照以下步骤登录到安装了 Lync Server Management Shell 的计算机（如 RTCUniversalServerAdmins 组的成员）或必要的用户权限（如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述）。
    
    2.  如果您在另一台计算机上远程运行命令（例如，登录到计算机并在标准版前端服务器上远程运行命令）：从分配给 CsUserAdministrator 角色或 CsAdministrator 的用户帐户。角色，请登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  若要移动单个用户，请使用 Move-csuser cmdlet，如下所示：
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    要移动的用户是用户 Pilar Ackerman，用户将从其当前分配的主池移动到该池 pool01.contoso.net

4.  若要移动大量用户，请将筛选器与**move-csuser** cmdlet 配合使用，并将生成的用户集传递到**move-csuser**：
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Move-csuser**和**move-csuser**的合并命令可能会导致以下情况：
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

