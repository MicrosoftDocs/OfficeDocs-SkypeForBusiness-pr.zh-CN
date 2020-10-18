---
title: Lync Server 2013：通知应用程序使用的组件
description: Lync Server 2013：通知应用程序使用的组件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577688"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中通知应用程序使用的组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-13_

在 Lync Server 2013 中，通知应用程序是响应组应用程序的一个组件。 部署企业语音时，会自动安装并激活通知应用程序和响应组应用程序。 本节介绍支持通知应用程序的组件。

<div>

## <a name="announcement-application-components"></a>通知应用程序组件

以下 Lync Server 组件支持通知应用程序：

  - **应用程序服务**    应用程序服务提供了用于部署、托管和管理统一通信应用程序的平台。 应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。

  - **响应组应用程序**    响应组应用程序是由应用程序服务承载的统一通信应用程序之一。 如果将未分配的电话号码范围配置为路由到通知，则响应组应用程序需要将对电话号码的呼叫路由。 如果所有区域都配置为路由到 Exchange 统一消息 (UM) ，则不需要 (响应组应用程序。 ) 

  - **音频文件**    音频文件用于通知。

  - **文件存储**    通知应用程序使用文件存储来存储其音频文件。

  - **Lync Server 控制面板**    您可以使用 Lync Server 控制面板配置未分配号码表。

  - **Lync Server 命令行**     管理程序您可以使用 Lync Server 命令行管理程序 cmdlet 配置通知设置和未分配号码表。

</div>

</div>

<span> </span>

</div>

</div>

</div>

