---
title: Lync Server 2013：配置支持的客户端版本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>在 Lync Server 2013 中配置支持的客户端版本

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-14_

在 Lync Server 2013 中，可以设置客户端版本策略以指定您的环境中支持的客户端版本。 此外，可以使用全局客户端版本配置，为尚未定义版本策略并因此尚未明确得到支持或限制的客户端指定默认操作。

您也可以使用客户端版本策略来管理客户端更新。如果设置客户端版本策略并使用“允许并升级”**** 和“阻止并升级”**** 选项，客户端将从 Windows Server 更新服务（如果正在使用此服务）或 Microsoft Update 接收更新的软件。

<div>

## <a name="client-version-policy-settings"></a>客户端版本策略设置

默认客户端版本策略要求所有客户端都运行 Lync。 如果环境中的客户端运行的是早期版本的 Communicator，您可能需要重新配置客户端版本规则，以防止在连接到 Lync Server 2013 时意外地阻止或更新客户端和设备。 您可以修改默认规则，也可以在“客户端版本策略”列表的更高位置添加一个规则来覆盖默认规则。 此外，由于发布累计更新 (CU)，应将客户端版本策略配置为要求最新更新。 有关详细信息，请参阅操作文档中的[指定可用于登录 Lync Server 2013 的客户端应用程序](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

