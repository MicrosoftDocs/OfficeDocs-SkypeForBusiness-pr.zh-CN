---
title: Lync Server 2013：为分支站点定义 PSTN 网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435af3ab537097592325438707b89ce901da9bcd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516389"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>在 Lync Server 2013 中为分支站点定义 PSTN 网关

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

在中心网站上执行此过程，其中包含至少一个前端池或 Standard Edition server。

<div>


> [!IMPORTANT]  
> 执行该过程之前，必须满足以下条件： 
> <UL>
> <LI>
> <P>&nbsp;必须在中央站点设置 Lync Server 2013 通信软件。</P>
> <LI>
> <P>必须在中央站点上部署中介服务器。</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>定义 PSTN 网关

1.  依次单击“开始”****、“所有程序”****、“Microsoft Lync Server”****，然后单击“Lync Server 拓扑生成器”****。

2.  在控制台树中展开中央站点，展开“分支机构站点”****，再展开要为其定义公用电话交换网 (PSTN) 网关的分支站点的名称，然后展开“共享组件”****。

3.  右键单击“PSTN 网关”****，然后单击“新建 IP/PSTN 网关”****。

4.  在“定义新的 IP/PSTN 网关”**** 对话框中，单击“网关 FQDN 或 IP 地址”****，然后键入要在分支站点部署的网关的完全限定域名 (FQDN) 或 IP 地址。

5.  单击“IP/PSTN 网关的侦听端口”****，然后接受默认值。

6.  在“SIP 传输协议”**** 列表中，单击网关使用的传输协议，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 出于安全考虑，强烈建议使用支持传输层安全性 (TLS) 的 PSTN 网关。

    
    </div>

<div>


> [!TIP]  
> 使用 cmdlet <STRONG>Set-CsPstnGateway</STRONG> 修改 PSTN 网关的属性。 有关详细信息，请参阅 Lync Server 命令行管理程序帮助中的 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">CsPstnGateway</A>。



</div>

分支站点恢复的**下一步**：[在 Lync Server 2013 中为分支站点恢复配置用户](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的 PSTN 网关部署选项](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

