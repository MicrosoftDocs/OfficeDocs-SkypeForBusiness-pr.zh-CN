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
ms.openlocfilehash: c4ecadb2a487dc17f18e1956b6ac075e25b0b035
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500549"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a>在 Lync Server 2013 中将用户移动到另一个池

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2018-02-09_

您可以使用 Lync Server 控制面板将用户分配到特定的服务器或池。

<div>


> [!TIP]  
> 若要将所有现有用户从运行 Lync Server 2010 或更早版本的源池中移到复杂的 Active Directory 环境中的 Lync Server 2013 目标池，可能会导致 Active Directory 复制速度较慢。 若要避免这种情况，可以使用搜索筛选器从运行 Lync Server 2010 或更低版本的池中移动用户，也可以使用 Lync Server 命令行管理程序移动 cmdlet 中的用户。 此外，筛选器功能适用于 Lync Server 2013 用户。



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>将所选用户移至其他服务器或池

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中，选择列表中的一个或多个特定用户。

6.  在“操作”**** 菜单中，单击“将所选用户移动到池”****。

7.  在“移动用户”**** 的“目标注册器池”**** 中，选择要将用户移动到的池。

8.  （可选）如果目标服务器或池不可用，则选中“强制”**** 复选框。
    
    <div>
    

    > [!Caution]  
    > 如果选择 " <STRONG>强制</STRONG>"，则将移动用户帐户，但不会移动相关用户数据（例如，计划会议和联系人）。

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>将所有用户从一个服务器或池移至另一个服务器或池

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在“操作”**** 菜单上，单击“将所有用户移动到池”****。

5.  在“移动用户”**** 的“源注册器池”**** 中，选择包含要移动的用户帐户的池。

6.  在“目标注册器池”**** 中，选择要将用户移动到的池。

7.  （可选）如果目标服务器或池不可用，则选中“强制”**** 复选框。
    
    <div>
    

    > [!Caution]  
    > 如果选择 " <STRONG>强制</STRONG>"，则将移动用户帐户，但不会移动相关用户数据（例如，计划会议和联系人）。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>使用筛选器将用户从一个池移至另一个池

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在 " **用户搜索**" 中，单击 " **搜索**"，然后单击 " **添加筛选器**"。

5.  在搜索条件中，依次选择“注册器池”****、“等于”**** 和“当前池 FQDN”****，然后单击“查找”****。

6.  在“操作”**** 菜单上，单击“将所有用户移动到池”****。
    
    <div>
    

    > [!NOTE]  
    > 将筛选器应用于现有用户集时，选项 " <STRONG>将所有用户移动到池</STRONG> " 位于已筛选的用户子集的上下文中，而不是 <STRONG><EM>所有</EM></STRONG> 可能的用户。

    
    </div>

7.  在“移动用户”**** 的“源注册器池”**** 中，选择包含要移动的用户帐户的池。

8.  在“目标注册器池”**** 中，选择要将用户移动到的池。

9.  （可选）如果目标服务器或池不可用，则选中“强制”**** 复选框。
    
    <div>
    

    > [!Caution]  
    > 如果选择 " <STRONG>强制</STRONG>"，则将移动用户帐户，但不会移动相关用户数据（例如，计划会议和联系人）。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 将用户从一个池移动到另一个池

1.  根据您在本地或远程) 运行 Windows PowerShell 命令的方式 (，您需要以正确的 Lync Server 2013 管理角色的成员身份登录，如下所示：
    
    1.  如果您运行的是本地计算机上的命令 (例如，直接登录到前端服务器) ：登录到安装了 Lync Server 命令行管理程序的计算机，或使用 [Lync server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限。
    
    2.  如果您在另一台计算机上远程运行命令 (例如，您登录到计算机并在 Standard Edition 前端服务器上远程运行命令) ：从分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  若要移动单个用户，请按如下方式使用 Move-CsUser cmdlet：
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    其中，要移动的用户是用户 Pilar Ackerman，该用户将从当前分配的主池移至 pool01.contoso.net 池

4.  若要移动大量用户，请将筛选器与 **Get-CsUser** cmdlet 配合使用，并将生成的用户组传递给 **Move-CsUser**：
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Get-CsUser** 和 **Move-CsUser** 命令结合使用时可能如下所示：
    
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

