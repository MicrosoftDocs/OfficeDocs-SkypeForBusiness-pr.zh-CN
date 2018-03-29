---
title: Skype for Business Server 2015 中高级企业语音功能的网络设置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 了解网络区域、网络站点和 IP 子网。 所有这些必须配置为部署计划，对于媒体为企业 2015，Skype 在旁路计划在 Skype 呼叫许可控制业务服务器 2015年），或计划在 Skype 的紧急服务在 Skype 业务服务器 2015年的业务服务器企业语音。
ms.openlocfilehash: eb24dc5098fe71cecc8099c2949039a91e61ebd7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中高级企业语音功能的网络设置
 
了解网络区域、网络站点和 IP 子网。 所有这些必须被配置为部署[业务 2015年的 Skype 在绕过媒体计划](media-bypass.md)，[计划中的业务服务器 2015年的 Skype 通话许可控制](call-admission-control.md)），或者在 Skype 的[紧急业务服务器 2015年的 Skype 服务计划](emergency-services.md)商业服务器企业语音。
  
Skype 业务服务器有三个高级的企业语音特征：[在业务服务器 2015年的 Skype 通话许可控制计划](call-admission-control.md))，[规划中业务服务器 2015年的 Skype 的紧急服务](emergency-services.md)，并在 Skype 的媒体的[计划绕过企业 2015年](media-bypass.md)。 这些功能与网络站点共享网络区域、 网络站点和 Skype 业务服务器拓扑中每个子网的关联的某些配置要求。 
  
本主题概述了共有的所有三种高级企业语音功能的配置要求。
  
## <a name="network-regions"></a>网络区域

网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。
  
> [!NOTE]
> 网络区域并非与 Skype 相同业务服务器拨入会议区域，需要一个或多个 Skype 业务服务器的拨号计划相关联会议拨入访问号码。 拨入会议区域有关的详细信息，请参阅[规划拨入会议](http://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)。 
  
CAC 要求每一个网络地区有关联的业务服务器中心站点，管理区域内的媒体通信 Skype (也就是说，它使决策基于策略的配置后，关于是否实时音频或视频会话可以被建立）。 Skype 业务服务器中心站点的地理位置，但而不是逻辑组的服务器被配置为一个池一套不代表。 
  
若要配置的网络区域，可以用于业务服务器控制面板中，**区域**选项卡上的 Skype**网络配置**节或运行**新建 CsNetworkRegion**或**设置 CsNetworkRegion** Skype 业务服务器命令行管理程序 cmdlet。 有关说明，部署文档中，请参阅[部署网络区域、 站点和子网中为业务 2015 Skype](../../deploy/deploy-enterprise-voice/deploy-network.md)或 Skype 业务服务器管理外壳程序文档的引用。
  
由所有三个高级的企业语音功能共享相同的网络区域定义。 如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。
  
将 Skype 业务服务器中心网站与网络区域相关联，您可以指定中心站点名称，使用 Skype 业务服务器控制面板的**网络配置**部分中或通过运行**新建 CsNetworkRegion**或**一组 CsNetworkRegion** cmdlet。 有关说明，部署文档中，请参阅[部署网络区域、 站点和子网中为业务 2015 Skype](../../deploy/deploy-enterprise-voice/deploy-network.md)或 Skype 业务服务器管理外壳程序文档的引用。
  
## <a name="network-sites"></a>网络站点

网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。
  
> [!NOTE]
> 网络站点仅供高级的企业语音功能。 它们不是相同配置中为业务服务器拓扑结构您 Skype 的分支站点。 
  
若要配置网络站点并将其与网络区域相关联，可以为业务服务器控制面板，使用 Skype 的**网络配置**节或运行 Skype 业务服务器管理外壳程序**新建 CsNetworkSite**或**一组 CsNetworkSite** cmdlet。 有关详细信息，在部署文档，请参阅[创建或修改网络站点](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)或 Skype 业务服务器管理外壳程序文档的引用。
  
## <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。
  
例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。
  
> [!CAUTION]
> 在网络服务器上的配置过程中指定的 IP 子网必须匹配才能正确使用媒体跳过由客户端计算机提供的格式。 Skype 业务客户端接受其本地的 IP 地址，并屏蔽具有相关的子网掩码的 IP 地址。 当确定旁路 ID 与每个客户端时，注册器将比较精确匹配客户端提供的子网对每个网络站点相关联的 IP 子网的列表。 由于这个原因，很重要的子网在网络配置过程中在服务器上输入实际而不是虚拟子网的子网。 （如果您部署调用许可控制，但不是媒体绕过，调用控件正常工作即使配置虚拟子网的许可）例如，如果 Skype 业务客户端的 IP 子网掩码为 255.255.255.0 IP 地址为 172.29.81.57 的计算机上登录，它将请求与子网 172.29.81.0 旁路 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此，很重要的管理员完全由 Skype 提供的业务客户端 （这配有子网在网络配置中，静态或动态主机配置协议 (DHCP) 通过。） 输入的子网 
  
## <a name="associating-subnets-with-network-sites"></a>将子网与网络站点相关联

企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。 这种关联的子网使高级的企业语音功能，可以找到在地理位置上的终结点。 例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。
  
要与网络站点关联的子网，可以为业务服务器控制面板，使用 Skype 的**网络配置**节或可用于 Skype 业务服务器管理外壳程序。 有关说明，请参见部署文档[与网络站点建立子网关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)或 Skype 业务服务器管理外壳程序文档的引用。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 呼叫许可控制业务服务器 2015年计划](call-admission-control.md)
  
[紧急服务 Skype 业务服务器 2015年计划](emergency-services.md)
  
[在业务 2015年的 Skype 的媒体跳过计划](media-bypass.md)

