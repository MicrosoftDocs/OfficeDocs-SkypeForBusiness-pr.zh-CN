---
title: Skype 中的高级企业语音功能 Business server 网络设置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 了解网络区域、网络站点和 IP 子网。 所有这些必须配置为媒体绕过中的业务，规划 Skype 部署规划呼叫允许控制中的 Skype 业务服务器），或计划在 Skype 的紧急服务 Business 中的服务器 Skype 业务 Server 企业语音。
ms.openlocfilehash: 6dad93aa2d5ef235b07f2189329f94d94b1a3d02
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885655"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Skype 中的高级企业语音功能 Business server 网络设置

了解网络区域、网络站点和 IP 子网。 必须配置所有这些业务服务器部署[规划媒体绕过中的业务的 Skype](media-bypass.md)、[规划呼叫允许控制业务服务器 Skype 中](call-admission-control.md)，或在 Skype[规划中的业务服务器 Skype 的紧急服务](emergency-services.md)企业语音。

Skype 业务服务器具有三个高级的企业语音功能：[规划中的业务服务器 Skype 的呼叫允许控制](call-admission-control.md)、[规划紧急服务中的业务服务器 Skype](emergency-services.md)和[规划媒体绕过 Skype for Business 中](media-bypass.md). 这些功能与网络站点共享网络区域、 网络站点和关联中的企业服务器拓扑 Skype 每个子网某些配置的要求。

本主题概述了通用于所有三种高级企业语音功能的配置要求。

## <a name="network-regions"></a>网络区域

网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。

> [!NOTE]
> 网络区域而无法 Skype 相同的业务服务器电话拨入式会议区域，需要将电话拨入式会议访问号码与一个或多个 Skype 对于业务服务器拨号计划相关联。 有关电话拨入式会议区域的详细信息，请参阅[规划电话拨入式会议](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)。

CAC 要求每个网络区域具有关联的 Skype 业务 Server 管理中心网站，其管理的区域中的媒体流量 (即，它使决策基于策略的已配置，关于是否实时音频或视频会话可以建立）。 地理位置，但而逻辑组为池配置的服务器或池的一组并不表示 Business Server 中央站点的 Skype。

若要配置网络区域，可以用于业务 Server Control Panel，**区域**选项卡上的 Skype**网络配置**部分，或运行**New-csnetworkregion**或**Set-csnetworkregion** Skype for BusinessServer 命令行管理程序 cmdlet。 有关说明，请参阅部署文档中的[部署网络区域、 站点和 Skype for Business 中的子网](../../deploy/deploy-enterprise-voice/deploy-network.md)或引用的业务 Server Management Shell 文档 Skype。

共享相同的网络区域定义的所有三个高级企业语音功能。 如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。

将 Business Server 中央站点 Skype 与网络区域相关联，您可以指定中央站点名称，使用的 Skype 业务 Server 控制面板的**网络配置**部分中，或通过运行**New-csnetworkregion**或**Set-csnetworkregion** cmdlet。 有关说明，请参阅部署文档中的[部署网络区域、 站点和 Skype for Business 中的子网](../../deploy/deploy-enterprise-voice/deploy-network.md)或引用的业务 Server Management Shell 文档 Skype。

## <a name="network-sites"></a>网络站点

网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。

> [!NOTE]
> 网络站点仅使用高级企业语音功能。 它们不是您在您 Skype 企业服务器拓扑中配置的分支站点相同。

若要配置网络站点，并将其与网络区域关联，可以对业务服务器控制面板中，使用**网络配置**部分中的 Skype 或业务 Server 命令行管理程序**New-csnetworksite**或**运行 SkypeSet-csnetworksite** cmdlet。 有关详细信息，请参阅部署文档中[创建或修改网络站点](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)或引用的业务 Server Management Shell 文档 Skype。

## <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。

> [!CAUTION]
> 在服务器上的网络配置过程中指定的 IP 子网必须匹配才能正常使用媒体绕过提供客户端计算机的格式。 业务客户端 Skype 采用其本地 IP 地址和关联子网掩码屏蔽的 IP 地址。 当确定绕过 ID 与每个客户端时，注册器将比较 IP 子网与子网为完全匹配提供由客户端的针对每个网络站点相关联的列表。 因此，很重要网络配置过程中输入的服务器上的子网是实际的子网，而不是虚拟子网。 （如果您部署呼叫允许控制，但不是媒体绕过，呼叫允许控制将正常即使您将配置虚拟子网。）例如，如果 Skype 业务客户端登录与 IP 子网掩码 255.255.255.0 172.29.81.57 IP 地址的计算机上时，它将请求与子网 172.29.81.0 相关联的绕过 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此，很重要，管理员输入子网完全由 Skype 提供的用于业务客户端 （其设置子网与网络配置过程中静态或动态主机配置协议 (DHCP) 由。）

## <a name="associating-subnets-with-network-sites"></a>将子网与网络站点相关联

企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。 此关联的子网使地理上找到终结点的高级的企业语音功能。 例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。

将子网与网络站点相关联，可以使用的 Skype**网络配置**部分的业务 Server Control Panel，或可用于 Skype 业务 Server Management Shell。 有关说明，请参阅部署文档中的[子网与网络站点关联](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)或引用的业务 Server Management Shell 文档 Skype。

## <a name="see-also"></a>另请参阅

[规划呼叫允许控制 Skype 中的业务服务器](call-admission-control.md)

[规划业务服务器中 Skype 的紧急服务](emergency-services.md)

[规划媒体绕过 Skype for Business 中](media-bypass.md)

