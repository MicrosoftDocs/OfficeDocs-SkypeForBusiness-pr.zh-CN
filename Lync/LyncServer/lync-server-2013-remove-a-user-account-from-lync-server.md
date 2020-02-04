---
title: Lync Server 2013：从 Lync Server 中删除用户帐户
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
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>从 Lync Server 2013 中删除用户帐户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-22_

你可以使用以下过程在 Lync Server 2013 中删除以前添加的用户帐户。

<div>


> [!NOTE]  
> 删除用户将导致你丢失为用户帐户配置的任何设置。 如果想要暂时禁用用户帐户，请参阅<A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">禁用或重新启用 Lync Server 2013 的用户帐户</A>主题。



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序删除用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**搜索用户**" 框中，键入要禁用或重新启用的用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。

5.  在表中，单击要删除的用户帐户。

6.  在 "**操作**" 菜单上，选择 "**从 Lync Server 中删除**"，将出现一个对话框。

7.  从对话框中，选择 **"确定"** 以删除用户。

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除用户帐户

你可以使用 Move-csuser cmdlet 删除用户帐户。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从远程会话 Windows PowerShell 运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-user-account"></a>删除用户帐户

  - 若要删除用户帐户，请使用 Disable-Move-csuser cmdlet。 例如：
    
        Disable-CsUser -Identity "Ken Myer"
    
    此命令运行后，无法重新启用帐户及其以前的设置。 相反，你需要使用 Enable-Move-csuser cmdlet 为 Ken Myer 创建全新帐户。

</div>

有关详细信息，请参阅 Disable cmdlet 的帮助主题[move-csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) 。

</div>

<div>

## <a name="see-also"></a>另请参阅


[禁用或重新启用 Lync Server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

