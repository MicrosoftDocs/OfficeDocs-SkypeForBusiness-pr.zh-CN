---
title: Skype for Business Server 中高级企业语音功能的网络Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 了解网络区域、网络站点和 IP 子网。 必须将所有这些配置为在 Skype for Business 中部署媒体旁路计划、在 Skype for Business Server) 中规划呼叫允许控制或规划 Skype for Business Server 中的紧急Skype for Business Server 企业语音。
ms.openlocfilehash: fd81c9084ca94e7b0884d1c496c153fd964bcf89
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762110"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Skype for Business Server 中高级企业语音功能的网络Skype for Business Server

了解网络区域、网络站点和 IP 子网。 必须将所有这些配置为在[Skype for Business](media-bypass.md)中部署规划媒体旁路、在[Skype for Business Server](call-admission-control.md)中规划呼叫允许控制或规划 Skype for Business Server 中的紧急[](emergency-services.md)服务Skype for Business Server 企业语音。

Skype for Business Server三个高级企业语音功能：Plan for call [admission control in Skype for Business Server、Plan](call-admission-control.md) [for emergency services in Skype for Business Server](emergency-services.md)和 Plan for media [bypass inSkype for Business](media-bypass.md)。 这些功能共享网络区域、网络站点以及网络拓扑中每个子网与Skype for Business Server关联的某些配置要求。

本主题概述了这三种高级配置功能企业语音要求。

## <a name="network-regions"></a>网络区域

网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。

> [!NOTE]
> 网络区域与电话Skype for Business Server区域不同，拨入式会议区域需要将电话拨入式会议访问号码与一个或多个 Skype for Business Server 拨号计划关联。 有关电话拨入式会议区域的详细信息，请参阅 [规划电话拨入式会议](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements)。

CAC 要求每个网络区域都有一个关联的 Skype for Business Server 中央站点，该站点管理区域 (内的媒体流量，也就是说，它根据已配置的策略做出有关是否可以建立) 实时音频或视频会话的策略。 Skype for Business Server中央站点并不表示地理位置，而是表示配置为池或一组池的服务器的逻辑组。

若要配置网络区域，可以使用 Skype for Business Server 控制面板的"网络配置"部分上的"区域"选项卡，或者运行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion** Skype for Business Server 命令行管理程序 cmdlet。 有关说明，请参阅部署文档中的 Deploy [network regions， sites and subnets in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in Skype for Business Server Management Shell documentation。

这三个高级网络区域定义由所有三个高级企业语音共享。 如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。

若要将 Skype for Business Server 中央站点与网络区域关联，可以使用 Skype for Business Server 控制面板的"网络配置"部分或运行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion** cmdlet 来指定中央站点名称。 有关说明，请参阅部署文档中的 Deploy [network regions， sites and subnets in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in Skype for Business Server Management Shell documentation。

## <a name="network-sites"></a>网络站点

网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。

> [!NOTE]
> 网络站点仅由高级网络企业语音使用。 它们与在拓扑拓扑中配置的分支站点Skype for Business Server相同。

若要配置网络站点并将其与网络区域关联，可以使用 Skype for Business Server 控制面板的"网络配置"部分，或运行 Skype for Business Server 命令行管理程序 **New-CsNetworkSite** 或 **Set-CsNetworkSite** cmdlet。 有关详细信息，请参阅部署[文档中的创建](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)或修改网络站点，或参阅命令行Skype for Business Server命令行管理程序文档。

## <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。

> [!CAUTION]
> 在服务器上进行网络配置期间指定的 IP 子网必须与客户端计算机提供的格式相匹配，才能正确用于媒体旁路。 客户端Skype for Business其本地 IP 地址，并屏蔽具有关联子网掩码的 IP 地址。 在确定与每个客户端关联的绕过 ID 时，注册器将比较与每个网络站点关联的 IP 子网列表与客户端提供的子网进行精确匹配。 因此，在服务器上进行网络配置期间输入的子网是实际子网而不是虚拟子网，这一点很重要。  (如果部署呼叫允许控制，但不部署媒体旁路 ) ， 即使配置了虚拟子网，呼叫允许控制也会正常工作。例如，如果 Skype for Business 客户端在 IP 地址为 172.29.81.57 的计算机上登录，IP 子网掩码为 255.255.255.0，它将请求与子网 172.29.81.0 关联的绕过 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此，管理员必须完全按照 Skype for Business 客户端提供的子网输入子网 (这些客户端在网络配置期间静态或由动态主机配置协议 (DHCP) .) 

## <a name="associating-subnets-with-network-sites"></a>将子网与网络站点相关联

企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。 通过子网关联，高级企业语音功能可以在地理位置上定位终结点。 例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。

若要将子网与网络站点关联，可以使用"控制面板"Skype for Business Server"网络配置"部分，或使用命令行管理程序Skype for Business Server命令行管理程序。  有关说明，请参阅部署文档中的[Associate a Subnet with a Network Site，](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)或参考 Skype for Business Server Management Shell 文档。

## <a name="see-also"></a>另请参阅

[规划呼叫允许控制Skype for Business Server](call-admission-control.md)

[规划紧急服务Skype for Business Server](emergency-services.md)

[规划媒体旁路Skype for Business](media-bypass.md)