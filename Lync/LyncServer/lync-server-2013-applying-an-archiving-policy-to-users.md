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
ms.openlocfilehash: 423eb8c4d96496f75f8702c5cf2ccf21a3b13b8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508919"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>在 Lync Server 2013 中向用户应用存档策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

如果已为用户启用 Lync Server 2013，并且已为驻留在 Lync Server 2013 上的用户创建了一个或多个用户策略，则可以通过向这些用户或用户组应用适当的策略来实现对特定用户的存档支持。 例如，如果您创建一个策略来支持对内部通信的存档，则可以将其应用到至少一个用户或用户组，以支持用户的 Lync Server 2013 通信的存档。

<div>


> [!NOTE]  
> 如果为您的部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否为托管在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。 有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。<BR>在启用存档之前，应在存档配置中指定所有适当选项。 有关详细信息，请参阅 Operations 文档中的在 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中管理存档配置选项（针对组织、网站和池</A> ）。



</div>

使用本主题中的过程将以前创建的存档用户策略应用于一个或多个用户帐户或用户组。

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>将存档用户策略应用于用户帐户

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在 " **编辑 Lync Server 用户** " 中的 " **存档策略**" 下，选择要应用的存档用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt; 自动 &gt; </STRONG>设置" 应用默认服务器安装设置。 服务器将自动应用这些设置。

    
    </div>

6.  单击“提交”****。

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配 Per-User 存档策略

可以使用 Windows PowerShell 和 **new-csarchivingpolicy** cmdlet 分配每用户存档策略。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>将每用户存档策略分配给单个用户

  - 以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>将每用户存档策略分配给多个用户

  - 此命令向帐户驻留在注册器池 atl-cs-001.litwareinc.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。 有关此命令中使用的 Filter 参数的详细信息，请参阅 [get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 文档。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>分配每用户存档策略

  - 以下命令取消之前已分配给 Ken Myer 的所有每用户存档策略的分配。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

有关详细信息，请参阅 [new-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 文档。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[在 Lync Server 2013 中分配每用户策略](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

