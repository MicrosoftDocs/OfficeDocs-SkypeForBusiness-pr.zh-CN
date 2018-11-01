---
title: Lync Server 2013：在拓扑生成器中定义网关
TOCTitle: 在拓扑生成器中定义网关
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425945(v=OCS.15)
ms:contentKeyID: 49312706
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 拓扑生成器中定义网关

 

_**上一次修改主题：** 2012-10-04_

按照下列步骤使用 拓扑生成器来定义可将 中介服务器与之关联的 *对等方* ，以便为启用 企业语音的用户提供到公用电话交换网 (PSTN) 的连接。 中介服务器的对等方可以是通过配置 SIP 中继连接到的 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。

> [!NOTE]  
> 本主题假定您已经在至少一个具有并置或独立 中介服务器的中央站点中设置了至少一个内部 前端池或 Standard Edition Server，如部署文档的 <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器</a> 和 <a href="lync-server-2013-publish-the-topology.md">在 Lync Server 2013 中发布拓扑</a>中所述。本主题还假定您已确认基础结构满足 <a href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync Server 2013 中企业语音的软件先决条件</a>和 <a href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync Server 2013 中企业语音的安全性和配置先决条件</a>中所述的先决条件。



## 定义中介服务器的对等方

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在 Lync Server 2013、网站名称和共享组件下，右键单击“PSTN 网关”节点，然后单击“新建 PSTN 网关”。
    
    ![拓扑生成器 Lync Server 2013](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "拓扑生成器 Lync Server 2013")

3.  在“定义新的 IP/PSTN 网关”中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”。
    
    ![IP/PSTN 网关](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "IP/PSTN 网关")
    
    > [!NOTE]  
    > 如果您作为传输类型指定传输层安全性 (TLS)，则必须指定 FQDN，而不是 中介服务器 对等的 IP 地址。
    


4.  定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”。
    
    ![IP 地址](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "IP 地址")

5.  定义 PSTN 网关的 *根中继* 。中继是 中介服务器和元组唯一标识的网关之间的逻辑连接。
    
    { 中介服务器 FQDN， 中介服务器 侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}
    
      - 在 拓扑生成器中定义 PSTN 网关时，您必须定义根中继才能成功将 PSTN 网关添加到拓扑中。
    
      - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
    ![定义网关：根中继](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "定义网关：根中继")

6.  在“IP/PSTN 网关的侦听端口”下，键入网关、PBX 或 SBC 将用于来自将与 PSTN 网关的根中继关联的 中介服务器的 SIP 消息的侦听端口。（默认情况下，PSTN 网关、PBX 或 SBC 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 端口为 5067。在分支站点的 Survivable Branch Appliance 上，默认 TCP 端口为 5081，默认 TLS 端口为 5082。）

7.  在“SIP 传输协议”下，单击对等方使用的传输类型，然后单击“确定”。
    
    > [!NOTE]  
    > 为了安全起见，我们强烈建议您部署可使用 TLS 的 中介服务器的对等方。
    


8.  在“关联的中介服务器”下，选择中介服务器池以与此 PSTN 网关的根中继关联。

9.  在“关联的中介服务器端口”下，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。
    
    > [!NOTE]  
    > 利用 Lync Server 2013 中的多个中继支持，可在要用于与多个 PSTN 网关通信的 中介服务器上定义多个 SIP 信号端口。定义中继时，“关联的中介服务器端口”必须位于中介服务器允许使用的各个协议的侦听端口的范围中。此端口范围是在 Lync Server 2013 和中介池下定义的。右键单击所关注的中介服务器池，并选择“编辑属性”。在“侦听端口”字段中指定端口范围。
    


10. 单击“完成”。

> [!IMPORTANT]
> 完成此步骤之前，请确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。


接下来，要向拓扑中添加对等方，请按照部署文档的 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)中的过程进行操作。每次使用 拓扑生成器构建或修改拓扑时，必须先发布拓扑，然后才能使用数据安装运行 Lync Server 的服务器的文件。

## 另请参阅

#### 任务

[在 Lync Server 2013 中修改拓扑生成器中的中继](lync-server-2013-modify-a-trunk-in-topology-builder.md)

