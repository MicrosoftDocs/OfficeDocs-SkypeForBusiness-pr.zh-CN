---
title: Lync Server 2013：导出语音路由测试用例
description: Lync Server 2013：导出语音路由测试用例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934bd183a17c46cf82fe5bc04faaa55a9bbe4731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564778"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中导出语音路由测试用例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

测试用例为您在组织中测试语音路由提供了一种方法：定义要拨打的号码以及要使用的拨号计划和语音策略等事项，并且 Lync Server 可以验证是否已将所提供的号码成功路由到 PSTN 网络。

可以使用 Lync Server 控制面板创建的测试用例通常仅保存在最初创建和运行事例的服务器上。 但是，这些测试用例可导出为 XML 文件（使用 .vtest 扩展名），然后在其他服务器上导入。 这使您可在位于拓扑中的不同点上的不同计算机上运行相同的测试。

<div>

## <a name="to-export-a-voice-routing-test-case"></a>导出语音路由测试用例

1.  在 "Lync Server 控制面板" 中，单击 " **语音路由** "，然后单击 " **测试语音路由**"。

2.  在“测试语音路由”**** 选项卡上，选择要导出的一个或多个测试用例。若要选择多个测试用例，请单击要导出的第一个用例，然后在按住 Ctrl 键的同时选择要导出的其他用例。

3.  在“操作”**** 菜单上，单击“导出测试用例”****。

4.  在“另存为”**** 对话框中，选择要存储已导出测试用例的文件夹，并在“文件名”**** 框中为生成的 XML 文件键入一个名称。请注意，如果要导出多个测试用例，则所有这些测试用例都将保存到单个 XML 文件中。

5.  若要保存测试用例，请单击“保存”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中导入语音路由测试用例](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

