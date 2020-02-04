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
ms.openlocfilehash: 2771a7a8b29cf410f9da5155e8f379bd7efe0e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>迁移过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-24_

Lync Server 2013 的推荐和支持的迁移过程是并行迁移过程。 本主题介绍了为什么应使用并行迁移，同时还包括有关共存的信息。

<div>

## <a name="side-by-side-migration"></a>并行迁移

在几乎所有迁移中，都应使用并行迁移路径。 在并行迁移中，你可以使用 Lync Server 2013 和运行 Office 通信服务器 2007 R2 的相应服务器一起部署新服务器，然后将操作转移到新服务器。 如果需要回滚到 Office 通讯服务器 2007 R2，您只需将操作转移回原始服务器。 请注意，在这种情况下，使用升级的客户安排的新会议将不起作用，并且客户端也需要降级。

</div>

<div>

## <a name="coexistence-testing"></a>共存测试

在与 Office 通信服务器 2007 R2 并行部署 Lync Server 2013 之后，该拓扑表示 Lync Server 2013 和 Office 通信服务器 2007 R2 的共存测试状态。 在此状态下，测试和确保服务已启动，可以管理每个网站，并且客户端可以与当前用户和旧用户进行通信非常重要。 在迁移所有用户之前，了解每个部署的状态非常重要，并确保每个部署都能正常运行。 通常，共存测试阶段存在于 Lync Server 2013 的试点测试中。 旧版用户在一段时间内被移动到 Lync Server 2013，以确保应用程序兼容性和功能和功能正常工作。 试点测试后，用户和应用程序将移至 Lync Server 2013 的产品版本，并且 Office 通信服务器 2007 R2 的旧池和应用程序将被停用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

