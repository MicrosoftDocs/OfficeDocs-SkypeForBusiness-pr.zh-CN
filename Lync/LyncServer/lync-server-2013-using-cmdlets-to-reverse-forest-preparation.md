---
title: Lync Server 2013：使用 cmdlet 反向林准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e3104f07934e590dc22ac9f5000601bc8166b6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535789"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>使用 cmdlet 对 Lync Server 2013 反向林准备

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-06-19_

使用 **Disable-CsAdForest** cmdlet 可反向执行林准备步骤。

<div>


> [!WARNING]  
> 如果您在还部署了旧版 Lync Server 的环境中运行 <STRONG>CsAdForest</STRONG> cmdlet，则早期版本的全局设置也将被删除。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>使用 cmdlet 反向执行林准备

1.  以目录林根级域中的 Domain Admins 组成员身份登录到加入域的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    例如：
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 参数指定是否强制运行该任务。 如果不存在此参数，即使林中的一个域仍为 Lync Server 2013 做好准备，该命令也不会运行。 如果指定了 Force 参数，无论林中其他域的状态如何，都将继续执行此操作。
    
    如果不指定 GroupDomain 参数，则默认值为本地域。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)  


[准备 Lync Server 2013 的林](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

