---
title: Lync Server 2010 的前端常规设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 通过编辑或配置以下属性来编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：
ms.openlocfilehash: c0174d6a0badadc217119b5b2ea1028bc01367278739d5b6b03bb4ae83c0f21d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315758"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的前端常规设置扩展器

通过编辑或配置以下属性来编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：

 **常规**

- **FQDN：** 前端服务器或前端池的完全限定域名。

- **选择"使用所有已配置的 IP 地址**"以使用在前端服务器或前端池上配置的所有地址。

    > [!IMPORTANT]
    > 如果将中介服务器并排在前端服务器或前端池上，则不应选择此选项。 中介服务器和前端服务器需要用于通信的专用 IP 地址。

- 选择 **"将服务用途限制为所选 IP** 地址"，然后输入前端服务器或前端池与部署其余部分通信的主 **IP** 地址的 IP 地址。 键入 **PSTN IP 地址** 与中介服务器关联的 IP 地址。

    **特性和功能**

- **会议**：如果在部署中需要会议功能，则选中此复选框。 会议包括音频、视频、应用程序共享、桌面共享和 Web 会议。 您需要为 Web 会议创建和关联 Office Web Apps Server (稍后在此"属性"页) 。

- 如果选择了会议，则可以选中“电话拨入式(PSTN)会议”。选中此复选框可启用电话拨入式会议功能。

- 如果您打算部署功能 **以使** Lync Server 2013 能够使用 IP 语音 (VoIP) 技术充当电话语音系统，包括根据设计和要求，包括使用中介服务器、PSTN 网关和 IP-PBX 部署话筒电话、SIP 中继或公用电话交换网络连接的选项，请选中此复选框 企业语音。 有关此企业语音的详细信息，请参阅[企业语音](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice)和[Plan for 企业语音 in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **关联**

- **SQL Server存储**：SQL Server (前端服务器或前端池) 命名实例的 FQDN。 从列表选择 SQL Server 存储或通过单击“新建”创建一个新的 SQL Server 存储

- 文件存储：以) 格式选择服务器的 FQDN 和共享 (，该 FQDN 将充当 Lync Server 2013 创建并用于复制、会议目录和其他用途的共享文件的文件存储位置。 `\\<FQDN of server>\<share name>` 从列表选择文件存储或通过单击“新建”创建一个新的文件存储。

- 选中" **关联存档服务器** "复选框可为此前端服务器或前端池启用存档服务器。 选中此复选框后，从列表中选择现有存档服务器或单击"新建"以创建新存档服务器的定义。

- 选中" **关联监控服务器** "复选框可为此前端服务器或前端池启用监控服务器。 选中该复选框后，从列表中选择现有监控服务器或单击"新建"以创建新监控服务器的定义。

- 选中" **将边缘池 (媒体组件关联"** 复选框，为此前端服务器或前端池启用边缘服务器。 选中此复选框后，从列表中选择现有边缘服务器或池，或单击"新建"创建新边缘服务器或池的定义。

  **复原能力**

- 选中" **关联的** 备份注册器池"复选框，从列表中选择将用作备份注册器 ( 的前端服务器或前端池，即当主注册器发生故障时指定为辅助注册器) 

- 如果选择了关联的备份注册器池并选择了备份注册器，则可以选中“语音的自动故障转移和故障回复”复选框。随后便可定义“语音故障转移检测间隔(秒)”和“语音故障回复间隔(秒)”的数字属性。有关详细信息，请参阅[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)

  **Web 服务**

- 若要配置“内部 Web 服务”，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和发布端口。

    > [!IMPORTANT]
    > 内部 Web 服务和定义的侦听和发布的端口用于内部客户端和设备。外部客户端和设备使用外部 Web 服务侦听和发布的端口，以及定义的外部 Web 服务完全限定域名 (FQDN)。

- 若要配置“外部 Web 服务”，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和已发布的端口。

    > [!IMPORTANT]
    > 外部 Web 服务及定义的侦听端口和已发布的端口都用于内部客户端和设备。外部客户端和设备使用外部 Web 服务侦听和已发布端口（通常由反向代理和定义的外部 Web 服务完全限定域名 (FQDN) 一起定义）。外部 Web 服务 FQDN 和简单 URL 的关系定义统一资源定位器 (URL) 地址，外部客户端可以使用该地址访问适用于外部用户和设备的服务。有关简单 URL 的更多详细信息，请参阅[Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls)。

  **中介服务器**

- 若要为 **并** (中介服务器（即前端服务器或前端池) 上部署的中介服务器）配置中介服务器属性，请选择"并排中介服务器已启用 **"。**

- 若要 **为并并** 的中介服务器定义侦听端口，请键入并并的中介服务器正在侦听的 **TLS** 和 **TCP** 端口值。 默认情况下，TLS 定义为 TCP 端口 5067。

- 若要定义中介服务器的 TCP 端口值，请选中" **启用 TCP 端口** "复选框。 默认情况下，中介服务器使用传输层安全性 (TCP 协议) TLS。 TCP 端口仅在“启用 TCP 端口”选项启用的情况下可用。

    > [!NOTE]
    > 这是一个可选设置，您应该参考网关或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

- 定义与并置的中介服务器关联的中继。如果已定义了中继，则可以将它们与中介服务器关联。

    如果多个网关与中介服务器关联，则可以通过选择要设置为默认值的网关并单击"设置为默认值"来 **指定默认网关**。 如果选择删除当前默认网关，请选择该网关并单击“取消设为默认值”。

> [!IMPORTANT]
> 如果对此对话框中的属性进行更改，则必须发布拓扑，并在所有受影响的服务器上Skype for Business Server部署向导。 发布新拓扑后，会提供必须运行 Skype for Business Server 部署向导的受影响服务器列表，作为成功拓扑发布摘要屏幕上的链接。 有关发布更新拓扑的详细信息，请参阅[Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology)。 有关部署向导Skype for Business Server的详细信息，请参阅[Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)。

单击“确定”以保存并将更改应用到拓扑文档。

单击 **"** 取消"将放弃所做的更改并关闭前端服务器或前端池的"编辑属性"。

单击“帮助”以阅读本帮助主题。

## <a name="see-also"></a>另请参阅

[定义和配置前端池](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)