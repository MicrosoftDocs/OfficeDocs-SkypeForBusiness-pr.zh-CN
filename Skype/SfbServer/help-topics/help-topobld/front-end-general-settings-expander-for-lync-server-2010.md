---
title: Lync Server 2010 的前端常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 可以通过编辑或配置以下属性来编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：
ms.openlocfilehash: 6d7cdb9067ff88b383077538e38c39c2f8e86a5a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219093"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的前端常规设置扩展器

可以通过编辑或配置以下属性来编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：

 **常规**

- **FQDN**：前端服务器或前端池的完全限定域名。

- 选择 " **使用所有已配置的 IP 地址** " 使用在前端服务器或前端池上配置的所有地址。

    > [!IMPORTANT]
    > 如果您在前端服务器或前端池上并置中介服务器，则不应选择此选项。 中介服务器和前端服务器需要专用 IP 地址来进行通信。

- 选择 " **将服务使用情况限制为所选 IP 地址** "，并输入与部署的其余部分的前端服务器或前端池通信的 **主 IP** 地址的 ip 地址。 键入 **PSTN ip 地址** 与中介服务器关联的 ip 地址。

    **特性和功能**

- **会议**：如果在部署中需要会议功能，则选中此复选框。 会议包括音频、视频、应用程序共享、桌面共享和 Web 会议。 您需要创建并将 Office Web Apps Server 用于 Web 会议 (稍后将在此属性页) 中定义。

- 如果选择了会议，则可以选中“电话拨入式(PSTN)会议”****。 选中此复选框可启用电话拨入式会议功能。

- 如果打算部署功能以启用 Lync Server 2013 作为电话语音系统（使用基于 IP 的语音 (VoIP) 技术），请选择 " **企业语音** " 复选框，包括使用中介服务器、PSTN 网关和 ip-pbx （基于设计和要求）组合或单独部署手持电话、SIP 中继或公共交换电话网络连接的选项。 有关企业语音的详细信息，请参阅[Skype For Business Server 2015 中的](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)[企业语音](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)和规划企业语音

    **群体**

- **Sql server 存储**： sql SERVER 的 FQDN (和（可选）与前端服务器或前端池关联的命名实例) 。 从列表选择 SQL Server 存储或通过单击“新建”**** 创建一个新的 SQL Server 存储

- **文件存储**：在 "格式") 中选择 "服务器" 和 "共享" (的 FQDN，  `\\<FQDN of server>\<share name>` 该格式将充当 Lync server 2013 为复制、会议目录和其他目的创建和使用的共享文件的文件存储位置。 从列表选择文件存储或通过单击“新建”**** 创建一个新的文件存储。

- 选中 " **关联存档服务器** " 复选框为此前端服务器或前端池启用存档服务器。 选中此复选框后，可从列表中选择现有存档服务器，或单击 " **新建** " 以创建新存档服务器的定义。

- 选中 " **关联监视服务器** " 复选框为此前端服务器或前端池启用监视服务器。 选中此复选框后，从列表中选择一个现有的监视服务器，或单击 " **新建** " 创建新的监视服务器的定义。

- 选中 " **关联媒体组件的边缘池 (** " 复选框，为此前端服务器或前端池启用边缘服务器。 选中此复选框后，可从列表中选择现有的边缘服务器或池，或单击 " **新建** " 以创建新的边缘服务器或池的定义。

  **功能**

- 选中 " **关联的备份注册器池** " 复选框，以从列表中选择将作为备份注册器的前端服务器或前端池 ( 也就是说，在主服务器出现故障的情况下，将前端服务器或前端池指定为辅助注册器) 

- 如果选择了关联的备份注册器池并选择了备份注册器，则可以选中“语音的自动故障转移和故障回复”**** 复选框。 随后便可定义“语音故障转移检测间隔(秒)”**** 和“语音故障回复间隔(秒)”**** 的数字属性。 有关详细信息，请参阅[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Web 服务**

- 若要配置“内部 Web 服务”****，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”****。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”****。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和发布端口。

    > [!IMPORTANT]
    > 内部 Web 服务和定义的侦听和发布的端口用于内部客户端和设备。外部客户端和设备使用外部 Web 服务侦听和发布的端口，以及定义的外部 Web 服务完全限定域名 (FQDN)。

- 若要配置“外部 Web 服务”****，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”****。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”****。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和已发布的端口。

    > [!IMPORTANT]
    > 外部 Web 服务及定义的侦听端口和已发布的端口都用于内部客户端和设备。 外部客户端和设备使用外部 Web 服务侦听和已发布端口（通常由反向代理和定义的外部 Web 服务完全限定域名 (FQDN) 一起定义）。 外部 Web 服务 FQDN 和简单 URL 的关系定义统一资源定位器 (URL) 地址，外部客户端可以使用该地址访问适用于外部用户和设备的服务。 有关简单 URL 的更多详细信息，请参阅[Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。

  **中介服务器**

- 若要配置并置中介服务器的 **中介服务器** 属性 (也就是说，在前端服务器或前端池上部署的中介服务器) ，请选择 " **并置中介服务器已启用**"。

- 若要定义并置中介服务器的 **侦听端口** ，请键入并置中介服务器正在侦听的 **TLS** 和 **TCP** 端口值。 默认情况下，TLS 定义为 TCP 端口 5067。

- 若要为中介服务器定义 TCP 端口值，请选中 " **启用 TCP 端口** " 复选框。 默认情况下，中介服务器使用传输层安全性 (TLS) 通过 TCP 协议。 TCP 端口仅在“启用 TCP 端口”选项启用的情况下可用。

    > [!NOTE]
    > 这是一个可选设置，您应该参考网关或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

- 定义与并置的中介服务器关联的中继。如果已定义了中继，则可以将它们与中介服务器关联。

    如果您有多个与中介服务器关联的网关，则可以通过选择要设置为默认网关的网关，然后单击 " **设为默认**值" 来指定默认网关。 如果选择删除当前默认网关，请选择该网关并单击“取消设为默认值”****。

> [!IMPORTANT]
> 如果您在此对话框中对属性进行了更改，则必须在所有受影响的服务器上发布拓扑并运行 Skype for Business Server 部署向导。 发布新拓扑后，必须运行 Skype for Business Server 部署向导的受影响服务器的列表，作为 "成功拓扑发布摘要" 屏幕上的链接。 有关发布更新拓扑的详细信息，请参阅[Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)。 有关 Skype for Business Server 部署向导的详细信息，请参阅 [Lync Server 管理工具](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。

单击“确定”**** 以保存并将更改应用到拓扑文档。

单击 " **取消** " 以放弃更改并关闭前端服务器或前端池的 " **编辑属性** "。

单击“帮助”**** 以阅读本帮助主题。

## <a name="see-also"></a>另请参阅

[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
