---
title: Lync Server 2013：组间呼叫应答使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05f41b7420f15c2815ababa0f85d8aca43898dd2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>由 Lync Server 2013 中的组呼叫应答使用的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

当您部署企业语音和呼叫寄存应用程序时，将自动部署组间呼叫应答。 您可以通过将呼叫寄存通道表配置为指定为呼叫应答组号码的不同号码区域，然后将用户分配给呼叫应答组并为用户启用组内呼叫应答，从而启用组呼叫装货。 以下 Lync Server 组件支持组呼叫装货：

  - **Application service**   Application service 提供用于部署、托管和管理统一通信应用程序（如呼叫寄存应用程序）的平台。 应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。

  - **呼叫寄存应用**   程序呼叫寄存应用程序是由应用程序服务托管的统一通信应用程序之一。 组呼叫应答基于呼叫寄存应用程序。

  - **Lync server 命令行**   管理程序使用 lync server 命令行管理程序管理组呼叫应答组。

  - **SEFAUtil 资源工具包工具**   使用辅助扩展功能激活实用程序（SEFAUtil）将用户分配到呼叫应答组，并为用户启用或禁用呼叫应答。

</div>

<span> </span>

</div>

</div>

</div>

