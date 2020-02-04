---
title: Lync Server 2013：使用 Cmdlet 反向执行林准备
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
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>针对 Lync Server 2013 使用 Cmdlet 反向执行林准备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-06-19_

使用**CsAdForest** cmdlet 可撤消林准备步骤。

<div>


> [!WARNING]  
> 如果你在还安装了早期版本的 Lync Server 的环境中运行<STRONG>CsAdForest</STRONG> cmdlet，则以前版本的全局设置也将被删除。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>使用 cmdlet 执行反向林准备

1.  以林根域中的 "域管理员" 组的成员身份登录加入域的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    例如：
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 参数指定是否强制运行任务。 如果此参数不存在，并且即使林中的一个域仍为 Lync Server 2013 准备好，该命令也不会运行。 如果指定了 Force 参数，则无论林中其他域的状态如何，操作都将继续。
    
    如果不指定 GroupDomain 参数，则默认值为本地域。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)  


[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

