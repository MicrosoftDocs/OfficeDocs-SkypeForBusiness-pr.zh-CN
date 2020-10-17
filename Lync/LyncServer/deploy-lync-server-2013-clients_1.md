---
title: 部署 Lync Server 2013 客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d42b410765b4cf8b7a52221f76ba532347ee3ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502999"
---
# <a name="deploy-lync-server-2013-clients"></a>部署 Lync Server 2013 客户端

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

将用户迁移到 Lync Server 2013 后，请执行以下操作：

1.  在新 Lync Server 2013 服务器上使用客户端版本筛选器，仅允许客户端安装了最新的更新以登录。

2.  如果需要，请配置客户端引导所需的组策略设置。 有关详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md) 。 仅当要更改现有客户端引导策略或者要设置新客户端引导策略时才需要配置这些设置。 如果您不打算配置客户端引导策略，或者希望旧客户端引导策略继续生效，则无需执行任何操作。

3.  使用 Lync Server 2013 控制面板、Lync Server 2013 命令行管理程序或同时使用这两者，为特定用户或用户组配置其他用户和客户端策略。 有关详细信息，请参阅规划文档中的 [Lync 2013 的新增和更改的设置](lync-server-2013-new-and-changed-settings-for-lync-2013.md) 。

4.  部署最新版本的 Lync Server 2013 客户端以及最新的累积更新。 有关详细信息，请参阅部署文档中的在 [Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md) 。

5.   (可选) 如果您的组织需要 Lync Server 2013 增强状态隐私模式，在迁移完成后，定义客户端版本策略规则以防止早期客户端版本登录。 然后，启用增强状态隐私模式。
    
    <div>
    

    > [!IMPORTANT]  
    > 在给定服务器池中的每个用户都安装了最新的客户端版本之前，不要启用 Lync 2013 增强状态隐私模式。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

