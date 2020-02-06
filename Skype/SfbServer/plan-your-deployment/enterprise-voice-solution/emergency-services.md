---
title: Skype for business Server 中的紧急服务计划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: 了解 Skype for Business Server 企业版中增强的9-1-1 （E9-1）服务，包括位置获取和呼叫路由。
ms.openlocfilehash: f09729bc6fdbd2fa64dee5b30af88494cd618915
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802982"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Skype for business Server 中的紧急服务计划

了解 Skype for Business Server 企业版中增强的9-1-1 （E9-1）服务，包括位置获取和呼叫路由。

Skype for Business 服务器支持美国的增强9-1-1 （E9-1）服务，作为企业语音部署的一部分。 E9-1-1 是一项紧急派发功能，对于来自办公楼和其他多租户设施的呼叫，该功能可将 9-1-1 呼叫与紧急响应位置 (ERL) 相关联，紧急响应位置包含市政（即街道）地址和其他更具体的位置信息，例如楼层号。 通过使用提供的 ERL，公共安全应答点 (PSAP) 可以立即向需要帮助的呼叫者派遣第一批响应者，从而降低因疏忽而将响应者指向不正确或模糊不清的位置的风险。

> [!NOTE]
> Skype for business 服务器现支持客户端的多个紧急号码的配置。 有关详细信息，请参阅[在 Skype For Business 服务器中规划多个紧急号码](multiple-emergency-numbers.md)。

> [!NOTE]
> Skype for Business 服务器具有三个高级的企业语音功能：呼叫许可控制、紧急服务（E9-1）和媒体旁路。 有关所有这三种功能的通用计划信息的概述，请参阅[Skype For Business 服务器中的高级企业语音功能的网络设置](network-settings-for-advanced-features.md)。

Skype for business 服务器支持从 Skype for Business 客户端和 Lync Phone Edition 设备进行增强的9-1-1 （E9-1）调用。 配置 Skype for business Server for E9-1 时，来自 Skype for Business 或 Lync Phone 版的紧急呼叫包括来自位置信息服务数据库的紧急响应位置（ERL）信息。 ERL 包含市政（即街道）地址，以及有助于确定在办公楼和其他多租户设施中的更精确位置的其他信息。 当用户进行紧急呼叫时，Skype for Business 服务器通过中介服务器向 E9 服务提供商路由呼叫音频以及位置和回拨信息。 E9-1-1 服务提供商会使用呼叫者的市政地址，将呼叫路由到为呼叫者所在的位置提供服务的公共安全应答点 (PSAP)，并沿着 PSAP 用来查找呼叫者 ERL 的紧急服务查询键 (ESQK) 进行发送。

Skype for Business 服务器支持将紧急呼叫路由到 E9 服务提供商的两种方法：

- 到合格的 E9-1-1 服务提供商的会话初始协议 (SIP) 中继连接

- 到基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商的紧急位置标识号 (ELIN) 网关

使用 SIP trunk E9 服务提供商时，请将 ERLs 添加到位置信息服务数据库，然后根据 E9 地址指南（MSAG）为-1 服务提供商维护的主要街道地址指南（）验证位置。 如果 E9 服务提供商收到一个没有位置信息的呼叫，或者有一个未通过 MSAG 验证的位置，E9 服务提供商将呼叫路由到国家/地区紧急呼叫回复中心（ECRC），该人员配备有专门培训的人员，他们口头获取呼叫方的位置（如有可能），并手动将呼叫路由到相应的 PSAP。 （某些 SIP 中继 E9 服务提供商还向客户提供 PSTN 直接向内拨号（已有）号码给 ECRC，该号码提供了路由9-1-1 呼叫的备用方法，如果 SIP 干线因任何原因而失败。）

与时间段复用（TDM）和基于 IP 的专用分支 exchange （PBX）手机（具有固定位置）不同，Skype for business 终结点可以很轻松地进行移动。 部署 E9-1 功能时，Skype for Business 服务器有助于确保无论呼叫者身在何处，紧急呼叫都可以路由到服务呼叫者位置的 PSAP。 例如，如果用户的主 office 位于华盛顿州雷德蒙，但用户在威奇托、堪萨斯、SIP 主干或基于 PSTN 的 E9-1 服务提供商将呼叫路由到威奇托中的 PSAP，则会将紧急呼叫放在来自分支机构中的一台计算机上。，而不是雷德蒙中的 PSAP。

使用 ELIN 网关时，还会将 ERLs 添加到位置信息服务数据库，但每个位置还包括一个 ELIN 号码。 ELIN 号码会在紧急呼叫过程中变为紧急呼叫号码。 然后，你必须确保 PSTN 运营商将 ELIN 上载到自动位置标识 (ALI) 数据库。

> [!NOTE]
> Skype for Business-连接的模拟设备无法接收位置信息服务中的位置信息或将位置信息发送到 E9 服务提供商。

 如果使用 SIP 中继 E9-1-1 服务提供商选项并需要通过模拟电话支持 E9-1-1，则有以下两个选项：

- **传统 PS-阿里选项**如果您的每个站点上都有本地 PSTN 网关，并且每个模拟电话都有，则可以直接使用专用交换机/自动位置标识（PS-阿里）服务提供商预配模拟设备的位置。 在这种情况下，你可以配置巧尽心思构建的 Skype for business 语音策略，并将其分配给模拟设备联系人对象，以便从这些电话直接通过本地网关将 E9 路由到服务该站点的 PSTN 提供商（而不是将呼叫路由到 E9 服务提供商 SIP 主干。 发出紧急呼叫后，与 PSTN 中继关联的 PS-ALI 提供商的数据库会将每个模拟电话的 DID 映射到一个物理位置并将此位置提供给 PSAP。 每当将电话移至不同的 ERL 时，必须通过 PS-ALI 服务提供商更新这些记录。

- **E9-1-1 服务提供商选项**如果 E9-1 服务提供商支持，则可以向 E9 服务提供商注册模拟电话 DIDs 及其相应的 ERLs。 如果提供商从不包含 PIDF 数据的 Skype for Business 服务器接收呼叫，则该提供商可以查看呼叫方的已做号码是否存在数据库匹配。 通过使用从其数据库中检索到的 ERL，提供程序可以自动将紧急呼叫路由到正确的 PSAP，PSAP 将收到模拟设备的使用和 ESQK 记录，使 dispatcher 能够查找呼叫者的位置。

如果您使用 ELIN 网关选项并需要通过模拟电话支持 E9-1-1，则可以直接向 PS-ALI 服务提供商提供模拟设备的位置，如上面第一个选项中所述。

从 Skype for Business 服务器角度来看，E9 （1-1）过程可以分为两个阶段：

- 阶段 1：获取位置

- 阶段 2：将紧急呼叫路由至 E9-1-1 服务提供商

本节介绍这些阶段的工作原理。

如果计划将基础结构配置为自动检测客户端位置，则首先需要确定将使用哪些网络元素将呼叫者映射到不同位置。 有关可能的选项的详细信息，请参阅[定义用于确定 Skype For Business 服务器中的位置的网络元素](network-location.md)。

## <a name="acquiring-a-location"></a>获取位置

在 Skype for business Server E9 部署中，每个内部连接的 Skype for business 或 Lync Phone 版客户端都将主动获取其自己的位置。 在 SIP 注册后，客户端 furnishes 在位置信息服务（即由复制的 SQL Server 数据库支持的 web 服务）的位置请求中对其自身知道的所有网络连接信息。 每个中心网站池都有一个位置信息服务，该服务使用网络信息查询匹配位置的记录。 如果存在匹配项，则 Location 信息服务将向客户端返回一个位置。 如果没有匹配项，则可能会提示用户手动输入位置（取决于位置策略设置）。 位置数据将以 Internet 工程任务组 (IETF) 标准化 XML 格式（称为状态信息数据格式位置对象 (PIDF-LO)）传回客户端。

Skype for Business 客户端将 PIDF 数据作为紧急呼叫的一部分包括在内，E9 服务提供商将使用此数据来确定相应的 PSAP，并将该 PSAP 的调用与正确的 ESQK 一起发送，这使 PSAP dispatcher 能够获取呼叫方的位置。

下图显示了 Skype for Business 客户端如何获取位置（除第三方基于客户端 MAC 地址的位置方法除外）：

![客户端获取位置的方式的图示](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

对于获取位置的客户端，必须执行下列步骤：

1. 管理员通过网络 wiremap 填充位置信息服务数据库（将各种类型的网络地址映射到相应的紧急响应位置（ERLs））的表。

2. 如果使用 SIP 中继 E9-1-1 服务提供商，则管理员将针对 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 数据库验证 ERL 的市政地址部分。如果使用 ELIN 网关，则管理员将确保 PSTN 运营商会将 ELIN 上载到自动位置标识 (ALI) 数据库。

3. 在注册期间或网络更改发生时，内部连接的客户端会将包含客户发现的网络地址的位置请求发送到位置信息服务。

4. 位置信息服务查询某个位置的已发布记录，如果找到匹配项，则以 PIDF 格式将 ERL 返回到客户端。

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>使用 SIP 中继路由 E9-1-1 呼叫

使用 SIP 中继连接至限定的 E9-1-1 服务提供商是可用于部署 E9-1-1 的一种方式。有关使用 ELIN 网关连接至基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商的详细信息，请参阅[Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx)。

下图显示了使用 SIP 主干和合格的 E9 服务提供商时，如何将紧急呼叫从 Skype for Business 服务器路由到公共安全应答点（PSAP）。

**通过 SIP 中继路由 E9-1-1 呼叫**

![从 Lync Server 路由到 PSAP 的紧急呼叫](../../media/Plan_LyncServer_E911_CallRouting.jpg)

当紧急呼叫来自兼容的 Skype for Business 服务器客户端时：

1. 包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回呼号码的 SIP 邀请将路由到 Skype for business 服务器。

2. Skype for Business 服务器匹配紧急号码，并将呼叫路由（基于在适用的位置策略中定义的**PSTN 使用**值）到中介服务器，从该服务器到 E9-1 服务提供商的 SIP 主干。

3. E9-1-1 服务提供商根据呼叫提供的位置将紧急呼叫路由至正确的 PSAP。如果客户端随紧急呼叫提供了已验证的紧急响应位置 (ERL)，则提供商会自动将呼叫路由至相应的 PSAP。如果位置是由用户手动输入的，则在将紧急呼叫路由至 PSAP 之前，紧急呼叫响应中心 (ECRC) 将首先口头与呼叫者核实位置的准确性。

4. 如果为通知配置了位置策略，则会向一个或多个组织的安全专员发送特殊的 Skype for Business 紧急通知即时消息。 此消息始终弹出在安全主管的屏幕上，并且包含呼叫者的姓名、电话号码、时间和地点，使安全人员能够使用即时消息或语音快速响应紧急呼叫方。

5. 如果您配置了用于会议的位置策略并且 E9-1-1 服务提供商支持该策略，则国际安全服务台会通过单向音频或双向音频作为与会者加入呼叫。

6. 如果过早中断呼叫，则 PSAP 使用回拨号码直接与呼叫者联系。

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>使用 ELIN 网关路由 E9-1-1 呼叫

统一通信开放互操作性计划中的某些合作伙伴提供了合格的支持紧急位置标识号 (ELIN) 的网关，该网关可充当合格 E9-1-1 服务提供商的 SIP 中继连接的备选项。 ELIN 网关支持 ISDN 或与基于公用电话交换网 (PSTN) 的 E9-1-1 服务的集中式自动通话记帐 (CAMA) 连接。 有关提供 ELIN 网关和其文档链接的合作伙伴的详细信息，请参阅适用于 Skype for business 的 Microsoft Lync 和[电话基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)[合格的基础结构](https://go.microsoft.com/fwlink/p/?LinkId=248425)。

与 E9-1-1 服务提供商的 SIP 中继连接相似，ELIN 网关还提供了将紧急呼叫路由到呼叫者的最合适的公共安全应答点 (PSAP) 的方法，但这些网关将 ELIN 用作位置标识符。 为组织中的每个紧急响应位置（ERL）定义 ELINs （有关详细信息，请参阅[管理 Skype for Business 服务器中 ELIN 网关的位置](elin-gateways.md)）。

当您使用 ELIN 网关拨打紧急电话时，您使用的是用于 SIP 中继连接的同一 Skype for Business 服务器 E9-1。 也就是说，位置信息服务数据库提供 Skype for Business 客户端的位置，并且位置策略启用该功能并定义路由。 但是，使用 ELIN 网关时，你需要将 ELINs 添加到位置信息服务数据库，并让 PSTN 运营商将其上传到自动位置识别（阿里）数据库。

当 Skype for Business 客户端从位置信息服务获取其位置时，位置包含 ELIN。 在紧急呼叫期间，ELIN 将包含在发送到 ELIN 网关的位置中。 ELIN 网关会将此呼叫标识为紧急呼叫并将呼叫者的号码与 ELIN 交换。 ELIN 网关随后会将呼叫路由到带有作为主叫号码的 ELIN 的 PSTN。 PSTN E9-1-1 提供商将在 ALI 数据库中查找 ELIN，该数据库是主街道地址指南 (MSAG) 数据库的附带数据库。 PSTN 随后会根据 ALI 查找将呼叫发送到最合适的 PSAP，而 PSAP 会根据 ALI 查找将第一个响应者发送到呼叫者的位置。 主叫号码将在 ELIN 网关上缓存一段预定时间以供回拨。 在回拨期间，PSAP 将到达 ELIN 网关，后者会将 ELIN 与呼叫者的直拨分机 (DID) 号码交换。

ELIN 网关仅支持来自您组织的网络中的紧急呼叫。它们不支持从您的网络外发出的紧急呼叫。

> [!NOTE]
> 有关将 SIP 中继连接用于紧急呼叫的详细信息，请参阅[Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx)。

下图显示了使用 ELIN 网关时，如何将紧急呼叫从 Skype for Business 服务器路由到 PSAP。

**使用 ELIN 网关路由 E9-1-1 呼叫**

![显示紧急服务呼叫如何经由中介服务器，随后传输到紧急服务提供商。在此之后，可以选择通过 IM 发送给现场安全部门和/或回拨原始呼叫方。](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. 包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回呼号码的 SIP 邀请将路由到 Skype for business 服务器。

2. Skype for Business 服务器匹配紧急号码，然后将呼叫路由（基于在适用位置策略中定义的**PSTN 使用**值）到中介服务器，以及从此处到 ELIN 网关。

3. ELIN 网关通过 ISDN 或 CAMA 中继将呼叫路由到 PSTN。

4. PSTN 将呼叫标识为紧急呼叫并将其路由到网路中的 E9-1-1 选择性路由器。E9-1-1 选择性路由器在 ALI 数据库中查找呼叫者的号码以获取地理位置。E9-1-1 选择性路由器根据从 ALI 数据库中检索到的位置信息将呼叫发送到最合适的 PSAP。 

5. 如果为通知配置了位置策略，则会向一个或多个组织的安全专员发送特殊的 Skype for Business 紧急通知即时消息。 此消息始终弹出在安全主管的屏幕上，并且包含呼叫者的姓名、电话号码、时间和地点，使安全人员能够使用即时消息或语音快速响应紧急呼叫方。

6. 如果呼叫被永久性中断，PSAP 将使用 ELIN 直接联系呼叫者。ELIN 网关会将 ELIN 与呼叫者的 DID 交换。


