---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76c1296f69421bfbfe83e61055249f2642420ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>验证试点池与旧池的共存情况

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

部署试点池之后，需要使用管理工具查看池信息来验证两个池是否共存。 对于 Lync Server 2013 池和旧版池，必须使用 Lync Server 2013 控制面板和拓扑生成器工具。

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>验证 Lync Server 2013 服务是否已启动

1.  在 Lync Server 2013 前端服务器中，导航到 "管理工具 \\ 服务" 小程序。

2.  确认以下服务正在前端服务器上运行：

**Lync Server 2013 服务**

![已启动 Lync Server 服务的列表](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "已启动 Lync Server 服务的列表")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>打开 "Lync Server 2013 控制面板"

在 Lync Server 2013 部署的前端服务器中，打开 Lync Server 2013 控制面板并选择 Lync Server 2010 池。 重复此过程以打开 Lync Server 2013 池。

**打开 Lync Server 2013 控制面板**

!["选择 URL" 对话框](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png ""选择 URL" 对话框")

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 上，您必须先将 Silverlight 升级到 Silverlight 版本5，然后再使用 Lync Server 控制面板。



</div>

此拓扑现在包括 Lync Server 2010 和 Lync Server 2013 服务器角色。

**“Lync Server 2013 控制面板拓扑”页**

![Lync Server 控制面板-拓扑页面](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 控制面板-拓扑页面")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>请勿尝试在 Lync Server 2010 拓扑生成器中打开拓扑

如果尝试使用 Lync Server 2010 拓扑生成器打开拓扑，将会遇到以下错误。 仅可使用 Lync Server 2013 拓扑生成器查看拓扑。 Lync Server 2013 拓扑生成器必须用于为 Lync Server 2013 和 Lync Server 2010 创建池。

**Lync Server 2010 拓扑生成器错误消息**

![Lync Server 拓扑生成器 MMC Snap 错误](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 拓扑生成器 MMC Snap 错误")

</div>

</div>

<span> </span>

</div>

</div>

</div>

