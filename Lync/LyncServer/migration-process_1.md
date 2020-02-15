---
title: 迁移过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6eec7971665aa8e4494ca4509c92c406458cb08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>迁移过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-24_

Lync Server 2013 的推荐和受支持的迁移过程是并行迁移过程。 本主题介绍为什么应使用并行迁移，还包括有关共存的信息。

<div>

## <a name="side-by-side-migration"></a>并行迁移

在几乎每个迁移中，都应该使用并行迁移路径。 在并行迁移中，可以使用 Lync Server 2013 和运行 Office 通信 Server 2007 R2 的相应服务器一起部署新的服务器，然后将操作转移到新服务器。 如果有必要回滚到 Office 通信服务器 2007 R2，您只需将操作转移回原始服务器。 请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。

</div>

<div>

## <a name="coexistence-testing"></a>共存测试

在与 Office 通信服务器 2007 R2 并行部署 Lync Server 2013 之后，该拓扑表示 Lync Server 2013 和 Office 通信服务器 2007 R2 的共存测试状态。 在这种状态下，必须测试并确保服务已启动，这一点很重要；可以管理每个站点，并且客户端可以与当前用户和旧用户通信。 在迁移所有用户之前，必须了解每个部署的状态和确保每个部署正常运行，这点非常重要。 通常情况下，共存测试阶段在 Lync Server 2013 的试点测试中存在。 旧版用户在一段时间内被移动到 Lync Server 2013，以确保应用程序兼容性和功能和功能正常运行。 完成试点测试后，用户和应用程序将移至 Lync Server 2013 的生产版本，并且旧池和 Office 通信服务器 2007 R2 的应用程序将停用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

