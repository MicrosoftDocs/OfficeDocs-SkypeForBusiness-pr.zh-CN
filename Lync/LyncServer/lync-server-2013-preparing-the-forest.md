---
title: Lync Server 2013：准备林
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>为 Lync Server 2013 准备林

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

林准备创建用于 Lync Server 2013 的 Active Directory 全局设置和对象以及 Active Directory 通用组, 并在 Active Directory 对象上授予合适的访问权限。 有关通用组和由林准备创建的全局设置和对象的说明, 请参阅[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。

林准备还会创建包含由 Lync Server 2013 使用的属性集和显示说明符的对象, 并将它们存储在配置容器中。

<div>


> [!IMPORTANT]  
> 在执行林准备过程之前, 请确保架构准备更改已复制到所有域控制器。 如果复制未完成, 则会出现错误。



</div>

如果你正在执行新的 Lync 服务器部署, 则必须将全局设置存储在配置容器中。 如果从早期版本升级, 但仍将全局设置存储在系统容器中, 则可以继续使用系统容器。

你必须是林根域的企业管理员或域管理员组的成员才能执行此过程。

<div>

## <a name="in-this-section"></a>本节内容

  - [为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)

  - [针对 Lync Server 2013 使用 Cmdlet 反向执行林准备](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

