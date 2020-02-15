---
title: Lync Server 2013：准备林
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec335e95264c4588b81ea5cae8473e540e9af5a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>准备 Lync Server 2013 的林

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

林准备创建 Active Directory 全局设置和对象以及由 Lync Server 2013 使用的 Active Directory 通用组，并授予对 Active Directory 对象的适当访问权限。 有关通用组以及由林准备创建的全局设置和对象的说明，请参阅[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。

林准备还会创建包含由 Lync Server 2013 使用的属性集和显示说明符的对象，并将它们存储在配置容器中。

<div>


> [!IMPORTANT]  
> 在执行林准备过程之前，请确保架构准备更改已复制到所有域控制器。 如果复制尚未完成，则会出错。



</div>

如果您正在执行新的 Lync Server 部署，则必须将全局设置存储在配置容器中。 如果要从早期版本进行升级，并且仍将全局设置存储在系统容器中，则可以继续使用系统容器。

只有林根目录域的 Enterprise Admins 组或 Domain Admins 组的成员才能执行此过程。

<div>

## <a name="in-this-section"></a>本部分内容

  - [为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)

  - [使用 cmdlet 对 Lync Server 2013 反向林准备](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

