---
title: Lync Server 2013：从 Lync Server 中删除用户帐户
description: Lync Server 2013：从 Lync Server 中删除用户帐户。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201eb8a7ba620792b92e2c7983890047c249ce86
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555748"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a>从 Lync Server 2013 中删除用户帐户

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

您可以使用以下过程在 Lync Server 2013 中删除之前添加的用户帐户。

<div>


> [!NOTE]  
> 移除用户将导致您丢失为用户帐户配置的所有设置。 如果要暂时禁用用户帐户，请参阅主题 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">disable or 重新启用 Lync Server 2013 的用户帐户</A>。



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序删除用户帐户

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中，单击要移除的用户帐户。

6.  在“操作”**** 菜单上，选择“从 Lync Server 中删除”****，然后将出现一个对话框。

7.  从该对话框中，选择“确定”**** 来移除该用户。

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除用户帐户

您可以使用 Disable-CsUser cmdlet 删除用户帐户。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或远程会话 Windows PowerShell 中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-user-account"></a>删除用户帐户

  - 若要移除用户帐户，请使用 Disable-CsUser cmdlet。例如：
    
        Disable-CsUser -Identity "Ken Myer"
    
    在此命令运行后，没有办法重新启用该帐户及其以前的设置。您将需要使用 Enable-CsUser cmdlet 为 Ken Myer 创建全新的帐户。

</div>

有关详细信息，请参阅 [get-csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 禁用或重新启用用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[为 Lync Server 2013 启用和禁用用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

