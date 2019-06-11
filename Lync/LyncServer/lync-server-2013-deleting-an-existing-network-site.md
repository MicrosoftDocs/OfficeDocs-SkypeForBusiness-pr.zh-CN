---
title: 'Lync Server 2013: 删除现有网络网站'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有网络网站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。 你可以使用 Lync Server 2013 控制面板配置网站并将其与区域相关联。 例如, 北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。 必须为组织内的每个网站创建 CAC 网络网站, 即使该网站没有带宽限制也是如此。 在 Lync Server 控制面板中, 您可以创建、修改和删除网络站点。 使用以下过程删除现有网络网站。 有关创建或修改网络站点的详细信息, 请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>删除网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。

4.  在 "**网站**" 页面上, 单击要删除的网站。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个网站。 若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个网站。 或者, 若要选择 "所有网站", 请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  在 "**编辑**" 菜单上, 单击 "**删除**"。

6.  单击“**确定**”。
    
    <div>
    

    > [!WARNING]  
    > 如果网络站点与网络子网相关联, 则不能将其删除。 如果您尝试删除与子网相关联的网站, 您将收到一条错误消息。 若要查看某个网站是否与任何子网相关联, 请单击该网站, 然后单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>显示详细信息</STRONG>"。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

