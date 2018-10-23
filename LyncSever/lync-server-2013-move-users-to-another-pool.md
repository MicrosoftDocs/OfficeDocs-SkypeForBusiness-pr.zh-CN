---
title: 在 Lync Server 2013 中将用户移至另一个池
TOCTitle: 在 Lync Server 2013 中将用户移至另一个池
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182600(v=OCS.15)
ms:contentKeyID: 49314576
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将用户移至另一个池

 

_**上一次修改主题：** 2013-03-11_

可使用 Lync Server 控制面板将用户分配给特定服务器或池。

> [!TIP]
> 将所有现有用户从运行 Microsoft Office Communications Server 2007 R2 或更早版本的源池移至复杂的 Active Directory 环境中的 Lync Server 2013 目标池可能会导致 Active Directory 复制速度变慢。要避免此问题，可使用搜索筛选器单独移动运行 Microsoft Office Communications Server 2007 R2 或更早版本的池中的部分用户，也可以使用 Lync Server 命令行管理程序通过 cmdlet 移动用户。另外，Lync Server 2013 用户也可以使用筛选器功能。


## 将所选用户移至其他服务器或池

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5.  在表中，选择列表中的一个或多个特定用户。

6.  在“操作”菜单中，单击“将所选用户移动到池”。

7.  在“移动用户”的“目标注册器池”中，选择要将用户移动到的池。

8.  （可选）如果目标服务器或池不可用，则选中“强制”复选框。
    
    > [!WARNING]
    > 如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议）。如果不选中，将同时移动帐户和关联数据。


## 将所有用户从一个服务器或池移至另一个服务器或池

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“操作”菜单中，单击“将所有用户移动到池”。

5.  在“移动用户”的“源注册器池”中，选择包含要移动的用户帐户的池。

6.  在“目标注册器池”中，选择要将用户移动到的池。

7.  （可选）如果目标服务器或池不可用，则选中“强制”复选框。
    
    > [!WARNING]
    > 如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议）。如果不选中，将同时移动帐户和关联数据。


## 使用筛选器将用户从一个池移至另一个池

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“用户搜索”中，单击“搜索”，单击“添加筛选器”。

5.  在搜索条件中，依次选择“注册器池”、“等于”和“当前池 FQDN”，然后单击“查找”。

6.  在“操作”菜单上，单击“将所有用户移动到池”。
    
    > [!NOTE]  
    > 将筛选器应用于现有用户组时，选项“将所有用户移动到池”出现在经过筛选的用户子集上下文中，而不是出现在<strong><em>所有</em></strong> 可能的用户上下文中。
    


7.  在“移动用户”的“源注册器池”中，选择包含要移动的用户帐户的池。

8.  在“目标注册器池”中，选择要将用户移动到的池。

9.  （可选）如果目标服务器或池不可用，则选中“强制”复选框。
    
    > [!WARNING]
    > 如果选中“强制”，将移动用户帐户，但会删除任何关联的用户数据（例如，用户已安排的会议和联系人）。如果不选中，将同时移动帐户和关联数据。


## 使用 Lync 命令行管理程序将用户从一个池移至另一个池

1.  根据运行 Windows PowerShell 命令的方式（本地还是远程），需要按如下方式以正确 Lync Server 2013 管理角色成员的身份登录：
    
    1.  如果您要在本地计算机上运行命令（例如，直接登录前端服务器）：以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。
    
    2.  如果您要在另一台计算机上远程运行命令（例如，登录您的计算机并在 Standard Edition 前端服务器上远程运行命令）：使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  若要移动单个用户，请按如下方式使用 Move-CsUser cmdlet：
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    其中，要移动的用户是用户 Pilar Ackerman，该用户将从当前分配的主池移至 pool01.contoso.net 池

4.  若要移动大量用户，请将筛选器与 **Get-CsUser** cmdlet 配合使用，并将生成的用户组传递给 **Move-CsUser**：
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Get-CsUser** 和 **Move-CsUser** 命令结合使用时可能如下所示：
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

## 另请参阅

#### 其他资源

[修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)

