---
title: Lync Server 2013：创建或修改新的客户端版本策略规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9207ff9d615990d0e944ac8c435561f0c937f089
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改新的客户端版本策略规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-21_

客户端版本策略规则定义当用户尝试使用特定客户端和客户端版本登录时应采取的操作。 您可以从 Lync Server 2013 控制面板中创建或修改客户端版本策略的各个规则。

<div>


> [!IMPORTANT]  
> 规则按优先级顺序列出。 例如，如果您有一个允许运行版本1.5 的客户端进行连接的规则，然后是一个规则，该规则会阻止运行低于2.0 的版本的客户端，则第一个规则优先，并且允许运行版本1.5 的客户端连接。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>使用 Lync Server 控制面板创建或修改客户端版本策略规则

1.  在 Lync server 2013 with Lync Server 控制面板[中创建或修改新的客户端版本策略](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。

2.  在 "**编辑客户端版本策略**" 页上，执行下列操作之一：
    
      - 单击“新建”**** 创建新的客户端版本规则。
    
      - 单击列表中已定义的客户端类型之一，然后单击“显示详细信息”****。
    
    <div>
    

    > [!NOTE]  
    > 可以使用通配符来指示客户端类型。

    
    </div>

3.  在“用户代理”**** 中，选择客户端类型。

4.  在“版本号”**** 下，执行下列操作：
    
      - 在“主版本”**** 中，键入与客户端的主版本相对应的版本号。
    
      - 在“次版本”**** 中，键入与客户端的次版本相对应的版本号。
    
      - 在“内部版本”**** 中，键入与客户端的主版本和次版本相对应的版本号。
    
      - 在“更新”**** 中，键入与客户端的更新版本相对应的版本号。
    
    <div>
    

    > [!NOTE]  
    > 可以使用通配符来指示客户端版本号。

    
    </div>

5.  要为上述步骤中指定的客户端版本指定匹配操作，请在“比较操作”**** 中，单击下列选项之一：
    
      - **相同**
    
      - **不是**
    
      - **更高**
    
      - **更高或相同**
    
      - **更低**
    
      - **更低或相同**

6.  要指定在满足上述步骤中的条件时执行的操作，请在“操作”**** 中，单击下列选项之一：
    
      - 要允许客户端登录，请单击“允许”****。
    
      - 要允许客户端登录并接收来自 Windows Server 更新服务或 Microsoft Update 的更新，请单击“允许并升级”****。仅当选中用户代理“OC”**** 时，才能进行此操作。
        
        <div>
        

        > [!NOTE]  
        > 如果选择此操作，则会在用户下一次登录 Lync 2013 时显示通知。 该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。 为了避免混淆，您只应在更新可用后选择此操作。

        
        </div>
    
      - 要允许客户端登录并显示有关下载其他客户端版本的位置的消息，请单击“使用 URL 允许”****。需要在此过程的后面阶段指定 URL。
    
      - 要阻止客户端登录，请单击“阻止”****。
    
      - 要阻止客户端登录并允许客户端接收来自 Windows Server 更新服务或 Microsoft Update 的更新，请单击“阻止并升级”****。仅当选中用户代理“OC”**** 时，才能进行此操作。
    
      - 要阻止客户端登录并显示有关下载其他客户端版本的位置的消息，请单击“使用 URL 阻止”****。需要在此过程的后面阶段指定 URL。

7.  （可选）如果在上一步中单击“使用 URL 允许”**** 或“使用 URL 阻止”****，则在“URL”**** 中键入要包含在消息中的客户端下载 URL。

8.  单击“确定”****，然后单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

