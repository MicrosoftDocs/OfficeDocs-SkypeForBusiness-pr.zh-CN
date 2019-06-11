---
title: 'Lync Server 2013: 查看网络区域信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52baf7c9dca4d663630bbf0cb17384916f5a953e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看网络区域信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

网络区域跨多个地理区域互连网络的各个部分。 每个网络区域必须与一个中心网站相关联。 中心网站是运行呼叫许可控制 (CAC) 带宽策略服务的数据中心网站。 您可以使用 Lync Server "控制面板" 查看网络区域。 网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。 使用本主题查看现有的网络区域。 有关创建或修改现有网络区域的详细信息, 请参阅[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>使用 Lync Server "控制面板" 查看有关网络区域的信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域**"。

4.  在 "**区域**" 页面上, 单击要查看的区域。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一个区域。

    
    </div>

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络区域信息

你可以使用 Windows PowerShell 和**CsNetworkRegion** cmdlet 查看网络区域信息。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-region-information"></a>查看网络区域信息

  - 若要查看有关所有网络区域的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkRegion
    
    这将返回与以下类似的信息：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

有关详细信息, 请参阅[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)  
[在 Lync Server 2013 中删除现有网络区域](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

