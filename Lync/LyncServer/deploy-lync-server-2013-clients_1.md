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
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>部署 Lync Server 2013 客户端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

将用户迁移到 Lync Server 2013 后，请执行下列操作：

1.  在新的 Lync Server 2013 服务器上使用客户端版本筛选器，仅允许已安装最新更新的客户端登录。

2.  如有必要，请配置客户端引导所需的组策略设置。 有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)"。 只有当你想要更改现有客户端引导策略或想要设置新的客户端引导策略时，才需要配置这些设置。 如果您不打算配置客户端引导策略，或者希望旧的客户端引导策略保持有效，则无需执行任何操作。

3.  使用 Lync Server 2013 控制面板、Lync Server 2013 管理外壳程序或同时使用这两者，为特定用户或用户组配置其他用户和客户端策略。 有关详细信息，请参阅规划文档中[Lync 2013 的新增和更改设置](lync-server-2013-new-and-changed-settings-for-lync-2013.md)。

4.  部署最新版本的 Lync Server 2013 客户端以及最新的累积更新。 有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)"。

5.  可选如果你的组织需要 Lync Server 2013 增强状态隐私模式，在迁移完成后，请定义客户端版本策略规则以防止较早版本的客户端版本登录。 然后，启用 "增强状态隐私模式"。
    
    <div>
    

    > [!IMPORTANT]  
    > 不要启用 Lync 2013 增强的状态隐私模式，直到给定服务器池中的每个用户都安装了最新的客户端版本。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

