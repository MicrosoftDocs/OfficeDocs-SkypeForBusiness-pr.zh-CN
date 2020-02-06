---
title: Skype for Business Server 中的高级企业语音功能的网络设置
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
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 了解网络区域、网络站点和 IP 子网。 所有这些都必须配置为在 skype for Business 中部署媒体绕过计划，在 skype for business server 中规划呼叫许可控制，或在 Skype for business server 企业版的 Skype for business 服务器中规划紧急服务。
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802592"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Skype for Business Server 中的高级企业语音功能的网络设置

了解网络区域、网络站点和 IP 子网。 所有这些都必须配置为在 skype for [business 中部署媒体旁路计划](media-bypass.md)，在 skype For business [server 中规划呼叫许可控制](call-admission-control.md)，或在 Skype For business Server 企业版的[Skype for business 服务器中规划紧急服务](emergency-services.md)。

Skype for business 服务器具有三个高级的企业语音功能：[在 skype for Business 服务器中规划呼叫许可控制](call-admission-control.md)、在 skype For business [server 中规划紧急服务](emergency-services.md)以及[规划 skype for business 中的媒体旁路](media-bypass.md)。 这些功能与网络站点的 Skype for business 服务器拓扑中的网络区域、网络站点和每个子网的关联有一定的配置要求。

本主题概述了所有这三种高级企业语音功能所共有的配置要求。

## <a name="network-regions"></a>网络区域

网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。

> [!NOTE]
> 网络区域与 Skype for business 服务器电话拨入式会议区域不同，后者是将电话拨入式会议访问号码与一个或多个 Skype for business 服务器拨号计划关联所必需的。 有关电话拨入式会议区域的详细信息，请参阅 [Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)。

CAC 要求每个网络区域都有一个关联的 Skype for Business 服务器中心网站，该网站负责管理区域内的媒体流量（即，它根据已配置的策略做出决策，有关是否有实时音频或可以建立视频会话）。 Skype for Business Server 中心网站不代表地理位置，而是指配置为池或池集的逻辑服务器组。

要配置网络区域，你可以使用 Skype for Business Server 控制面板的 "**网络配置**" 部分中的 "**区域**" 选项卡，或者运行**CsNetworkRegion**或**CsNetworkRegion** Skype for business server Management Shell cmdlet。 有关说明，请参阅部署文档中的 "[在 Skype For business 中部署网络区域、网站和子网](../../deploy/deploy-enterprise-voice/deploy-network.md)" 或参阅 Skype For Business 服务器管理外壳文档。

所有三个高级企业语音功能都共享相同的网络区域定义。 如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。

若要将 Skype for business Server 中央站点与网络区域关联，请指定中心网站名称，方法是使用 Skype for Business Server 控制面板的 "**网络配置**" 部分，或者运行**CsNetworkRegion**或**CsNetworkRegion** cmdlet。 有关说明，请参阅部署文档中的 "[在 Skype For business 中部署网络区域、网站和子网](../../deploy/deploy-enterprise-voice/deploy-network.md)" 或参阅 Skype For Business 服务器管理外壳文档。

## <a name="network-sites"></a>网络站点

网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。

> [!NOTE]
> 网络站点仅由高级企业语音功能使用。 它们与您在 Skype for Business 服务器拓扑中配置的分支站点不同。

若要配置网络网站并将其与网络区域关联，可以使用 Skype for Business Server 控制面板的 "**网络配置**" 部分，或者运行 skype For Business Server Management Shell **CsNetworkSite**或**CsNetworkSite** cmdlet。 有关详细信息，请参阅在部署文档中[创建或修改网络网站](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)，或参阅 Skype For Business 服务器管理外壳文档。

## <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。

> [!CAUTION]
> 在服务器上的网络配置期间指定的 IP 子网必须与客户端计算机提供的格式匹配，才能正确用于媒体绕过。 Skype for Business 客户端使用其本地 IP 地址，并使用关联的子网掩码屏蔽 IP 地址。 确定与每个客户端关联的绕过 ID 时，注册机构会将与每个网络站点相关联的 IP 子网的列表与客户端提供的子网进行比较，以精确匹配。 出于此原因，在服务器上的网络配置期间输入的子网必须是实际的子网，而不是虚拟子网。 （如果您部署了 "呼叫许可控制"，但没有媒体旁路，则即使配置了虚拟子网，呼叫许可控制也能正常运行。）例如，如果 Skype for Business 客户端使用 ip 地址为255.255.255.0 的 ip 地址在计算机上登录，则它将请求与子网172.29.81.0 关联的旁路 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此，管理员应严格按照 Skype for Business 客户端提供的方式输入子网（静态或动态主机配置协议（DHCP）在网络配置期间预配子网）。）

## <a name="associating-subnets-with-network-sites"></a>将子网与网络站点相关联

企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。 此子网关联使高级企业语音功能能够在地理位置找到终结点。 例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。

若要将子网与网络站点关联，可以使用 Skype for Business Server 控制面板的 "**网络配置**" 部分，也可以使用 Skype For Business 服务器命令行管理程序。 有关说明，请参阅在部署文档中[将子网与网络站点关联](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)，或参阅 Skype For Business 服务器管理外壳文档。

## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中规划呼叫许可控制](call-admission-control.md)

[Skype for business Server 中的紧急服务计划](emergency-services.md)

[在 Skype for Business 中规划媒体旁路](media-bypass.md)

