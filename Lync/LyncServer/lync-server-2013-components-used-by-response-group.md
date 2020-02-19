---
title: Lync Server 2013：响应组使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6cf167917dc7d72484eb0fa833a688b0b4e4b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Lync Server 2013 中的响应组使用的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

当您部署企业语音时，将自动启用响应组应用程序。 本节介绍支持响应组应用程序的组件。

<div>

## <a name="response-group-components"></a>响应组组件

以下 Microsoft Lync Server 2013 组件支持响应组应用程序：

  - **Application service**   Application service 提供用于部署、托管和管理统一通信应用程序（如响应组）的平台。 应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。

  - **响应组应用**   程序响应组应用程序是由应用程序服务承载的统一通信应用程序之一。 当您部署响应组时，它会自动包括在内。 响应组应用程序将传入呼叫路由并排队到代理组。

  - **语言包**   需要语言包才能支持文本到语音转换和语音识别。 这些语音技术在配置邮件时使用，如欢迎消息和其他提示，以及交互式语音响应（IVR）问题和答案。 默认情况下，在部署 Lync Server 2013 时，会安装26个受支持的语言包。

  - **音频文件**   ：音频文件用于邮件和保留音乐。

  - **文件存储**   响应组使用文件存储来存储音频文件。 多个响应组池可以使用同一实例的文件存储。

  - **响应组配置工具**   ：响应组配置工具是一个基于 web 的工具，用于创建和配置响应组。 当您安装 Web 服务时，将包含响应组配置工具。

  - **Microsoft Lync server 2013 控制面板**   您可以使用 Lync server 控制面板设置和配置响应组的代理组和队列。

  - **Lync server 命令行**   管理程序可以使用 Lync Server 命令行管理程序 cmdlet 配置所有响应组设置。

  - **Microsoft Lync 2013**   正式代理（代理必须登录到组才能接受对组的呼叫）使用 Lync 2013 登录到组并从组中注销。 如果为正式代理配置了代理组，则代理将单击 Lync 2013 中的菜单项，以打开 Internet Explorer，并显示用于登录和注销组的网页控制台。

  - ****   响应组配置工具（代理的登录和注销控制台、Lync Server 控制面板和响应组客户端 Web 服务）需要 web 服务 web 服务。

  - **响应组客户端 web 服务**   响应组应用程序提供了一个客户端 web 服务，该服务可供第三方应用程序用来检索有关代理、代理组成员身份、代理登录状态、组呼叫状态以及支持匿名呼叫的组的信息。 Lync 2013 和 Lync 2010 助理使用响应组客户端 Web 服务检索代理可用于进行匿名呼叫的响应组的列表。 当您安装 Web 服务时，将包含客户端 web 服务。

</div>

</div>

<span> </span>

</div>

</div>

</div>

