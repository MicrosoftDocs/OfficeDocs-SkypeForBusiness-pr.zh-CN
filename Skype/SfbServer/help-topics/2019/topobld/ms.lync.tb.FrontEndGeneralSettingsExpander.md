---
title: 前端常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
ROBOTS: NOINDEX, NOFOLLOW
description: 要编辑现有前端池或 Standard Edition Server 的设置，可参考以下各节内容：
ms.openlocfilehash: 76992a6d88c25a1907e4bb2cc1f6dee69a418f01
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688507"
---
# <a name="front-end-general-settings-expander"></a>前端常规设置扩展器

要编辑现有前端池或 Standard Edition Server 的设置，可参考以下各节内容：

- 常规设置

- 复原设置

- Web 服务设置

- 中介服务器设置

## <a name="front-end-pool"></a>前端池

对于前端池，可以配置常规设置、复原设置、Web 服务设置和中介服务器设置。有关详细信息，请参阅以下子节中的信息。有关定义和配置前端池设置的详细信息，请参阅[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。

### <a name="general-settings"></a>常规设置

可以配置以下常规设置：

- **FQDN**。编辑要更改的池的 FQDN。

- **启用硬件负载平衡器监控端口**。选中该复选框并输入您的硬件负载平衡器将用于监控池服务器状态的端口号。

- 在“**功能**”中，定义该池将并置的其他角色。可以配置以下设置：

  - **会议**。包含音频、视频和应用程序共享。选择此选项后，您可以选择电话拨入式 (PSTN) 会议。可以在本节后面的“中介服务器设置”子节下指定并定义公用电话交换网 (PSTN) 网关。

  - **企业语音**。 对合格的手机和设备以及 Skype for business 客户端启用通过 IP 拨出的内部语音通话。 若要启用外部呼叫功能，需要包含中介服务器。 有关详细信息，请参阅本主题后面的“中介服务器”。

- 在“**关联**”中，编辑或指定以下内容：

  - **SQL 存储**。修改现有 SQL Server 服务器或新建基于 SQL Server 的数据库以保存前端池数据库。可以从列表中选择新的 SQL Server 实例或通过单击“**新建**”创建新的条目。

    选择“**启用 SQL Server 存储镜像**”，然后选择要用于镜像的服务器。单击“**新建**”可创建新的 SQL Server 存储。

    选择“**使用 SQL Server 镜像见证启用自动故障转移**”以选择将某台服务器用作镜像见证。单击“**新建**”可创建新的 SQL Server 存储。

  - **文件共享**。修改前端池正在使用的文件存储。通过从列表中选择，可以从已定义的文件存储中选择新的文件存储。单击“**新建**”可创建新的文件存储。

    > [!IMPORTANT]
    > 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。

  - **存档**。将存档服务器存储与前端池关联。通过从列表中选择服务器，可以从已定义的存档 SQL Server 存储中进行选择，或单击“**新建**”以指定新的存档服务器。

    > [!IMPORTANT]
    > 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。

    选择“**启用 SQL Server 存储镜像**”，然后选择要用于镜像的服务器。单击“**新建**”可创建新的 SQL Server 存储。

    选择“**使用 SQL Server 镜像见证启用自动故障转移**”以选择将某台服务器用作镜像见证。单击“**新建**”可创建新的 SQL Server 存储。

  - **监视（CDR 和 QoE 度量）**。选择此选项将监控 SQL Server 存储与前端池关联。通过从列表中选择服务器，可以从已定义的监控服务器中进行选择，或单击“**新建**”以指定新的监控服务器。

    选择“**启用 SQL Server 存储镜像**”，然后选择要用于镜像的服务器。单击“**新建**”可创建新的 SQL Server 存储。

    选择“**使用 SQL Server 镜像见证启用自动故障转移**”以选择将某台服务器用作镜像见证。单击“**新建**”可创建新的 SQL Server 存储。

  - **关联边缘池（用于媒体组件）**。将边缘服务器或池与前端池关联。通过从列表中选择服务器，可以从已定义的边缘服务器或池中进行选择，或单击“**新建**”以指定新的边缘服务器或池。

  - **将池与一个 Office Web Apps 服务器关联**。选择此选项可将 Office Web Apps 服务器与前端池关联。从列表中选择现有服务器，或单击“**新建**”以创建新的 Office Web Apps 服务器。

### <a name="resiliency"></a>复原

复原为池提供灾难恢复和高可用性。它提供了备份，如果主服务器发生故障，备份服务器可以接管发生故障的服务器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统上的主服务器发生故障。

从列表中选择充当池的备份服务器的前端池或 Standard Edition Server。还可以选择启用故障转移和回退时间间隔。启用故障转移和回退时间设置（以秒为单位指定）后，可自动检测发生故障的服务器，回退时间用于自动确定主服务器是否已备份。

> [!IMPORTANT]
> 定义故障检测和回退间隔时，应注意不要输入在服务器短时间内未做出响应的情况下会导致发生故障转移和回退的间隔。主服务器可能会在短时间内没有响应，这取决于池或服务器的加载状况。对于池到池或池到 Standard Edition Server，故障转移和回退的默认值是 300 秒和 600 秒。对于站点中的 Survivable Branch Appliance 或 Survivable Branch Server 到池或到 Standard Edition Server，故障转移的默认值是 120 秒，回退的默认值是 240 秒。

> [!CAUTION]
> “**故障转移间隔**”的最小值不应该设置为低于 90 秒的值。如果将此值设置为低于 90 秒的值，将使用 90 秒。Intercluster Ping 时间为 30 秒，设置为低于 90 秒的值将导致主服务器和备份服务器循环开关机，进而因服务器尝试解析其他服务器的正常状态，会对生产产生不适当的影响。小于 90 秒的值将不足以确定主服务器是否可用。

### <a name="web-services"></a>Web 服务

要为前端池上的 Web 服务编辑或指定其他设置，请在“**内部 Web 服务**”和“**外部 Web 服务**”中修改或指定设置。

对于“**内部 Web 服务**”，请指定以下内容：

> [!CAUTION]
> 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为**pool01.contoso.com**，则不能将**Pool01.contoso.com**用于其他前端池或前端服务器。 如果你还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果你决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。

- 如果选择“**覆盖 FQDN**”，则可以为池上的“**内部 Web 服务**”标识指定不同的 FQDN。默认情况下，该设置是为前端池定义的当前池名称。

- 部署所需的 HTTP 和 HTTPS 侦听端口和已发布端口。端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认设置是最常见的设置，通常不需要更改，除非在您的组织和基础结构设计中有具体的要求。

对于“**外部 Web 服务**”，请指定以下内容：

- 外部 Web 服务的 FQDN。此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。

- 部署所需的 HTTP 和 HTTPS 侦听端口和已发布端口。 最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。 根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。 已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。 这些值确定了该池将侦听哪些端口的传入请求。 通常情况下，不需要更改这些项，除非对池的端口要求有冲突。 建议使用相同端口值的内部和外部已发布端口。 这不会出现冲突。

### <a name="mediation-server"></a>中介服务器

对于“**中介服务器**”，请指定以下内容：

- 如果要将中介服务器并置到该池上，请选中“**并置中介服务器已启用**”复选框。如果选择不并置中介服务器，则本节中没有可用的设置。

- 如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

- 与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。

- 如果有多个中继与中介服务器关联，可以通过选择相应中继，然后单击“**设为默认值**”，指定默认中继。若要取消选择中继作为默认中继，请单击“**取消设为默认值**”。

有关定义和配置前端池设置的详细信息，请参阅[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。

## <a name="standard-edition-server"></a>Standard Edition Server

对于 Standard Edition Server，可以配置常规设置、复原设置、Web 服务设置和中介服务器设置。有关详细信息，请参阅以下子节中的信息。有关定义和配置 Standard Edition Server 设置的详细信息，请参阅[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。

### <a name="general-settings"></a>常规设置

可以配置以下常规设置：

- **FQDN**。 请注意，无法更改 FQDN。 必须删除并重新定义 Standard Edition Server 才能更改与其关联的 FQDN。

- 选择“**使用所有已配置的 IP 地址**”或“**将服务用途限制为所选 IP 地址**”。如果选择将服务用途限制为定义的 IP 地址，则需要定义服务器用于除 PSTN 外的所有通信的主 IP 地址。需要定义单独的 IP 地址用于 PSTN。也可以选择“**启用 IPv6**”为此服务器启用 IPv6。

- **启用硬件负载平衡器监控端口**。选中该复选框并输入您的硬件负载平衡器将用于监控服务器状态的端口号。

- 在“**功能**”中，定义要与该服务器并置的其他角色。可以配置以下设置：

  - **会议**。包含音频、视频和应用程序共享。选择此选项后，您可以选择“**电话拨入式 (PSTN) 会议**”。稍后可以在中介服务器设置下指定并定义 PSTN 网关。

  - **企业语音**。 对合格的手机和设备以及 Skype for business 客户端启用通过 IP 拨出的内部语音通话。 若要启用外部呼叫功能，需要包含中介服务器。 有关详细信息，请参阅本主题后面的“中介服务器”。

- 在“**关联**”中，可以编辑或指定以下内容：

  - 选择“**SQL Server 存储**”将 SQL Server 存储与前端服务器关联。也可以启用镜像并选择镜像见证服务器。

  - **文件共享**。修改 Standard Edition Server 正在使用的文件存储。通过从列表中选择，可以从已定义的文件存储中选择新的文件存储。单击“**新建**”可创建新的文件存储。

    > [!IMPORTANT]
    > 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。

  - **存档**。将存档 SQL Server 存储与 Standard Edition Server 关联。通过从列表中选择服务器，可以从已定义的存档存储中进行选择，或单击“**新建**”以指定新的存档存储。

    > [!IMPORTANT]
    > 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。

  - **监视（CDR 和 QoE 度量）**。将监控 SQL Server 存储与 Standard Edition Server 关联。通过从列表中选择服务器，可以从已定义的监控服务器中进行选择，或单击“**新建**”以指定新的监控服务器。

  - **将池与一个 Office Web Apps 服务器关联**。选择此选项可将 Office Web Apps 服务器与前端池关联。从列表中选择现有服务器，或单击“**新建**”以创建新的 Office Web Apps 服务器。

  - **关联边缘池**。将边缘服务器或池与 Standard Edition Server 进行关联。通过从列表中选择服务器，可以从已定义的边缘服务器或池中进行选择，或单击“**新建**”以指定新的边缘服务器或池。

### <a name="resiliency"></a>复原

复原为服务器提供灾难恢复和高可用性。它提供了备份，如果主服务器发生故障，备份服务器可以接管发生故障的服务器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统发生故障。

从列表中选择充当备份服务器的前端池或 Standard Edition Server。还可以选择启用故障转移和回退时间间隔。启用故障转移和回退时间设置（以秒为单位指定）后，可自动检测发生故障的注册器，回退时间用于自动确定主注册器是否已备份。

> [!IMPORTANT]
> 定义故障检测和回退间隔时，应注意不要输入在服务器短时间内未做出响应的情况下会导致发生故障转移和回退的间隔。主服务器可能会在短时间内没有响应，这取决于池或服务器的加载状况。对于池到池或池到 Standard Edition Server，故障转移和回退的默认值是 300 秒和 600 秒。对于站点中的 Survivable Branch Appliance 或 Survivable Branch Server 到池或到 Standard Edition Server，故障转移的默认值是 120 秒，回退的默认值是 240 秒。

### <a name="web-services"></a>Web 服务

要为服务器上的 Web 服务编辑或指定其他设置，请在“**内部 Web 服务**”和“**外部 Web 服务**”中修改或指定设置。

对于“**内部 Web 服务**”，可以指定以下内容：

- 如果选择“覆盖 FQDN”，则可以为服务器上的内部 Web 服务标识指定不同的 FQDN。默认情况下，该设置是为 Standard Edition Server 定义的当前服务器名称。

- 部署所需的 HTTP 和 HTTPS 侦听端口和已发布端口。端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认设置是最常见的设置，通常不需要更改，除非在您的组织和基础结构设计中有具体的要求。

对于“**外部 Web 服务**”，可以指定以下内容：

- 外部 Web 服务的 FQDN。此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。

- 部署所需的 HTTP 和 HTTPS 侦听端口。最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。这些值确定了该服务器将侦听哪些端口的传入请求。通常，这些值不需要更改，除非服务器上的端口要求有冲突。

### <a name="mediation-server"></a>中介服务器

对于“**中介服务器**”，可以指定以下内容：

- 如果要将中介服务器与该服务器并置，请选中“**并置中介服务器已启用**”复选框。如果选择不并置中介服务器，则本节中没有可用的设置。

- 如果已启用中介服务器并置，请在服务器上为 TLS 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义 TCP 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

- 与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。

- 如果有多个网关与中介服务器关联，可以通过选择相应网关，然后单击“**设为默认值**”，指定默认网关。若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。

有关定义和配置 Standard Edition Server 设置的详细信息，请参阅[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。


