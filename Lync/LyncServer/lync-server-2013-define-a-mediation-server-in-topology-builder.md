---
title: 'Lync Server 2013: 在拓扑生成器中定义中介服务器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓扑生成器中定义中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-25_

按照本主题中的步骤, 使用拓扑生成器定义独立中介服务器或在你以前未部署企业语音的网站上使用前端池的池 collocated。

你可以使用管理员组的成员帐户定义拓扑。

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>定义中介服务器 collocated 到前端池

按照本主题中的步骤, 使用拓扑生成器将中介服务器 collocated 定义到尚未部署企业语音的网站中的前端池。

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>将中介服务器添加到前端池

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器的控制台树中, 展开要为其定义前端池的网站的名称。

3.  在控制台树中, 右键单击所需的前端池类型, 然后单击 "**新建前端池"。**

4.  在“定义新的前端池”**** 向导中导航，直到到达“选择并置服务器角色”**** 页。

5.  在 "**选择 collocated 服务器角色**" 中, 选中 " **Collocate 中介服务器**" 选项。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>如果所选的前端池的类型为 "企业版", 则将在该前端池的所有前端服务器上安装中介服务器组件。</P>
    > <LI>
    > <P>中介服务器使用的<STRONG>下一个跃点池</STRONG>将是中介服务器 Collocated 的前端池。</P>
    > <LI>
    > <P>中介服务器使用的<STRONG>edge 池</STRONG>将是与中介服务器 Collocated 的前端池关联的同一 edge 池。</P></LI></UL>

    
    </div>

6.  单击 "**设为默认值**" 使用此前端池将来自 Microsoft Office 通信服务器 2007 R2 的呼叫路由到 PSTN。

7.  完成将一个或多个对等方关联到前端池后, 单击 "**完成**"。
    
    <div>
    

    > [!NOTE]  
    > 在你继续执行企业语音部署过程中的下一步骤之前, 请确保使用你指定的 Fqdn 将中介服务器池 (即具有中介服务器组件 collocated 的前端池) 使用。

    
    </div>

8.  接下来, 按照在 "部署指南" 文档中的 "[发布 Lync server 2013](lync-server-2013-publish-the-topology.md)中的拓扑" 中的过程操作, 将中介服务器添加到拓扑中, 然后再转到修改中介服务器侦听端口的下一步 (如有必要)。 你必须在每次使用拓扑生成器定义或修改拓扑时发布你的拓扑。

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>定义独立中介服务器

按照本主题中的步骤使用拓扑生成器在尚未部署企业语音的网站上定义独立的中介服务器或池。

如果你已在此网站上部署了 collocated 到前端池的中介服务器, 则可以跳过此部分并[在 lync server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md), 然后再继续[在 lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)。

<div>


> [!NOTE]  
> 本部分假设你已经设置了至少一个前端池, 如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或标准版服务器</A>中所述, 并在部署指南中的<A href="lync-server-2013-publish-the-topology.md">lync Server 2013 中发布拓扑</A>。文档.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>添加中介服务器

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器的控制台树中, 展开要为其定义中介服务器的网站的名称。

3.  在控制台树中, 右键单击 "**中介池**" 节点, 然后单击 "**中介服务器池**"。

4.  在 "**定义新中介池**" 中, 键入中介服务器池完全限定的域名 (FQDN)。

5.  接下来，执行下列操作之一：
    
      - 如果你想要在池中部署多个中介服务器以提供高可用性, 请选择 "**多台计算机池**"。
        
        <div>
        

        > [!NOTE]  
        > 必须部署 DNS 负载平衡以支持具有多个中介服务器的中介服务器池。 有关详细信息, 请参阅规划文档中的在<A href="lync-server-2013-dns-load-balancing.md">Lync server 2013 中</A>的 "在中介服务器池上使用 Dns 负载平衡" 部分。

        
        </div>
    
      - 如果你只希望在池中部署一个中介服务器, 因为你不需要高可用性, 然后选择 "**单个计算机池**"。 跳过以下步骤。

6.  如果在前一步骤中选择了“多计算机池”****，那么在“定义此池中的计算机”**** 项上单击“计算机 FQDN”****，键入此池中每个服务器的 FQDN，然后单击“添加”****。 对要添加到池中的所有其他中介服务器重复此步骤。 定义该池中的所有计算机后，单击“下一步”****。

7.  在 "**选择下一跃点"** 页面上, 单击 "**下一跃点池**", 单击将使用此中介服务器池的前端池的 FQDN, 然后单击 "**下一步**"。

8.  在“选择边缘服务器”**** 页上执行下列操作之一：
    
      - 如果你想要为已启用企业语音的外部用户提供 PSTN 连接, 请在 "**选择此中介服务器使用的 Edge 池**" 下, 单击将使用此中介服务器池提供 PSTN 连接的 edge 服务器池的 FQDN这些外部用户, 然后单击 "**下一步**"。
    
      - 如果您不打算为企业语音启用外部用户, 或者如果您不想在内部网络外部向用户提供 PSTN 连接, 请单击 "**下一步**"。

9.  接下来, 按照在 "部署" 文档中的 "在[Lync server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)" 中的过程将中介服务器添加到拓扑中。 你必须在每次使用拓扑生成器构建或修改拓扑时发布你的拓扑, 以便可以使用数据为运行 Lync Server 的服务器安装文件。 然后, 继续执行后续步骤以在中介服务器上修改侦听端口 (如有必要)。

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>定义中介服务器侦听端口

按照本主题中的步骤, 使用拓扑生成器定义中介服务器或池将接受来自网关对等的传入连接的侦听端口。

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>修改中介服务器侦听端口

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器的控制台树中, 展开 "**中介池**" 节点, 然后右键单击以前创建的中介服务器。

3.  默认情况下, 中介服务器上的 SIP 侦听端口为来自 Lync Server 的 TLS 流量 5070, 5067 用于来自对等 (网关、PBXes 或 SBCs) 的 TLS 流量。 默认情况下，TCP 端口处于禁用状态。 如果有不支持 TLS 的网关，则必须启用 TCP 端口。

4.  指定所需的 TLS 或 TCP 侦听端口范围中介服务器将接受来自 PSTN 网关的传入连接。
    
    <div>
    

    > [!NOTE]  
    > 如果未选中“启用 TCP 端口”<STRONG></STRONG>，则不需要输入 TCP 端口范围。 此设置是可选的。

    
    </div>

接下来,[在 Lync server 2013 的拓扑生成器中定义一个网关](lync-server-2013-define-a-gateway-in-topology-builder.md), 并按照在[Lync Server 2013 中安装中介服务器文件](lync-server-2013-install-the-files-for-mediation-server.md)中的步骤在池中的每个中介服务器上安装文件。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

