---
title: Lync Server 2013 Active Directory 支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 193ebaedd11c239ba380937da3051ec8336578a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-04_

Lync Server 2013 支持的 Active Directory 域服务本地拓扑如下所示：

  - 具有单个域的单林

  - 具有单个树和多个域的单林

  - 具有多个树和互不连接的命名空间的单林

  - 中央林拓扑中的多林

  - 资源林拓扑中的多林

<div>


> [!NOTE]  
> Lync Server 2013 不支持单标签域。 例如，支持具有名为<STRONG>contoso. local</STRONG>的根域的林，但不支持名为<STRONG>local</STRONG>的单标签根域。 有关详细信息，请参阅 Microsoft 知识库文章 300684 "有关为带有单标签 DNS 名称的域配置 Windows 的信息" <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支持对域进行重命名。 如果需要重命名已在其中部署 Lync Server 的域，则需要先卸载 Lync Server，再重命名域，然后重新安装 Lync Server。



</div>

有关支持的拓扑和本地部署要求的详细信息，请参阅规划文档中的[Lync Server 2013 中的 Active Directory 域服务要求、支持和拓扑](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)。

</div>

<span> </span>

</div>

</div>

</div>

