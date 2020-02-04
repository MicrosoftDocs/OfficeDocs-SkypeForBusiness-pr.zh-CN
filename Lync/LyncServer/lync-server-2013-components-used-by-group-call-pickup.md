---
title: Lync Server 2013：组呼叫挑选使用的组件
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
ms.openlocfilehash: 7b9c810d5835d113a26bd3a15295f75a71552590
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中的组呼叫装货使用的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-30_

当您部署企业语音和呼叫驻留应用程序时，将自动部署组呼叫装货。 您可以通过配置 "呼叫驻留" 轨道表，将指定为 "呼叫装货组号码" 的不同号码区域配置为 "呼叫驻留"，然后为用户分配呼叫装货组并为用户启用组呼叫装货。 以下 Lync Server 组件支持组呼叫分拣：

  - **应用程序服务**   应用程序服务提供用于部署、托管和管理统一通信应用程序（如呼叫驻留应用程序）的平台。 应用程序服务将自动安装在前端池和每个标准版服务器上的每个前端服务器上。

  - **呼叫驻留应用程序**   呼叫寄存应用程序是由应用程序服务托管的统一通信应用程序之一。 组呼叫分拣基于呼叫寄存应用程序。

  - **Lync server management shell**   使用 lync server management shell 管理组呼叫装货组。

  - **SEFAUtil 资源工具包工具**   使用辅助扩展功能激活实用工具（SEFAUtil）将用户分配给呼叫装货组并为用户启用或禁用呼叫装货。

</div>

<span> </span>

</div>

</div>

</div>

