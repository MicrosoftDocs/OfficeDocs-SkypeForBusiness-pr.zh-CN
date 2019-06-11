---
title: 迁移过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>迁移过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-17_

Lync Server 2013 的推荐和支持的迁移过程是并行迁移。 本主题介绍了应使用并行迁移的原因, 还包括有关共存测试的信息。

<div>

## <a name="side-by-side-migration"></a>并行迁移

在几乎所有迁移中, 都应使用并行迁移路径。 在并行迁移中, 你将新服务器与运行 Lync server 2010 的相应服务器一起部署在 Lync Server 2013 旁边, 然后将操作转移到新服务器。 如果需要回退到 Lync Server 2010, 您只需将操作转移回原始服务器。 请注意, 在这种情况下, 使用升级的客户安排的新会议将不起作用, 并且客户端也需要降级。

</div>

<div>

## <a name="coexistence-testing"></a>共存测试

在与 Lync Server 2010 并行部署 Lync Server 2013 之后, 该部署表示 Lync Server 2013 和 Lync Server 2010 的共存测试状态。 在此状态下, 测试和确保服务已启动、可管理每个网站, 并且客户端可以与当前用户和旧版用户进行通信非常重要。 在迁移所有用户之前, 了解每个部署的状态非常重要, 并确保每个部署都能正常运行。 通常, 共存测试阶段存在于 Lync Server 2013 的试点测试中。 旧版用户在一段时间内被移动到 Lync Server 2013, 以确保应用程序兼容性和功能和功能正常工作。 试点测试后, 用户和应用程序将移至 Lync Server 2013 的产品版本, 并且 Lync Server 2010 的旧池和应用程序将被停用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

