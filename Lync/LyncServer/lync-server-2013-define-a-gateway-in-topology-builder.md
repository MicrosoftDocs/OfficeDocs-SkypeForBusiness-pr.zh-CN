---
title: 'Lync Server 2013: 在拓扑生成器中定义网关'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓扑生成器中定义网关

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-04_

请按照以下步骤使用拓扑生成器定义*对等*, 你可以将中介服务器与之关联, 以便为已启用企业语音的用户提供与公共交换电话网络 (PSTN) 的连接。 对中介服务器的对等可以是 PSTN 网关、IP PBX, 或通过配置 SIP 主干连接的 Internet 电话服务提供商 (ITSP) 的会话边界控制器 (SBC)。

<div>


> [!NOTE]  
> 本主题假定你至少已在一个中心网站中设置了一个具有 collocated 或独立中介服务器的内部前端池或标准版服务器, 如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">中定义和配置前端池或标准版服务器中所述。Lync Server 2013</A>和发布部署文档中<A href="lync-server-2013-publish-the-topology.md">lync server 2013 中的拓扑</A>。 本主题还假定你已验证你的基础结构是否满足<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync Server 2013 中的软件必备</A>条件中所述的先决条件, 以及如何在 lync 中使用<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">企业语音的安全和配置先决条件服务器 2013</A>。



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>为中介服务器定义对等

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在 "Lync Server 2013" 下, 您的网站名称, 右键单击 " **PSTN 网**关" 节点, 然后单击 "**新建 pstn 网关**"。
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  在“定义新的 IP/PSTN 网关”**** 中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”****。
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > 如果将传输层安全性 (TLS) 指定为传输类型, 则必须指定 FQDN, 而不是中介服务器对等的 IP 地址。

    
    </div>

4.  定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”****。
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  定义 PSTN 网关的 *根中继*。 主干是中介服务器和由元组唯一标识的网关之间的逻辑连接。
    
    {中介服务器 FQDN、中介服务器侦听端口 (TLS 或 TCP): 网关 IP 和 FQDN, 网关侦听端口}
    
      - 在拓扑生成器中定义 PSTN 网关时, 必须定义根干线才能成功地将 PSTN 网关添加到拓扑。
    
      - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  在 " **IP/PSTN 网关侦听端口**" 下, 键入网关、PBX 或 SBC 将用于来自中介服务器的将与 PSTN 网关根干线关联的 SIP 消息的侦听端口。 (默认情况下, 在 PSTN 网关、PBX 或 SBC 上, 端口是传输控制协议 (TCP) 和5067的传输层安全性 (TLS) 的5066。 在分支站点的 Survivable 分支设备上, 默认端口为适用于 TLS 的 TCP 和5082的默认端口5081。)

7.  在“SIP 传输协议”**** 下，单击对等方使用的传输类型，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 出于安全原因, 强烈建议你将对等部署到可以使用 TLS 的中介服务器。

    
    </div>

8.  在 "**关联的中介服务器**" 下, 选择要与此 PSTN 网关的根中继相关联的中介服务器池。

9.  在 "**关联的中介服务器端口**" 下, 键入中介服务器将用于来自网关的 SIP 消息的侦听端口。
    
    <div>
    

    > [!NOTE]  
    > 通过 Lync Server 2013 中的多个中继支持, 可以在中介服务器上定义多个 SIP 信号端口, 以便与多个 PSTN 网关进行通信。 定义主干时, 关联的<STRONG>中介服务器端口</STRONG>必须位于中介服务器允许的各个协议的侦听端口范围内。 此端口范围在 Lync Server 2013 和中介池下定义。 右键单击感兴趣的中介服务器池, 然后选择 "<STRONG>编辑属性</STRONG>"。 Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

10. 单击“**完成**”。

<div>


> [!IMPORTANT]  
> 在完成此步骤之前, 请确保你定义的对等正在运行, 并使用你指定的 FQDN 或 IP 地址。



</div>

接下来, 要将对等添加到拓扑中, 请按照在 "部署" 文档中的[Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)中的过程进行操作。 你必须在每次使用拓扑生成器构建或修改拓扑时发布你的拓扑, 以便可以使用数据为运行 Lync Server 的服务器安装文件。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中的拓扑生成器中修改主干](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

