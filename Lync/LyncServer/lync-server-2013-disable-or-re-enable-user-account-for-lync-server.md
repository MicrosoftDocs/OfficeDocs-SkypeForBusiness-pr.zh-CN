---
title: Lync Server 2013：为 Lync Server 禁用或重新启用用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 646f4ae59ce5058af84c0e5ddd3197f7a9f47fe7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528989"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>为 Lync Server 2013 禁用或重新启用用户帐户

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-04-04_

您可以使用以下过程在 Lync Server 2013 中禁用以前启用的用户帐户，而不会丢失为该用户帐户配置的 Lync Server 设置。 由于您不会丢失 Lync Server 用户帐户设置，因此您可以重新启用以前启用的用户帐户，而无需重新配置用户帐户。

<div>


> [!WARNING]  
> 仅在 Active Directory 中禁用用户帐户 <STRONG>不会</STRONG> 阻止用户登录或使用 Lync Server。 这是因为 Lync 使用可简化身份验证过程的证书身份验证，并且这些客户端证书在180天内有效。 如果要停止已为 Lync 启用的已启用的 Active Directory 帐户访问 Lync Server，则必须使用 <STRONG>get-csuser</STRONG> cmdlet，或使用此文章中列出的 <STRONG>lync server 控制面板</STRONG> 。 在 Lync 中禁用用户并在该环境中复制中央管理存储后，用户将无法再登录。 此外，已登录的用户将断开连接。



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>为 Lync Server 禁用或重新启用以前启用的用户帐户

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中，单击要禁用或重新启用的用户帐户。

6.  在“操作”**** 菜单上，执行下列操作之一：
    
      - 若要暂时禁用 Lync Server 2013 的用户帐户，请单击 "为 **Lync Server 暂时禁用**"。
    
      - 若要为 Lync Server 2013 启用用户帐户，请单击 " **为 Lync Server 重新启用**"。

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows PowerShell 禁用或重新启用用户帐户

可以暂时禁用用户帐户，然后再使用 **get-csuser** cmdlet 重新启用用户帐户。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-disable-a-user-account"></a>禁用用户帐户

  - 若要暂时禁用某一用户帐户，请将 Enabled 属性的值设置为 False ($False)。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>重新启用用户帐户

  - 若要重新启用已禁用的用户帐户，请将 Enabled 属性的值设置为 True ($True)。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

有关详细信息，请参阅 [get-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 添加和启用用户帐户](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[为 Lync Server 2013 启用和禁用用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

