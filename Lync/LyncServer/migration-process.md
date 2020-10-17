---
title: 迁移过程
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf45be5e5d30a1c8a69a634837bc63c2768b193
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515119"
---
# <a name="migration-process"></a>迁移过程

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

Lync Server 2013 的建议和受支持迁移过程是并行迁移。 本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。

<div>

## <a name="side-by-side-migration"></a>并行迁移

在几乎每个迁移中，都应该使用并行迁移路径。 在并行迁移中，将新服务器与运行 Lync Server 2010 的相应服务器一起部署到 Lync Server 2013，然后将操作转移到新服务器。 如果有必要回滚到 Lync Server 2010，您只需将操作转移回原始服务器。 请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。

</div>

<div>

## <a name="coexistence-testing"></a>共存测试

在将 Lync Server 2013 与 Lync Server 2010 并行部署后，该部署表示 Lync Server 2013 和 Lync Server 2010 的共存测试状态。 在此状态下，必须测试和确保服务已启动，可以管理每个站点，并且客户端可以与当前用户和旧用户通信。 在迁移所有用户之前，必须了解每个部署的状态并确保每个部署正常运行。 通常情况下，共存测试阶段在 Lync Server 2013 的试点测试中存在。 旧版用户在一段时间内被移动到 Lync Server 2013，以确保应用程序兼容性和功能和功能正常运行。 完成试点测试后，用户和应用程序将移至 Lync Server 2013 的生产版本，并停用 Lync Server 2010 的旧池和应用程序。

</div>

</div>

<span> </span>

</div>

</div>

</div>

