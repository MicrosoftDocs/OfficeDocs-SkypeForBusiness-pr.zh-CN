---
title: Lync Server 2013：将存档策略应用于用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>将存档策略应用于 Lync Server 2013 中的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

如果用户已启用 Lync Server 2013，并且已为驻留在 Lync Server 2013 上的用户创建了一个或多个用户策略，则可以通过向这些用户或用户组应用相应的策略来实现对特定用户的存档支持。 例如，如果创建了支持内部通信存档的策略，则可以将其应用到至少一个用户或用户组以支持用户的 Lync Server 2013 通信的存档。

<div>


> [!NOTE]  
> 如果为你的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管于 Exchange 2013 的用户启用存档，并将其邮箱置于原地保留。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。<BR>在启用存档之前，应在存档配置中指定所有适当的选项。 有关详细信息，请参阅在<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中为你的组织、网站和池在操作文档中管理存档配置选项</A>。



</div>

使用本主题中的过程将以前创建的存档用户策略应用于一个或多个用户帐户或用户组。

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>将存档用户策略应用于用户帐户

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "在**存档策略**中**编辑 Lync 服务器用户**" 下，选择要应用的存档用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置。 服务器将自动应用这些设置。

    
    </div>

6.  单击“**提交**”。

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户存档策略

可以使用 Windows PowerShell 和**CsArchivingPolicy** cmdlet 分配每用户存档策略。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>将每用户存档策略分配给单个用户

  - 以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>将每用户存档策略分配给多个用户

  - 此命令将每用户存档策略 RedmondArchivingPolicy 分配给所有帐户驻留在注册机构池 atl-cs-001.litwareinc.com 的用户。 有关此命令中使用的筛选器参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 文档。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>分配每个用户的存档策略

  - 以下命令取消之前分配给 Ken Myer 的任何每用户存档策略。 取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

有关详细信息，请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 文档。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[在 Lync Server 2013 中分配每个用户的策略](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

