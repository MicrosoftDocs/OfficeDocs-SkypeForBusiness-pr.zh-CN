---
title: Lync Server 2013：在拓扑生成器中定义网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40881b38c83ebf254a60773060b642d183b7dfaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓扑生成器中定义网关

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

按照以下步骤使用拓扑生成器定义*对等方*，您可以将中介服务器与之关联，以便为启用企业语音的用户提供到公用电话交换网（PSTN）的连接。 对中介服务器的对等方可以是通过配置 SIP 中继连接到的 Internet 电话服务提供商（ITSP）的 PSTN 网关、ip-pbx 或会话边界控制器（SBC）。

<div>


> [!NOTE]  
> 本主题假定您已至少在一个具有并置或独立中介服务器的中心站点中设置了一个内部前端池或 Standard Edition 服务器，如在部署文档中的<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定义和配置前端池或 Standard edition 2013 server</A>中所述和在<A href="lync-server-2013-publish-the-topology.md">lync Server 2013 中发布拓扑</A>中所述。 本主题还假设您已验证您的基础结构是否满足 Lync server 2013 中的<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">企业语音软件先决条件</A>中所述的先决条件，以及<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">lync Server 2013 中企业语音的安全性和配置先决条件</A>。



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>定义中介服务器的对等方

1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在 "Lync Server 2013" 下，为您的网站名称 "共享组件"，右键单击 " **PSTN 网**关" 节点，然后单击 "**新建 pstn 网关**"。
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  在“定义新的 IP/PSTN 网关”**** 中，键入对等方的完全限定域名 (FQDN) 或 IP 地址，然后单击“下一步”****。
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > 如果将传输层安全性（TLS）指定为传输类型，则必须指定 FQDN，而不是中介服务器的对等方的 IP 地址。

    
    </div>

4.  定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”****。
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  定义 PSTN 网关的*根中继*。 中继是中介服务器与元组唯一标识的网关之间的逻辑连接。
    
    {中介服务器 FQDN、中介服务器侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}
    
      - 在拓扑生成器中定义 PSTN 网关时，必须定义根中继才能成功将 PSTN 网关添加到拓扑中。
    
      - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  在 " **IP/PSTN 网关侦听端口**" 下，键入网关、PBX 或 SBC 将用于来自中介服务器且将与 PSTN 网关的根中继关联的 SIP 消息的侦听端口。 （默认情况下，在 PSTN 网关、PBX 或 SBC 上，端口为传输控制协议（TCP）和5067（对于传输层安全性（TLS））为5066。 在分支站点的 Survivable 分支设备上，默认端口为5081，用于 TLS 的 TCP 和5082。

7.  在“SIP 传输协议”**** 下，单击对等方使用的传输类型，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 出于安全考虑，强烈建议您将对等部署到可以使用 TLS 的中介服务器。

    
    </div>

8.  在 "**关联的中介服务器**" 下，选择要与此 PSTN 网关的根中继相关联的中介服务器池。

9.  在 "**关联的中介服务器端口**" 下，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多个中继支持时，可以在中介服务器上定义多个 SIP 信号端口，以用于与多个 PSTN 网关进行通信。 在定义中继时，<STRONG>关联的中介服务器端口</STRONG>必须位于中介服务器允许的各个协议的侦听端口范围内。 此端口范围在 Lync Server 2013 和中介池下定义。 右键单击相关的中介服务器池，然后选择 "<STRONG>编辑属性</STRONG>"。 在“侦听端口”<STRONG></STRONG>字段中指定端口范围。

    
    </div>

10. 单击“完成”****。

<div>


> [!IMPORTANT]  
> 完成此步骤之前，请确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。



</div>

接下来，若要将对等方添加到拓扑中，请按照部署文档中的在[Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)中的过程操作。 您必须在每次使用拓扑生成器构建或修改拓扑时发布拓扑，以便数据可用于安装运行 Lync Server 的服务器的文件。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改拓扑生成器中的中继](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

