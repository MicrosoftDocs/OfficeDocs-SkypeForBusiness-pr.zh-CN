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
ms.openlocfilehash: b94bc731ac00a4ff774930f506282b6aef16cbaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a>在 Lync Server 2013 中配置响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-30_

响应组是一种企业语音功能，用于将传入呼叫路由和排队到一组人员（称为*工程师*，如帮助桌面或客户服务桌面）。

部署 "企业语音" 时，将在前端服务器或标准版服务器上自动安装和启用响应组所需的组件。 若要使 "响应组" 对用户可用，必须先配置代理组、"队列" 和 "工作流"。 此外，响应组管理员可以将现有工作流的配置委派给响应组管理器，然后这些管理员可以修改和重新配置工作流及其关联的代理组和队列。

本部分将指导你完成 Lync Server 2013 响应组的配置。 它假设你已阅读与响应组相关的计划部分，并已部署企业版服务器或具有企业语音的标准版服务器。

<div>


> [!TIP]  
> 有关使用 Lync Server 命令行管理程序创建响应组的详细信息，包括示例脚本，请参阅 "在" 处<A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>使用 Lync Server Management Shell 创建第一个响应组。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的响应组配置权限和先决条件](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013 中的 "响应" 组的部署过程](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013 中的工作流创建方案概述](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [在 Lync Server 2013 中创建响应组代理组](lync-server-2013-create-response-group-agent-groups.md)

  - [在 Lync Server 2013 中创建响应组队列](lync-server-2013-create-response-group-queues.md)

  - [可选在 Lync Server 2013 中定义响应组工作时间](lync-server-2013-optional-define-response-group-business-hours.md)

  - [可选在 Lync Server 2013 中定义 "响应组" 假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [在 Lync Server 2013 中创建响应组工作流](lync-server-2013-create-response-group-workflows.md)

  - [可选在 Lync Server 2013 中验证响应组部署](lync-server-2013-optional-verify-response-group-deployment.md)

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

