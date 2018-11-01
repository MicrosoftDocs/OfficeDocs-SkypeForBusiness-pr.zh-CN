---
title: Lync Server 2013：PSTN 连接组件
TOCTitle: PSTN 连接组件
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398504(v=OCS.15)
ms:contentKeyID: 49313149
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 PSTN 连接组件

 

_**上一次修改主题：** 2016-12-08_

企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。此外，用户在发起和接收呼叫时应不必了解底层技术。从用户的角度来看，企业语音基础结构与 PSTN 之间的呼叫应该就像是另一个 SIP 会话。

对于 PSTN 连接，既可以部署 SIP 中继，也可以部署 PSTN 网关（使用 PBX，也称为直接 SIP 链接；或不使用 PBX）。

## SIP 中继

作为使用 PSTN 网关的替代方案，可以使用 SIP 中继将企业语音解决方案连接到 PSTN。SIP 中继可以实现以下方案：

  - 企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。

  - 通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。

使用此部署解决方案需要 SIP 中继服务提供商。

## PSTN 网关

PSTN 网关是在企业语音基础结构与 PSTN 或 PBX 之间转换信号和媒体的第三方设备。PSTN 网关与中介服务器配合工作，以向企业语音客户端提交 PSTN 或 PBX 呼叫。中介服务器还将来自企业语音客户端的呼叫提交到 PSTN 网关，以便路由到 PSTN 或 PBX。有关与 Microsoft 一起提供适用于 Lync Server 的设备的合作伙伴列表，请访问 Microsoft 统一通信合作伙伴网站，网址为 [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0x804)。

## 专用交换机

如果您现有的语音基础结构使用专用交换机 (PBX)，则您可以将 PBX 与 Lync Server 企业语音结合使用。

支持的企业语音-PBX 集成方案包括：

  - 支持媒体旁路的 IP-PBX，具有中介服务器。

  - 要求使用单独的 PSTN 网关的 IP-PBX。

  - 时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。

> [!NOTE]  
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。媒体旁路仅支持 <a href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</a> 上的“统一通信开放式互操作性程序 – Lync Server”中列出的产品和版本。



有关提供企业语音解决方案的合作伙伴的详细信息，请访问 Microsoft 统一通信合作伙伴网站，网址为 [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。

有关提供企业语音硬件解决方案（包括 PSTN 网关）的合作伙伴的详细信息，请访问 Microsoft 统一通信合作伙伴网站 [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。

