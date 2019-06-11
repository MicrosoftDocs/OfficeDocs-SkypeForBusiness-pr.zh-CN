---
title: Lync Server 2013：为分支站点定义 PSTN 网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>在 Lync Server 2013 中为分支站点定义 PSTN 网关

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

在中心站点执行此过程, 该站点包含至少一个前端池或标准版服务器。

<div>


> [!IMPORTANT]  
> 执行此过程之前, 必须具备以下条件: 
> <UL>
> <LI>
> <P>必须在中心&nbsp;站点设置 Lync Server 2013 通信软件。</P>
> <LI>
> <P>中介服务器必须部署在中心站点。</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>定义 PSTN 网关

1.  单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync 服务器**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中, 展开中心网站, 展开 "**分支 Office 网站**", 展开要为其定义公共交换电话网络 (PSTN) 网关的分支网站的名称, 然后展开 "**共享组件**"。

3.  右键单击 " **PSTN 网关**", 然后单击 "**新建 IP/PSTN 网关**"。

4.  在 "**定义新的 IP/PSTN 网关**" 对话框中, 单击 "**网关 FQDN" 或 "IP 地址**", 然后键入要在分支站点部署的网关的完全限定的域名 (FQDN) 或 ip 地址。

5.  单击 "侦听端口", 选择 " **IP/PSTN 网关**", 然后接受默认值。

6.  在 " **SIP 传输协议**" 列表中, 单击网关使用的传输协议, 然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 出于安全考虑, 强烈建议使用支持传输层安全 (TLS) 的 PSTN 网关。

    
    </div>

<div>


> [!TIP]  
> 使用 cmdlet <STRONG>Set-CsPstnGateway</STRONG>修改 PSTN 网关的属性。 有关详细信息, 请参阅 Lync Server Management Shell 帮助中的 "<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">设置 CsPstnGateway</A>"。



</div>

分支站点恢复的**下一步**: 为[Lync Server 2013 中的分支站点恢复配置用户](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

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

