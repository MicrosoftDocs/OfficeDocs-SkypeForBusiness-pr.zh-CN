---
title: Lync Server 2013：将子网与用于媒体绕过的网络站点关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>将子网与 Lync Server 2013 中的媒体绕过的网络站点关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-12_

<div>


> [!NOTE]  
> 本主题假定你已配置了媒体绕过全局设置，并且已配置了媒体绕过的网络区域和网络站点。



</div>

您的网络中的每个子网都必须与特定的网络站点相关联。 这是因为子网信息用于确定终结点所在的网络站点。 当会话中双方双方的位置已知时，媒体绕过可确定发送媒体以进行处理的位置。

媒体绕过对将子网与网络站点相关联的特殊要求。 若要在拓扑中的子网和网络站点之间创建关联，请按照[将子网与 Lync Server 2013 中的网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)的过程进行操作。

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>后续步骤：创建带宽策略配置文件

将子网与用于媒体绕过的网络站点相关联后，必须创建一个或多个带宽策略配置文件，以便将子网分区为具有良好连接性的子网，而不是为了媒体绕过。 网络区域中的所有子网都没有带宽限制的网络站点具有良好的连接性，因此这些子网可以使用 "媒体绕过"。

有关配置带宽策略配置文件的过程，请参阅[在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

