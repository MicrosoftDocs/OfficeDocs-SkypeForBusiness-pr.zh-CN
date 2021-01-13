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
description: 通过编辑或配置以下属性编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：
ms.openlocfilehash: 8616d65a73f1fb618a72ab41bc628527aa6e2a59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818392"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的前端常规设置扩展器

通过编辑或配置以下属性编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：

 **常规**

- **FQDN**：前端服务器或前端池的完全限定域名。

- **选择"使用所有已配置的 IP 地址**"，以使用在前端服务器或前端池上配置的所有地址。

    > [!IMPORTANT]
    > 如果将中介服务器并排在前端服务器或前端池上，则不应选择此选项。 中介服务器和前端服务器需要要通信的专用 IP 地址。

- 选择 **"将服务用途限制为** 所选 IP 地址"，并输入前端服务器或前端池与部署其余部分通信的主 **IP** 地址的 IP 地址。 键入 **PSTN IP 地址** 与中介服务器关联的 IP 地址。

    **特性和功能**

- **会议**：如果在部署中需要会议功能，则选中此复选框。 会议包括音频、视频、应用程序共享、桌面共享和 Web 会议。 您需要为 Web 会议创建和关联 Office Web Apps Server (稍后在此"属性"页中定义) 。

- 如果选择了会议，则可以选中“电话拨入式(PSTN)会议”。 选中此复选框可启用电话拨入式会议功能。

- 如果要部署使Lync Server 2013 能够使用 IP 语音 (VoIP) 技术充当电话语音系统的功能，包括根据设计和要求，选择部署话筒电话、SIP 中继或使用中介服务器、PSTN 网关和 IP-PBX 的公共电话交换网络连接的选项，请选中复选框 企业语音。 有关此企业语音的详细信息，请参阅[企业语音](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)Skype for Business [Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)中的 企业语音 和计划

    **关联**

- **SQL Server存储**：SQL Server (前端服务器或前端池) 命名实例的 FQDN。 从列表选择 SQL Server 存储或通过单击“新建”创建一个新的 SQL Server 存储

- 文件存储：选择服务器的 FQDN 和共享 (，格式为) ，它将充当 Lync Server 2013 创建并用于复制、会议目录和其他用途的共享文件的文件存储位置。 `\\<FQDN of server>\<share name>` 从列表选择文件存储或通过单击“新建”创建一个新的文件存储。

- 选中" **关联存档服务器** "复选框可为此前端服务器或前端池启用存档服务器。 选中该复选框后，从列表中选择现有存档服务器，或单击"新建"为新的存档服务器创建定义。

- 选中" **关联监控服务器** "复选框可为此前端服务器或前端池启用监控服务器。 选中该复选框后，从列表中选择现有监控服务器，或单击"新建"为新的监控服务器创建定义。

- 选中" **将边缘池 (媒体组件关联"** 复选框，为此前端服务器或前端池启用边缘服务器。 选中该复选框后，从列表中选择现有边缘服务器或池，或单击"新建"为新的边缘服务器或池创建定义。

  **复原能力**

- 选中 **"** 关联的备份注册器池"复选框，从列表中选择一个前端服务器或前端池，该池将成为备份注册器 (，即当主注册器发生故障时指定为辅助注册器前端) 

- 如果选择了关联的备份注册器池并选择了备份注册器，则可以选中“语音的自动故障转移和故障回复”复选框。 随后便可定义“语音故障转移检测间隔(秒)”和“语音故障回复间隔(秒)”的数字属性。 有关详细信息，请参阅[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Web 服务**

- 若要配置“内部 Web 服务”，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和发布端口。

    > [!IMPORTANT]
    > 内部 Web 服务和定义的侦听和发布的端口用于内部客户端和设备。外部客户端和设备使用外部 Web 服务侦听和发布的端口，以及定义的外部 Web 服务完全限定域名 (FQDN)。

- 若要配置“外部 Web 服务”，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和已发布的端口。

    > [!IMPORTANT]
    > 外部 Web 服务及定义的侦听端口和已发布的端口都用于内部客户端和设备。 外部客户端和设备使用外部 Web 服务侦听和已发布端口（通常由反向代理和定义的外部 Web 服务完全限定域名 (FQDN) 一起定义）。 外部 Web 服务 FQDN 和简单 URL 的关系定义统一资源定位器 (URL) 地址，外部客户端可以使用该地址访问适用于外部用户和设备的服务。 有关简单 URL 的更多详细信息，请参阅[Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。

  **中介服务器**

- 若要为 **并** 排的中介服务器 (（即部署在前端服务器或前端池) 上的中介服务器）配置中介服务器属性，请选择"启用并排中介服务器 **"。**

- 若要 **为并并** 的中介服务器定义侦听端口，请键入并并的中介服务器正在侦听的 **TLS** 和 **TCP** 端口值。 默认情况下，TLS 定义为 TCP 端口 5067。

- 若要为中介服务器定义 TCP 端口值，请选中" **启用 TCP 端口** "复选框。 默认情况下，中介服务器使用传输层安全性 (TCP 协议) 传输层安全性。 TCP 端口仅在“启用 TCP 端口”选项启用的情况下可用。

    > [!NOTE]
    > 这是一个可选设置，您应该参考网关或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

- 定义与并置的中介服务器关联的中继。如果已定义了中继，则可以将它们与中介服务器关联。

    如果您具有多个与中介服务器关联的网关，则可以通过选择要设置为默认值的网关并单击"设置为默认值"来指定默认 **网关**。 如果选择删除当前默认网关，请选择该网关并单击“取消设为默认值”。

> [!IMPORTANT]
> 如果对此对话框中的属性进行更改，则必须发布拓扑，并在所有受影响的服务器上运行 Skype for Business Server 部署向导。 发布新拓扑后，会提供必须运行 Skype for Business Server 部署向导的受影响服务器列表，作为成功拓扑发布摘要屏幕上的链接。 有关发布更新拓扑的详细信息，请参阅[Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)。 有关 Skype for Business Server 部署向导的详细信息，请参阅 [Lync Server 管理工具](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。

单击“确定”以保存并将更改应用到拓扑文档。

单击 **"** 取消"将放弃所做的更改并关闭前端服务器或前端池的"编辑属性"。

单击“帮助”以阅读本帮助主题。

## <a name="see-also"></a>另请参阅

[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
