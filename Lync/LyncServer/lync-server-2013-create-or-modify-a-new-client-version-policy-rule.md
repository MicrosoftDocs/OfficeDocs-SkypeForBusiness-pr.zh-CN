---
title: 'Lync Server 2013: 创建或修改新的客户端版本策略规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改新的客户端版本策略规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-01-21_

客户端版本策略规则定义当用户尝试使用特定客户端和客户端版本登录时应采取的操作。 你可以从 Lync Server 2013 控制面板创建或修改客户端版本策略的单个规则。

<div>


> [!IMPORTANT]  
> 规则按优先级顺序列出。 例如, 如果你有允许运行版本1.5 的客户端连接的规则, 然后是阻止运行2.0 之前的版本的客户端的规则, 则将优先使用运行版本1.5 的客户端, 并且允许运行版本的客户端进行连接。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>通过 Lync Server "控制面板" 创建或修改客户端版本策略规则

1.  使用 Lync Server "控制面板"[在 Lync server 2013 中创建或修改新的客户端版本策略](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。

2.  在 "**编辑客户端版本策略**" 页面上, 执行下列操作之一:
    
      - 单击 "**新建**" 以创建新的客户端版本规则。
    
      - 单击列表中某个已定义的客户端类型, 然后单击 "**显示详细信息**"。
    
    <div>
    

    > [!NOTE]  
    > 可以使用通配符指示客户端类型。

    
    </div>

3.  在 "**用户代理**" 中, 选择一种客户端类型。

4.  在 "**版本号**" 下, 执行下列操作:
    
      - 在 "**主要版本**" 中, 键入与客户端的主要版本相对应的数字。
    
      - 在 "**次要版本**" 中, 键入与客户端的次要版本相对应的数字。
    
      - 在 "**生成**" 中, 键入与客户端的主要和次要版本相对应的数字。
    
      - 在 "**更新**" 中, 键入与客户端更新的版本相对应的数字。
    
    <div>
    

    > [!NOTE]  
    > 可以使用通配符指示客户端版本号。

    
    </div>

5.  若要为您在前面的步骤中指定的客户端版本指定匹配操作, 请在 "**比较" 操作**中, 单击下列操作之一:
    
      - **相同**
    
      - **不是**
    
      - **更高**
    
      - **更高或相同**
    
      - **更低**
    
      - **更低或相同**

6.  若要指定在满足前面步骤中的条件时要执行的操作, 请单击下列**操作**之一:
    
      - 要允许客户登录, 请单击 "**允许**"。
    
      - 若要允许客户登录并接收来自 Windows Server 更新服务或 Microsoft 更新的更新, 请单击 "**允许和升级**"。 仅当选择了 "用户代理**OC** " 时, 此操作才可用。
        
        <div>
        

        > [!NOTE]  
        > 选择此操作会导致在用户下次登录 Lync 2013 时显示通知。 该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。 为了避免混淆，您只应在更新可用后选择此操作。

        
        </div>
    
      - 若要允许客户登录并显示有关从何处下载另一个客户端版本的消息, 请单击 "**允许使用 URL**"。 在此过程后面的部分中指定 URL。
    
      - 若要阻止客户端登录, 请单击 "**阻止**"。
    
      - 若要阻止客户端登录并允许客户从 Windows Server 更新服务或 Microsoft 更新接收更新, 请单击 "**阻止和升级**"。 仅当选择了 "用户代理**OC** " 时, 此操作才可用。
    
      - 若要阻止客户登录并显示有关从何处下载另一个客户端版本的消息, 请单击 "**带 URL 阻止**"。 在此过程后面的部分中指定 URL。

7.  可选如果在上一步中单击 "**允许 url**或带 Url 的**阻止**", 请键入要包含在**url**中的消息中的客户端下载 URL。

8.  单击 **"确定**", 然后单击 "**提交**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

