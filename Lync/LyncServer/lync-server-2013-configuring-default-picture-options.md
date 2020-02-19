---
title: Lync Server 2013：配置默认图片选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24d32ca52df9c75cf2a0816ff81bd5eaa775d22a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>在 Lync Server 2013 中配置默认图片选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-22_

默认情况下，将自动显示用户的图片。 如果用户想要隐藏其图片，可以在 Lync 客户端中选择 "**隐藏我的图片**" 选项。 但是，其他一些 Office 应用程序将忽略此设置。

如果在用户关闭图片时可能显示图片，则可以在全局范围内更改 Lync 图片显示设置，也可以更改网站或服务，以便默认情况下不会显示用户的图片。 使用以下 Lync Server 命令行管理程序 cmdlet，以使用户的图片在客户端中明确选择 "**显示我的图片**" 选项，否则不会显示。

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的[CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) 。

</div>

<span> </span>

</div>

</div>

</div>

