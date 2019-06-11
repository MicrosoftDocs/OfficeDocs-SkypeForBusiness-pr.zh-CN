---
title: Lync Server 2013：将外部用户访问策略分配到启用 Lync 的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

如果已启用 Lync Server 的用户, 则可以通过向特定用户应用适当的策略来在 Lync Server 控制面板中配置 SIP 联盟、XMPP 联盟、远程用户访问和公共即时消息 (IM) 连接。 例如, 如果你创建了支持远程用户访问的策略, 则必须先将其应用于用户, 然后用户才能从远程位置连接到 Lync 服务器, 并从远程位置与内部用户进行协作。

<div>


> [!NOTE]  
> 若要支持外部用户访问, 必须启用对要支持的每种类型的外部用户访问的支持, 并配置相应的策略和其他选项以控制其使用。 有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-configuring-support-for-external-user-access.md">配置 Lync server 2013 中的外部用户访问支持</A>或在操作文档中<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理 lync server 2013 的联合访问和外部访问</A>。



</div>

使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>将外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "在**外部访问策略**中**编辑 Lync 服务器用户**" 下, 选择要应用的用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 将应用默认服务器或全局策略设置。

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户外部访问策略

可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 分配每用户外部访问策略。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>将每用户外部访问策略分配给单个用户

  - 此命令将每用户外部访问策略 RedmondExternalAccessPolicy 分配给用户 Ken Myer。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>为多个用户分配每个用户的外部访问策略

  - 此命令将每用户外部访问策略 USAExternalAccessPolicy 分配给在 Active Directory 中的美国组织单位中拥有帐户的所有用户。 有关此命令中使用的 OU 参数的详细信息, 请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>取消分配每用户外部访问策略

  - 此命令取消之前分配给 Ken Myer 的任何每用户外部访问策略。 取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

有关详细信息, 请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

