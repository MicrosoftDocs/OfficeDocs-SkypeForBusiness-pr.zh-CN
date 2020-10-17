---
title: 'Lync Server 2013：使用 Office 自定义工具 (OCT) '
description: Lync Server 2013：使用 Office 自定义工具 (OCT) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 602502ba4579ed6c640eee909d4c6b056ce247d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547328"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Office 自定义工具 (OCT) 

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。 使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。 可将该文件放在网络安装点上的 Updates 文件夹中。 在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。 Updates 文件夹仅可用于在 Office 2013 的初始安装过程中部署软件更新。

OCT 是安装程序的一部分且包括在产品的批量许可版本中。 通过 `setup.exe /admin` 从包含 Office 2013 源文件的网络安装点的根目录中的命令行键入，可以运行 OCT。 例如，可使用以下命令：

`\\server\share\Office15\setup.exe /admin`

管理员可使用 OCT 创建安装程序自定义 .msp 文件。 就像在 Microsoft Office 2010 年10月中一样，管理员可以自定义以下方面：

  - **设置** 用于指定客户端的默认安装位置和默认单位名称、其他网络安装源、产品密钥、最终用户许可协议、显示级别、Office 的早期版本、要删除的自定义程序、安装过程中要运行的自定义程序、安全设置和安装程序属性。

  - **功能** 用于配置用户设置并自定义 Office 功能的安装方式。 管理员可以使用 OCT 为用户指定 Office 应用程序设置的初始默认值。 用户可以在安装后修改大多数设置。

  - **其他内容** 用于添加或删除文件、添加或删除注册表项，以及配置快捷方式。

  - **Outlook** 用于自定义用户的默认 Outlook 配置文件、指定 Exchange 设置、添加帐户、删除帐户和导出设置，以及指定发送和 \\ 接收组。

有关 OCT 的信息，请参阅 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。

</div>

<span> </span>

</div>

</div>

</div>

