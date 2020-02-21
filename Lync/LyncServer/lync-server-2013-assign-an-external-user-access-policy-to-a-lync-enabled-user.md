---
title: Lync Server 2013：将外部用户访问策略分配给启用 Lync 的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612b872e0071e2ad3fa2d4d064048805a4e65953
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

如果已为用户启用 Lync Server，则可以通过将适当的策略应用于特定用户，在 Lync Server 控制面板中配置 SIP 联合身份验证、XMPP 联合身份验证、远程用户访问和公共即时消息（IM）连接。 例如，如果创建了一个支持远程用户访问的策略，则必须将其应用于用户，然后用户才能从远程位置连接到 Lync Server，并从远程位置与内部用户进行协作。

<div>


> [!NOTE]  
> 要支持外部用户访问，必须启用对要支持的每种外部用户访问类型的支持，并配置相应的策略及其他选项以控制其使用。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 中配置外部用户访问支持</A>或在操作文档中<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理联合身份验证和外部访问 lync server 2013</A> 。



</div>

使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>将外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑 Lync Server 用户”**** 中的“外部访问策略”**** 下，选择要应用的用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG> " 设置将应用默认服务器或全局策略设置。

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户外部访问策略

可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 分配每用户外部访问策略。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>向单个用户分配每用户外部访问策略

  - 此命令向用户 Ken Myer 分配每用户外部访问策略 RedmondExternalAccessPolicy。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>为多个用户分配每用户外部访问策略

  - 此命令向在 Active Directory 的 UnitedStates OU 中拥有帐户的所有用户分配每用户外部访问策略 USAExternalAccessPolicy。 有关此命令中使用的 OU 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 的相关文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>取消分配每用户外部访问策略

  - 此命令取消分配之前为 Ken Myer 分配的任何每用户外部访问策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

