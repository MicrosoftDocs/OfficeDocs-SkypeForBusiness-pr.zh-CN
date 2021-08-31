---
title: 规划紧急服务Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: 了解 Skype for Business Server 企业语音 中的增强型 9-1-1 (E9-1-1) 服务，包括位置获取和呼叫路由。
ms.openlocfilehash: 18cb4158e7e7d31772f365711b1ec5e0ed22357a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732751"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>规划紧急服务Skype for Business Server

了解 Skype for Business Server 企业语音 中的增强型 9-1-1 (E9-1-1) 服务，包括位置获取和呼叫路由。

Skype for Business Server部署中支持 (增强型 9-1-1) E9-1-1 企业语音服务。 E9-1-1 是一项紧急派发功能，对于来自办公楼和其他多租户设施的呼叫，该功能可将 9-1-1 呼叫与紧急响应位置 (ERL) 相关联，紧急响应位置包含市政（即街道）地址和其他更具体的位置信息，例如楼层号。 通过使用提供的 ERL，公共安全应答点 (PSAP) 可以立即向需要帮助的呼叫者派发第一批响应方，从而降低因疏忽而将响应方指向不正确或模糊不清的位置的风险。

> [!NOTE]
> Skype for Business Server现在支持为客户端配置多个紧急号码。 有关详细信息，请参阅[Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md)。

> [!NOTE]
> Skype for Business Server三个高级企业语音功能：呼叫允许控制、 (E9-1-1) 和媒体旁路。 有关这三项功能共同的规划信息的概述，请参阅 Skype for Business Server 中高级 企业语音[功能的网络Skype for Business Server。](network-settings-for-advanced-features.md)

Skype for Business Server支持从 Skype for Business 客户端和 Lync 电话 Edition 设备进行增强型 9-1-1 (E9-1-1) 呼叫。 为 E9-1-1 配置 Skype for Business Server 时，从 Skype for Business 或 Lync 电话 Edition 拨打的紧急呼叫包括紧急响应位置 (ERL) 位置信息。 ERL 包含市政（即街道）地址，以及有助于确定在办公楼和其他多租户设施中的更精确位置的其他信息。 当用户进行紧急呼叫时，Skype for Business Server通过中介服务器将呼叫音频以及位置和回拨信息路由到 E9-1-1 服务提供商。 E9-1-1 服务提供商会使用呼叫者的市政地址，将呼叫路由到为呼叫者的位置提供服务的公共安全应答点 (PSAP)，并沿着 PSAP 用来查找呼叫者的 ERL 的紧急服务查询键 (ESQK) 进行发送。

Skype for Business Server支持将紧急呼叫路由到 E9-1-1 服务提供商的两种方法：

- 到合格的 E9-1-1 服务提供商的会话初始协议 (SIP) 中继连接

- 到基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商的紧急位置标识号 (ELIN) 网关

使用 SIP 中继 E9-1-1 服务提供商时，需要向位置信息服务数据库添加 ELL，然后根据主街道地址指南 (MSAG) （由 E9-1-1 服务提供商维护）验证位置。 如果 E9-1-1 服务提供商收到没有位置信息或位置尚未根据 MSAG 进行验证的呼叫，E9-1-1 服务提供商将呼叫路由到国家/地区紧急呼叫响应中心 (ECRC) ，该中心配备专门培训的人员，这些人员会以语言方式获取呼叫者的位置（如果可能）并手动将呼叫路由到相应的 PSAP。  (某些 SIP 中继 E9-1-1 服务提供商还会为客户提供到 ECRC 的 PSTN 外线直拨 (DID) 号码，从而在 SIP 中继因任何原因失败的情况下，提供路由 9-1-1 呼叫的替代方法。) 

与时分多路复用 (TDM) 和基于 IP 的专用交换机 (PBX) 电话（具有固定位置）不同，Skype for Business 终结点可以非常移动。 部署 E9-1-1 功能时，Skype for Business Server 有助于确保无论呼叫者位于何处，紧急呼叫都可以路由到为呼叫者所在的位置服务 PSAP。 例如，如果用户的主办公室位于华盛顿州雷德蒙德，但用户从位于华盛顿州威奇托的分支机构的计算机拨打紧急呼叫，则基于 SIP 中继或基于 PSTN 的 E9-1-1 服务提供商将呼叫路由到格林威奇托的 PSAP，而不是雷德蒙德的 PSAP。

使用 ELIN 网关时，还可以将 ELIN 添加到位置信息服务数据库，但还包括每个位置的 ELIN 号码。 ELIN 号码会在紧急呼叫过程中变为紧急呼叫号码。 然后，您必须确保 PSTN 运营商将 ELIN 上载到自动位置标识 (ALI) 数据库。

> [!NOTE]
> Skype for Business连接的模拟设备无法从位置信息服务接收位置信息，也无法将位置传输给 E9-1-1 服务提供商。

 如果您使用 SIP 中继 E9-1-1 服务提供商选项并需要通过模拟电话支持 E9-1-1，则有以下两个选项：

- **传统 PS-ALI 选项** 如果在部署了模拟电话的每个站点都有本地 PSTN 网关，并且每个模拟电话都有 DID，则可直接使用专用交换机/自动位置标识 (PS-ALI) 服务提供商预配模拟设备的位置。 在这种情况下，配置特别设计的 Skype for Business 语音策略，并将其分配给模拟设备联系对象，以便来自这些电话的 E9-1-1 呼叫直接通过本地网关路由到为站点 (服务的 PSTN 提供商，而不是将呼叫路由到 E9-1-1 服务提供商 SIP 中继) 。 发出紧急呼叫后，与 PSTN 中继关联的 PS-ALI 提供商的数据库会将每个模拟电话的 DID 映射到一个物理位置并将此位置提供给 PSAP。 每当将电话移至不同的 ERL 时，必须通过 PS-ALI 服务提供商更新这些记录。

- **E9-1-1 服务提供商选项** 您可以在 E9-1-1 服务提供商处注册模拟电话 DID 及其对应的 ELL（如果 E9-1-1 服务提供商支持）。 如果提供商收到来自不包含 PIDF-LO Skype for Business Server的呼叫，提供商可以看到呼叫方 DID 号码上是否有数据库匹配项。 通过使用从数据库检索到的 ERL，提供商会自动将紧急呼叫路由到正确的 PSAP，PSAP 将接收模拟设备的 DID 和允许调度程序查找呼叫者位置的 ESQK 记录。

如果您使用 ELIN 网关选项并需要通过模拟电话支持 E9-1-1，则可以直接向 PS-ALI 服务提供商提供模拟设备的位置，如上面第一个选项中所述。

从Skype for Business Server，E9-1-1 过程可以分为两个阶段：

- 阶段 1：获取位置

- 阶段 2：将紧急呼叫路由至 E9-1-1 服务提供商

本节介绍这些阶段的工作原理。

如果您计划将基础结构配置为自动检测客户端位置，则首先需要确定将使用哪些网络元素将呼叫者映射到不同位置。 有关可能的选项的详细信息，请参阅[Define the network elements used to determine location in Skype for Business Server](network-location.md)。

## <a name="acquiring-a-location"></a>获取位置

在 Skype for Business Server E9-1-1 部署中，每个内部连接的 Skype for Business 或 Lync 电话 Edition 客户端会主动获取其自己的位置。 SIP 注册后，客户端在位置信息服务的位置请求中提供它自己知道的所有网络连接信息，位置信息服务是一种受复制的 SQL Server 数据库支持的 Web 服务。 每个中央站点池都有一个位置信息服务，该服务使用网络信息查询其记录中的匹配位置。 如果存在匹配项，则位置信息服务会向客户端返回位置。 如果没有匹配项，则可能提示用户手动输入位置（取决于位置策略设置）。 位置数据将以 Internet 工程任务组 (IETF) 标准化 XML 格式传输回客户端，称为“状态信息数据格式位置对象 (PIDF-LO)”。

Skype for Business 客户端包括 PIDF-LO 数据作为紧急呼叫的一部分，E9-1-1 服务提供商使用这些数据来确定相应的 PSAP，将呼叫与正确的 ESQK 一起路由到该 PSAP，从而允许 PSAP 调度程序获取呼叫者的位置。

下图显示了客户端Skype for Business如何获取位置 (基于 MAC 地址的第三方客户端 MAC 地址的位置方法除外) ：

![客户端如何获取位置图。](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

对于获取位置的客户端，必须执行下列步骤：

1. 管理员使用网络线路映射表填充位置信息服务 (，这些表将各种类型的网络地址映射到相应的紧急响应 (ERLS) ) 。

2. 如果使用 SIP 中继 E9-1-1 服务提供商，则管理员将针对 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 数据库验证 ERL 的市政地址部分。如果使用 ELIN 网关，则管理员将确保 PSTN 运营商会将 ELIN 上载到自动位置标识 (ALI) 数据库。

3. 在注册期间或发生网络更改时，内部连接的客户端会向位置信息服务发送包含客户端发现的网络地址的位置请求。

4. 位置信息服务查询其已发布记录的位置，如果找到匹配项，则以 PIDF-LO 格式将 ERL 返回到客户端。

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>使用 SIP 中继路由 E9-1-1 呼叫

使用 SIP 中继连接到合格的 E9-1-1 服务提供商是部署 E9-1-1 的一种方法。有关使用 ELIN 网关连接到基于公用电话交换网 (PSTN) E9-1-1 服务提供商的详细信息，请参阅[Routing E9-1-1 Calls by Using an ELIN Gateway](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway)。

下图显示了在使用 SIP 中继和合格的 E9-1-1 服务提供商时如何将紧急呼叫从 Skype for Business Server 路由到公共安全应答点 (PSAP) 。

**通过 SIP 中继路由 E9-1-1 呼叫**

![从 Lync Server 到 PSAP 的紧急呼叫路由。](../../media/Plan_LyncServer_E911_CallRouting.jpg)

从兼容的客户端拨打紧急呼叫Skype for Business Server：

1. 包含位置、呼叫者的回拨号码和可选的 (通知 URL) 会议回拨号码的 SIP INVITE 将路由到 Skype for Business Server。

2. Skype for Business Server匹配紧急号码，并基于在适用的位置策略) 中定义的 **PSTN** 用法值将呼叫 (路由到中介服务器，然后通过 SIP 中继从该服务器路由到 E9-1-1 服务提供商。

3. E9-1-1 服务提供商根据呼叫提供的位置将紧急呼叫路由至正确的 PSAP。当客户端在紧急呼叫中包括验证的紧急响应位置 (ERL) 时，提供商会自动将呼叫路由至正确的 PSAP。如果位置由用户手动输入，那么紧急呼叫响应中心 (ECRC) 会首先口头与呼叫者验证位置的准确性，再将紧急呼叫路由至 PSAP。

4. 如果为通知配置了位置策略，则向组织的一个或多个安全官员发送一个Skype for Business紧急通知即时消息。 此消息始终在安全人员的 () 屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员能够使用即时消息或语音快速响应紧急呼叫者。

5. 如果针对会议配置了位置策略，并且它受到 E9-1-1 服务提供商的支持，那么内部安全服务台会以单向或双向音频的方式加入到呼叫会议中。

6. 如果呼叫过早地中断，那么 PSAP 使用回拨号码直接联系呼叫者。

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>使用 ELIN 网关路由 E9-1-1 呼叫

统一通信开放互操作性计划中的一些合作伙伴提供启用了合格的紧急位置识别号码 (ELIN) 的网关，可以充当到合格的 E9-1-1 服务提供商的 SIP 中继连接的替代之选。 ELIN 网关支持与基于公用电话交换网 (PSTN) 的 E9-1-1 服务的 ISDN 或集中式自动信息计算 (CAMA) 连接。 有关提供 ELIN 网关的合作伙伴及其文档链接的详细信息，请参阅适用于[Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)的基础结构和适用于[Skype for Business。](../../../SfbPartnerCertification/certification/infra-gateways.md)

与 E9-1-1 服务提供商的 SIP 中继连接一样，ELIN 网关还可以将紧急呼叫路由到呼叫者最合适的公共安全应答点 (PSAP) ，但这些网关使用 ELIN 作为位置标识符。 为组织 (中的每个紧急响应位置 (ERL) 定义[ERL，](elin-gateways.md)有关详细信息，请参阅在 Skype for Business Server) 中管理 ELIN 网关的位置。

在将 ELIN 网关用于紧急呼叫时，Skype for Business Server SIP 中继连接的 E9-1-1 基础结构。 即，位置信息服务数据库向客户端Skype for Business位置，位置策略将启用该功能并定义路由。 但是，使用 ELIN 网关时，你需要将 ELIN 添加到位置信息服务数据库，让 PSTN 运营商将它们上载到 ALI (自动位置标识) 数据库。

当Skype for Business客户端从位置信息服务获取其位置时，该位置将包含 ELIN。 在紧急呼叫期间，ELIN 包括在发送到 ELIN 网关的位置中。 ELIN 网关将该呼叫识别为紧急呼叫并将呼叫方的号码交换为 ELIN。 然后 ELIN 网关使用 ELIN 作为呼叫号码将呼叫路由到 PSTN。 PSTN E9-1-1 提供商在 ALI 数据库中查找 ELIN，该数据库与主街道地址指南 (MSAG) 数据库是配套数据库。 然后 PSTN 根据 ALI 查询将呼叫发送到最适宜的 PSAP，随后 PSAP 根据 ALI 查询将首位响应者发送到呼叫者位置。 呼叫号码在 ELIN 网关上缓存预定义的一段时间以便回叫。 在回叫期间，PSAP 到达 ELIN 网关，后者将 ELIN 交换为呼叫者的直接拨入 (DID) 号码。

ELIN 网关仅支持来自组织网络的紧急呼叫。它们不支持从您网络外部发出的紧急呼叫。

> [!NOTE]
> 有关针对紧急呼叫使用 SIP 中继连接的详细信息，请参阅[Routing E9-1-1 Calls by Using a SIP Trunk](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk)。

下图显示了在使用 ELIN 网关时如何将紧急Skype for Business Server路由到 PSAP。

**使用 ELIN 网关路由 E9-1-1 呼叫**

![显示对紧急服务的呼叫如何通过中介服务器，然后到达紧急服务提供商。 之后，可以选择向现场安全发送 IM 和/或回叫原始呼叫者。](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. 包含位置、呼叫者的回拨号码和可选的 (通知 URL 和会议) 的 SIP INVITE 将路由到Skype for Business Server。

2. Skype for Business Server匹配紧急号码，然后根据在适用的位置策略 () 中定义的 **PSTN** 用法值将呼叫路由至中介服务器，然后从该服务器路由到 ELIN 网关。

3. ELIN 网关通过 ISDN 或 CAMA 中继将呼叫路由到 PSTN。

4. PSTN 将呼叫标识为紧急呼叫并将其路由到网路中的 E9-1-1 选择性路由器。E9-1-1 选择性路由器在 ALI 数据库中查找呼叫者的号码以获取地理位置。E9-1-1 选择性路由器根据从 ALI 数据库中检索到的位置信息将呼叫发送到最合适的 PSAP。

5. 如果为通知配置了位置策略，则向组织的一个或多个安全官员发送一个Skype for Business紧急通知即时消息。 此消息始终在安全人员的 () 屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员能够使用即时消息或语音快速响应紧急呼叫者。

6. 如果呼叫过早地中断，那么 PSAP 使用 ELIN 直接联系呼叫者。ELIN 网关将 ELIN 交换为呼叫者的 DID。