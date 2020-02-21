---
title: Lync Server 2013：配置响应组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40f48b52759bfc12441a558b85de89d149f4bf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a>在 Lync Server 2013 中配置响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

响应组是一个企业语音功能，可将传入呼叫路由并排队给一组人员（称为*代理*，如技术支持或客户服务桌面）。

响应组所需的组件将在部署企业语音时在前端服务器或 Standard Edition Server 中自动安装并启用。 要使响应组对用户可用，必须依次配置代理组、队列和工作流。 此外，响应组管理员还可以将现有工作流的配置委派给响应组管理器，然后可以修改和重新配置工作流及其关联的代理组和队列。

本部分将指导您完成 Lync Server 2013 响应组的配置。 它假定您已阅读与响应组相关的规划部分，并已部署企业版服务器或具有企业语音的 Standard Edition 服务器。

<div>


> [!TIP]  
> 有关使用 Lync Server 命令行管理程序创建响应组的详细信息，包括示例脚本，请参阅中的 "使用 Lync Server 命令行管理程序创建您<A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>的第一个响应组"。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的响应组配置权限和先决条件](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013 中响应组的部署过程](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013 中的工作流创建方案概述](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [创建响应组代理组 Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [在 Lync Server 2013 中创建响应组队列](lync-server-2013-create-response-group-queues.md)

  - [Optional在 Lync Server 2013 中定义响应组工作时间](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Optional在 Lync Server 2013 中定义响应组假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [在 Lync Server 2013 中创建响应组工作流](lync-server-2013-create-response-group-workflows.md)

  - [Optional在 Lync Server 2013 中验证响应组部署](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

