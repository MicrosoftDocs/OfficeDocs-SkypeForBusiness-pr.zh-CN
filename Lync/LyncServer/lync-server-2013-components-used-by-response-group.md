---
title: Lync Server 2013：响应组使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f52ceb18c355f6d867b5b3b4485434df83683d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Lync Server 2013 中响应组使用的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-11_

部署企业语音时, 将自动启用响应组应用程序。 本部分介绍支持响应组应用程序的组件。

<div>

## <a name="response-group-components"></a>响应组组件

以下 Microsoft Lync Server 2013 组件支持响应组应用程序:

  - **应用程序服务**   应用程序服务提供用于部署、托管和管理统一通信应用程序 (如响应组) 的平台。 应用程序服务将自动安装在前端池中的每个前端服务器上和每个标准版服务器上。

  - **响应组应用**   程序响应组应用程序是由应用程序服务托管的统一通信应用程序之一。 当你部署响应组时, 它会自动包括在内。 响应组应用程序将传入呼叫路由和排队到多个代理组。

  - **语言包**   支持文本到语音转换和语音识别需要语言包。 配置消息（例如欢迎消息以及其他提示、互动语音响应 (IVR) 问题和答案）时，会使用这些语音技术。 默认情况下, 当你部署 Lync Server 2013 时, 将安装26个受支持的语言包。

  - **音频文件**   音频文件用于邮件和保留音乐。

  - **文件存储**   响应组使用文件存储来存储音频文件。 多个响应组池可以使用相同的文件存储实例。

  - **响应组配置工具**   "响应组配置" 工具是用于创建和配置响应组的基于 web 的工具。 在安装 Web 服务时, 将包括 "响应组配置" 工具。

  - **Microsoft Lync server 2013 控制面板**   您可以使用 Lync server 控制面板设置和配置响应组的代理组和队列。

  - **Lync server management shell**   可以使用 Lync server management shell cmdlet 配置所有响应组设置。

  - **Microsoft Lync 2013**   正式代理 (必须先登录到组才可接受对组的呼叫) 使用 Lync 2013 登录到组并注销。 如果为正式代理配置了代理组, 代理将单击 Lync 2013 中的菜单项以打开 Internet Explorer, 并显示用于登录和注销组的网页控制台。

  - ****   响应组配置工具、代理的登录和注销控制台、Lync Server 控制面板和响应组客户端 web 服务需要 web services web 服务。

  - **响应组 "客户端 web 服务**   响应" 组应用程序提供了客户端 web 服务, 可供第三方应用程序用于检索有关代理、代理组成员身份、代理登录状态、组呼叫状态的信息。以及支持匿名调用的组。 Lync 2013 和 Lync 2010 助理使用响应组客户端 Web 服务检索代理可用于进行匿名调用的响应组的列表。 在安装 Web 服务时, 将包括客户端 web 服务。

</div>

</div>

<span> </span>

</div>

</div>

</div>

