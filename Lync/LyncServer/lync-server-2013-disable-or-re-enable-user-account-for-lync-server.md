---
title: 'Lync Server 2013: 禁用或重新启用 Lync Server 的用户帐户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>禁用或重新启用 Lync Server 2013 的用户帐户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-04-04_

可以使用以下过程在 Lync Server 2013 中禁用以前启用的用户帐户, 而不会丢失为用户帐户配置的 Lync 服务器设置。 由于您不会丢失 Lync Server 用户帐户设置, 因此您可以重新启用以前启用的用户帐户, 而无需重新配置用户帐户。

<div>


> [!WARNING]  
> 仅在 Active Directory 中禁用用户帐户<STRONG>不会</STRONG>阻止用户登录或使用 Lync Server。 这是因为 Lync 使用可优化身份验证过程的证书身份验证, 并且这些客户证书在180天内有效。 如果你想要停止禁用已为 Lync 访问 Lync Server 而启用的 Active Directory 帐户, 则必须使用<STRONG>move-csuser</STRONG> cmdlet, 或使用<STRONG>Lync server 控制面板</STRONG>, 如本文中所述。 一旦用户在 Lync 中处于禁用状态, 并且中央管理存储已复制到用户将无法再登录的环境中。 同样, 已登录用户将断开连接。



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>为 Lync Server 禁用或重新启用以前启用的用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**搜索用户**" 框中, 键入要禁用或重新启用的用户帐户的全部或第一部分的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名称、SIP 地址或行统一资源标识符 (URI)。然后单击 "**查找**"。

5.  在表中, 单击要禁用或重新启用的用户帐户。

6.  在 "**操作**" 菜单上, 执行下列操作之一:
    
      - 若要暂时禁用 Lync Server 2013 的用户帐户, 请单击 " **Lync Server 暂时禁用**"。
    
      - 若要启用 Lync Server 2013 的用户帐户, 请单击 " **Lync Server 重新启用**"。

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows PowerShell 禁用或重新启用用户帐户

用户帐户可以暂时禁用, 然后在稍后通过使用**move-csuser** cmdlet 重新启用。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-disable-a-user-account"></a>禁用用户帐户

  - 若要暂时禁用用户帐户, 请将 Enabled 属性的值设置为 False ($False)。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>重新启用用户帐户

  - 若要重新启用已禁用的用户帐户, 请将 Enabled 属性的值设置为 True ($True)。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

有关详细信息, 请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 添加和启用用户帐户](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

