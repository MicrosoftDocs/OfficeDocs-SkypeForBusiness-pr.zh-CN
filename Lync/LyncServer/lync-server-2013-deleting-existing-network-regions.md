---
title: Lync Server 2013：删除现有网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有网络区域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

网络区域跨多个地理区域互连网络的各个部分。 每个网络区域必须与一个中心网站相关联。 中心网站是运行呼叫许可控制（CAC）带宽策略服务的数据中心网站。 可以使用 Lync Server "控制面板" 配置网络区域。 网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。 从 Lync Server 控制面板中，您可以创建、修改或删除网络区域。 使用本主题删除现有网络区域。 有关创建或修改现有网络区域的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-delete-a-network-region"></a>删除网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域**"。

4.  在 "**区域**" 页面上，单击要删除的区域。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个区域。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域。 或者，若要选择所有区域，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  在 "**编辑**" 菜单上，单击 "**删除**"。

6.  单击“**确定**”。
    
    <div>
    

    > [!WARNING]  
    > 如果网络区域与网络网站相关联，则无法将其删除。 如果您尝试删除与网站相关联的区域，您将收到一条错误消息。 若要查看某个区域是否与任何网站相关联，请选择该区域，然后单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>显示详细信息</STRONG>"。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

