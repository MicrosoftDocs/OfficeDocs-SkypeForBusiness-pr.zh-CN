---
title: "Microsoft Teams 中的服务质量 (QoS)"
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 02/16/2018
ms.topic: article
ms.service: msteams
description: "针对 Microsoft Teams 的服务质量 (QoS) 准备贵组织的网络。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 61bebd64c7d1478c16e114631b696dee2bf59625
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="quality-of-service-qos-in-microsoft-teams"></a>Microsoft Teams 中的服务质量 (QoS)
==========================================
本指南将帮助你针对 Teams 的服务质量 (QoS) 准备贵组织的网络。


服务质量 (QoS) 机制允许你对特定类型的网络流量进行优先排序。 为提供企业级用户体验，对实时通讯服务（如 Teams）的流量进行优先排序至关重要。 为了使 QoS 真正有效，必须配置端到端的 QoS 兼容连接（PC、网络交换机和路由器到云），因为此路径中的任何部分无法支持 QoS 都可能会降低整个通话的质量。


![说明组织网络与 Office 365 服务之间关系的图的屏幕截图](media/Qos-in-Teams-Image1.png)

 

大多数情况下，互联网络是非托管网络，即互联网连接。 解决端到端 QoS 的一个可用选项是 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)。 我们建议仍在你控制的网络部分（即本地网络）实施 QoS。 这会提高整个部署中实时通讯工作负荷的质量，并化解现有部署中的瓶颈。 

## <a name="objectives"></a>目标 

本指南重点介绍如何对实时通讯流量（即语音和视频）进行优先排序。 其他类型的流量也可以根据需要进行优先排序。

有多种方式对流量进行优先排序，最常用的是使用区分服务代码点 (DSCP) 标记。 这可以根据端口范围，但也需通过组策略对象进行应用。 本文档中将会介绍这两个方面。

通过组策略对象 (GPO) 控制 DSCP 标记可以确保加入域的计算机收到正确设置，且这些设置仅由管理员来管理。 

QoS 仅当在将呼叫方连接到被叫方的所有链路上实施时才有效，请务必了解这一点。 如果我们在内部网络上使用 QoS，并且用户从远程位置登录，我们只能在内部的托管网络内进行优先排序。 通过实施 VPN 远程位置可能可以收到托管连接，但不建议通过 VPN 运行实时通讯流量。

> [!NOTE]
> 我们建议为 VPN 连接的远程用户实施拆分隧道，以最大限度地改进用户体验。 有关详细信息，请参阅文档 [VPN 拆分隧道部署指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 )。

在具有跨越大洲的托管链接的全局组织中，强烈建议使用 QoS，因为与本地网络 (LAN) 相比其带宽有限。

## <a name="quality-of-service"></a>服务质量

为了给网络上的应用程序提供有保证的服务级别，基础网络设备必须有办法对不同类型的流量进行分类。 例如，如果希望语音得到更好的处理，路由器必须能够区分语音流量和正常的 Web 浏览流量。 

区分服务 (DiffServ) 提供了一个框架，其中流量由网络设备根据 IPv4/IPv6 包的标题中的服务类型 (ToS) 字段进行处理。 DiffServ 字段最重要的六个数字称为区分服务代码点 (DSCP)。 使用此框架，可以将流量分为特定类型的流量（语音），然后进行标记（101110，或十进制 46），例如当网络设备处理这些标记时，可以对流量进行相应地优先排序（本示例中为加速转发）。

当网络流量进入路由器时，流量将置于队列中，如果没有 QoS，尤其是当仅有一个队列时，数据将按先进先出的顺序处理。这意味着，语音流量（对延迟非常敏感）可能会被在线流服务的流量卡住。 实施 QoS 时，可以定义多个队列，它们具有不同的拥挤管理功能（如 Cisco 的优先排队 (PQ) 和基于类的加权公平队列 (CBWFQ)）以及拥挤避免功能（如加权随机早期检测 (WRED)）。

![说明 Teams 中 QoS 队列的图的屏幕截图。](media/Qos-in-Teams-Image2.png)

图 1：QoS 队列可视化

这些内容就绪后，可以提供可预测的服务质量，因为基础的托管网络现在已经了解如何对流量进行分类、标记和优先排序。 从 Teams 角度看，最重要的配置项是数据包的分类和标记，但要使应用程序的配置与基础网络配置相符，必须进行谨慎规划，以使端到端 QoS 成功。

## <a name="qos-scenarios"></a>QoS 方案

为 Teams 实施 QoS 时，我们以四个开始方案为依据制定了指南：

1.  你已部署或正在部署 Teams 并且正在计划通过基于端口的标记实施 QoS。 基于端口的标记是最可靠的的方法，因为它在所有平台中一致工作且最易于实施。 

2.  你已部署或正在部署 Teams 并且正在计划通过组策略对象标记实施 QoS。 此方案有时会与方案 1 结合使用。 此方案非常有效（如下所述），但需要注意的是，它仅适用于已加入域的 Windows 客户端。 任何不是已加入域的 Windows 客户端的设备不会启用 QoS\DSCP 标记。 

3.  你已部署 Skype for Business Online（包括 QoS 标记）且正在部署 Teams。 如果是你，Teams 将遵循现有配置，并且将使用与 Skype for Business 客户端相同的端口范围和标记。 不需要进行额外配置。 
    > [!NOTE]
    > 如果你正在使用通过组策略的应用程序名称 QoS 标记，应将“Teams.exe”添加为应用程序名称。
4.  你已部署或正在部署 Teams 并且想要通过基于端口的标记使用自定义端口范围实施 QoS。

## <a name="recommended-differentiated-services-code-point-dscp-markings"></a>建议的区分服务代码点 (DSCP) 标记

第一步是利用具有 DSC 值的非重叠唯一端口范围对流量（如音频和视频）进行分类。 此处分配的 DSC 值将根据网络配置，确定网络中的流量优先级。 每个工作负荷都有自己的 DSCP 值，尽管有些客户可能会对语音和视频设置相同的值，让他们在网络中具有相同优先级。 

要使用的 DSCP 值取决于工作负荷的优先级。 例如，业务要求可能决定使用与视频相同的优先级（因此会标记与视频相同的 DSCP 值）处理应用程序共享。 其他环境可能已有 QoS 策略。 

下面的表 1 显示了将 Teams 与 ExpressRoute 结合使用时所需的 DSCP 标记。 对于不确定在自己环境中使用哪些标记的客户而言，这是一个很好的起点。 要了解详细信息，请阅读 [ExpressRoute QoS 要求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)。


| 客户端源端口|协议|媒体类别|常用 DSCP 值|DSCP 类|
|---------|---------|---------|---------|---------|
| 50,000 – 50,019|TCP/UDP|音频|46|加速转发 (EF)|
| 50,020 – 50,039|TCP/UDP|视频|34|保证转发 (AF41)|
| 50,040 – 50,059|TCP/UDP|应用程序/桌面共享和文件传输|18|类选择器 (CS3)|

表 1：DSCP 标记

下面是使用表 1 中的信息时的一些注意事项：

- 文件共享和应用程序共享使用相同的源端口范围，因此，在使用基于端口的标记时将使用相同的 DSCP 标记。 因此，它还会确定哪个优先级对*两种*模式（交互式或默认）最适用。
    
- 如果计划在未来实施 ExpressRoute 且尚未实施 QoS，建议遵循上述指南，因此发送者和接收者的 DSCP 值将相同。 
    
## <a name="source-ports-used-by-teams"></a>Teams 使用的源端口

在 Teams 中，应根据不同工作负荷使用的源端口配置 QoS。 此时服务器端和客户端的端口范围均不可配置。 

为部署 QoS，请使用表 2 中列出的客户端源端口范围及其相关的 QoS DSCP 标记。

| 客户端源端口|协议|媒体类别|常用 DSCP 值|DSCP 类|
|---------|---------|---------|---------|---------|
| 50,000 – 50,019|TCP/UDP|音频|46|加速转发 (EF)|
| 50,020 – 50,039|TCP/UDP|视频|34|保证转发 (AF41)|
| 50,040 – 50,059|TCP/UDP|应用程序/桌面共享和文件传输|18|类选择器 (CS3)|

表 2：客户端源端口范围

> [!NOTE]
> 如果你已根据 Skype for Business Online 的源端口范围配置 QoS，相同配置将适用于 Teams，无需进行其他更改。 如果你已经部署 Skype for Business 服务器（本地），则需要重新设计 QoS 策略。

## <a name="setting-differentiated-services-code-point-dscp-markings"></a>设置区分服务代码点 (DSCP) 标记

有多种方法设置正确的 DSCP 标记以进行流量分类。

- 端点处的 DSCP 标记：通常这是首选选项，因为端点本身可提供正确标记。 目前这可以使用 GPO 完成，但这仅在已加入域的 Windows 客户端上可行。 例如，Mac OSX 或移动客户端不提供使用 DSCP 值标记流量的机制。

- 基于端口，使用路由器上的 ACL：这在 Windows 和 Mac 的异构环境中是常用选项。 在此方案中，网络团队根据为每种模式定义的源端口范围标记入口/出口路由器（通常位于广域网 (WAN)）的流量。 这种方法适用于各种平台，但它仅在 WAN 边缘进行标记，而不是一直标记到客户端计算机，并且会产生管理费用。
    
- 在客户端上使用 DSCP 标记，在路由器上使用基于端口的 ACL。
    
如果可行，我们建议结合使用两者，以便使用 GPO 控制大部分客户端，同时使用基于端口的 DSCP 标记确保移动客户端、Mac 和其他客户端仍会获得（部分）QoS 处理。

可以使用组策略内基于策略的 QoS 为 Teams 客户端中的预定义源端口范围设置 DSCP 值。 下表使用表中指定的端口范围为每种工作负荷创建策略。

| 客户端流量类型|端口范围起始值|端口范围结束值|DSCP 值|
|---------|---------|---------|--------|
| 音频|50000|50019|46|
| 视频|50020|50039|34|
| 应用程序共享|50040|50059|18|
| 文件传输|50040|50059|18|

表 3：按流量类型的端口范围

注意：Teams 设置的端口范围无法更改。 有关最新信息，请查看此页面：https://support.microsoft.com/ kb/2409256

确定端口范围后，下一步是在组策略对象 (GPO) 内配置基于策略的 QoS 设置。 有关这些步骤的详细信息，请访问 [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx)。 

必须在客户端计算机上刷新组策略，然后你创建的新策略才会生效。 尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：

        gpudate.exe /force

此命令可以从在管理员凭据下运行的任何命令窗口运行。 若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。

## <a name="verifying-the-dscp-markings-in-gpo"></a>验证 GPO 中的 DSCP 标记

要验证是否已设置 GPO 的值，请执行下列步骤：

1.  使用 gpresult 验证本地 PC 是否已收到 GPO 的设置。 gpresult /R >gp.txt 将生成一个报告并发送到文本文件 gp.txt。

    ![运行 gpresult 命令的管理员命令提示符的屏幕截图。](media/Qos-in-Teams-Image3.png)

    图 2：验证应用的组策略对象
    > [!NOTE]
    > 或者，你可以运行 gpresult /H gp.html，以更加用户友好的 HTML 报告形式生成相同数据。 
2.  在生成的文件中查找标头“应用的组策略对象”并验证应用的策略列表中包含之前创建的 GPO 的名称。 

3.  打开注册表编辑器并导航到：

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    验证下面的表 3 中列出的注册表值。
    
    | 名称 | 类型 | 数据|
    |---------|---------|---------
    | 应用程序名称|REG_SZ|Teams.exe|
    | DSCP 值|REG_SZ|46|
    | 本地 IP|REG_SZ|*|
    | 本地 IP 前缀长度|REG_SZ|*|
    | 本地端口|REG_SZ|50000-50019|
    | 协议|REG_SZ|*|
    | 远程 IP|REG_SZ|*|
    | 远程 IP 前缀|REG_SZ|*|
    | 远程端口|REG_SZ|*|
    | 限制率|REG_SZ|-1|
    
    表 3：QoS 的 Windows 注册表值

4.  验证应用程序名称对你使用的客户端是否正确，并验证 DSCP 值和本地端口是否反映了 GPO 中的设置。

## <a name="validating-qos-analyzing-teams-traffic-on-the-network"></a>验证 QoS：分析网络上的 Teams 流量

GPO 设置的 DSCP 值需要从呼叫方呈现给被叫方，以使 QoS 生效。 通过检查 Teams 客户端生成的流量，我们可以验证遍历网络时 DSCP 是否未更改或者未消失。 

我们倾向于捕获网络入口点的流量。 可以在交换机或路由器上使用端口镜像，以帮助捕获网络上的流量。 

### <a name="looking-at-network-traffic-using-network-monitor"></a>使用网络监视器查看网络流量

网络监视器是一款可以从 Microsoft 下载以分析流量的工具。 下载[网络监视器 3.4](https://www.microsoft.com/download/4865)。

连接到运行网络监视器的 PC 上配置为端口镜像的端口并开始捕获数据包。 使用 Skype for Business 客户端拨打电话。 在挂断电话之前确保媒体已建立。 停止捕获，创建与拨打电话的 PC 的源 IP 相匹配的显示筛选器，并将 DSCP 值 46 (hex 0xb8) 定义为搜索条件以缩小筛选范围：

Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

![网络监视器中“显示筛选器”对话框的屏幕截图，显示要应用的筛选器。](media/Qos-in-Teams-Image4.png)


单击“应用”****以激活筛选器。 在“帧摘要”****窗口中，选择第一个 UDP 包并查看帧详细信息：

![网络监视器中“帧详细信息”对话框的屏幕截图，突出显示 DSCP 设置。](media/Qos-in-Teams-Image5.png)

扩展 IPv4 并查看 DSCP 行末尾的值。 在本示例中，我们看到 DSCP 值设置为 46，这是正确的，因为使用的源端口是 50019，这告诉我们工作负荷是语音。 

为 GPO 标记的每个工作负荷重复执行验证。 

> [!NOTE]
> 验证标记对点对点流量也同样适用。 可以通过在两个客户端上安装网络监视器并在这两个客户端之间拨打电话来完成此操作。 按上面所述的相同方式查看客户端之间的媒体流量。

### <a name="sample-filters-to-use-for-network-monitor-or-wireshark"></a>用于网络监视器或 Wireshark 的示例筛选器

|用法  |示例筛选器  |
|---------|---------|
|语音（注意：必须关闭复用）     |   udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46      |
|视频     | udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34        |
|屏幕共享     |  udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18       |

### <a name="filter-media-traffic-from-microsoft-relays-requires-azure-expressroutehttpsazuremicrosoftcomservicesexpressroute"></a>筛选器：来自 Microsoft 中继的媒体流量（需要 [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)）

{52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} 中的 ip.src 和 {3479 3480 3481} 中的 (udp.srcport 或 (udp.srcport ge 50000 和 udp.srcport lt 60000))

### <a name="filter-media-traffic-to-microsoft-relays"></a>筛选器：发送到 Microsoft 中继的媒体流量

{52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} 中的 ip.dst 和 {3479 3480 3481} 中的 (udp.dstport 或 (udp.dstport ge 50000 和 udp.dstport lt 60000))


你应该会看到发送到和来自 Microsoft 中继的媒体流量。 你可以检查 Wireshark 中 IP 层上的 DSCP 标记，如下一节中所述。

### <a name="expected-dscp-markings"></a>预期的 DSCP 标记

音频流：46

视频流：34

数据流：18

### <a name="filter-dscp-condition-to-network"></a>筛选器：网络的 DSCP 条件

{46 34 18} 中的 ip.dsfield.dscp



### <a name="looking-at-network-traffic-using-wireshark"></a>使用 Wireshark 查看网络流量

Wireshark (https://www.wireshark.org/) 是一款功能强大的功能，允许用户筛选和记录网络数据以供进一步分析。 连接到运行 Wireshark 的 PC 上配置为端口镜像的端口并开始捕获数据包。 使用 Teams 客户端拨打电话。 在挂断电话之前确保媒体已建立。

停止数据包跟踪并创建仅显示安装 Teams 客户端的 PC 的源 IP 的筛选器，例如 *ip.src_host == 192.168.137.201*。查找使用来自为语音指定的范围 (50,000 – 50,019) 的源端口的数据包：

![具有筛选器设置的 Wireshark 的屏幕截图](media/Qos-in-Teams-Image6.png)
 

在数据包详细信息窗格中标记数据包并展开 Internet 协议版本 4 (IPV4) 标头：

![突出显示区分服务代码点设置的 Wireshark 的屏幕截图。](media/Qos-in-Teams-Image7.png)
 

验证*区分服务代码点*的值是否与特定工作负荷的值匹配，本示例中语音的值为 46（二进制 101110）。

为 GPO 标记的每个工作负荷重复执行验证。

> [!NOTE]
> 验证标记对点对点流量适用。 可以通过在两个客户端上安装 WireShark 或网络监视器并在这两个客户端之间拨打电话来完成此操作。 按上面所述的相同方式查看客户端之间的媒体流量。

## <a name="summary"></a>摘要

要提供 Teams 企业级体验，服务质量的重要性不容忽视。 但是，必须始终牢记，QoS 仅对正确托管的网络有效。 因此，部署团队必须与网络团队密切合作，确保在网络层传递正确的信息，理想情况是从端到端进行托管。

