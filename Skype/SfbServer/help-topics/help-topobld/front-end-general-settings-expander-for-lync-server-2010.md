---
title: 适合于 Lync Server 2010 的前端常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 可通过编辑或配置以下属性来编辑前端服务器或前端池的属性。 配置页面分为以下部分：
ms.openlocfilehash: 1e7fa730745c3eab20288b5b4bfbb9c0d781be83
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697287"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的前端常规设置扩展器

可通过编辑或配置以下属性来编辑前端服务器或前端池的属性。 配置页面分为以下部分：

 **常规**

- **FQDN**：前端服务器或前端池的完全限定的域名。

- 选择 "**使用所有配置的 IP 地址**"，以使用前端服务器或前端池上配置的所有地址。

    > [!IMPORTANT]
    > 如果在前端服务器或前端池上 collocate 中介服务器，则不应选择此选项。 中介服务器和前端服务器需要专用 IP 地址才能进行通信。

- 选择 "**将服务使用限制为所选 IP 地址**"，然后输入与部署的其余部分的前端服务器或前端池通信的**主 IP 地址**的 IP 地址。 键入**PSTN ip 地址**与中介服务器相关联的 ip 地址。

    **功能和功能**

- **会议**：如果你希望在你的部署中提供会议功能，请选中该复选框。 会议包括音频、视频、应用程序共享、桌面共享和网络会议。 你将需要为 Web 会议创建和关联 Office Web Apps 服务器（稍后在此属性页中定义）。

- 如果您选择了 "会议"，则可以选择 **"拨入（PSTN）会议**"。 选中复选框以启用电话拨入式会议功能。

- 如果想要部署功能，请选择 "**企业语音**"，以启用 Lync server 2013 作为使用 ip 语音（VoIP）技术的电话语音系统，包括基于 "设计" 和 "要求" 组合或单独部署手持电话、SIP 中继或公共交换电话网络连接的选项。 有关企业语音的详细信息，请参阅[Skype for Business Server 2015 中的](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)[企业语音](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)和企业语音计划

    **关联**

- **Sql server 应用商店**：与前端服务器或前端池相关联的 sql server （和命名实例）的 FQDN。 从列表中选择 SQL Server 应用商店，或者通过单击 "**新建**" 来创建新的 sql server 应用商店

- **文件存储**：选择将充当 Lync server 2013 为复制、会议目录和其他用途`\\<FQDN of server>\<share name>`创建和使用的共享文件的文件存储位置的服务器和共享（采用的格式）的 FQDN。 从列表中选择文件存储，或单击 "**新建**" 以创建新的文件存储。

- 选中 "**关联存档服务器**" 复选框以启用此前端服务器或前端池的存档服务器。 选中复选框后，从列表中选择现有存档服务器，或单击 "**新建**" 以创建新存档服务器的定义。

- 选中 "**关联监视服务器**" 复选框以启用此前端服务器或前端池的监视服务器。 选中复选框后，从列表中选择现有监视服务器，或单击 "**新建**" 以创建新的监视服务器的定义。

- 选择 "**关联边缘池" （对于 "媒体组件**" 复选框），为此前端服务器或前端池启用边缘服务器。 选中复选框后，从列表中选择现有的边缘服务器或池，或单击 "**新建**" 以创建新的边缘服务器或池的定义。

  **复原**

- 选中 "**关联的备份注册机构池**" 复选框，从列表中选择将用作备份注册注册机构的前端服务器或前端池（即，在主服务器出现故障的情况下，作为辅助注册机构的前端服务器或前端池）

- 如果已选择 "关联的备份注册机构"，并且选择了 "备份注册机构"，则可以选择用于**自动故障切换和语音回复的**复选框。 现在，你可以为**语音故障回复检测内部（sec）** 和**语音回切间隔（sec）** 定义数字属性。 有关详细信息，请参阅[规划企业语音复原](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Web 服务**

- 若要配置**内部 web 服务**，请定义**HTTP**和**HTTPS**的**侦听端口**。 默认情况下，这些端口分别是 TCP 端口80和 TCP 端口443。 您还可以为**HTTP**和**HTTPS**配置**已发布的端口**。 默认情况下，这些端口分别是 TCP 端口80和 TCP 端口443。 根据内部 web 服务配置和使用负载平衡器（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和已发布的端口。

    > [!IMPORTANT]
    > 内部 web 服务和定义的侦听和已发布端口适用于内部客户端和设备。 外部客户端和设备使用外部 web 服务侦听和已发布端口，以及已定义的外部 web 服务完全限定的域名（FQDN）。

- 若要配置**外部 web 服务**，请定义**HTTP**和**HTTPS**的**侦听端口**。 默认情况下，这些端口分别是 TCP 端口80和 TCP 端口443。 您还可以为**HTTP**和**HTTPS**配置**已发布的端口**。 默认情况下，这些端口分别是 TCP 端口80和 TCP 端口443。 根据内部 web 服务配置和使用负载平衡器（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和已发布的端口。

    > [!IMPORTANT]
    > 外部 web 服务和定义的侦听和已发布端口适用于外部客户端和设备。 外部客户端和设备使用外部 web 服务侦听和已发布端口，通常由反向代理定义，以及已定义的外部 web 服务完全限定的域名（FQDN）。 外部 web 服务 FQDN 和简单 Url 的关系定义了外部客户端将用于访问可用于外部用户和设备的服务的统一资源定位器（URL）地址。 有关简单 Url 的详细信息，请参阅[规划简单 url](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。

  **中介服务器**

- 若要为 collocated 中介服务器（即在前端服务器或前端池上部署的中介服务器）配置**中介服务器**属性，请选择 "**启用中介服务器" collocated**。

- 若要定义 collocated 中介服务器的**侦听端口**，请键入 Collocated 中介服务器正在侦听的**TLS**和**TCP**端口值。 默认情况下，TLS 定义为 TCP 端口5067。

- 若要定义中介服务器的 TCP 端口值，请选中 "**启用 TCP 端口**" 复选框。 默认情况下，中介服务器通过 TCP 协议使用传输层安全性（TLS）。 仅当启用 "启用 TCP 端口" 选择时，TCP 端口才可用。

    > [!NOTE]
    > 这是可选设置，你应该参考网关或 PSTN 的要求以确定是否需要此功能。 默认情况下，TCP 端口值为 5068。

- 定义与 collocated 中介服务器关联的中继。 如果已经定义中继，则可以将它们与中介服务器关联。

    如果您有多个与中介服务器关联的网关，则可以通过选择要设置为默认网关的网关来指定默认网关，然后单击 "**设为默认**值"。 如果你选择删除当前默认网关，请选择网关，然后单击 " **Unmake 默认**网关"。

> [!IMPORTANT]
> 如果在此对话框中对属性进行了更改，则必须在所有受影响的服务器上发布拓扑并运行 Skype for Business 服务器部署向导。 发布新拓扑后，在 "成功拓扑发布摘要" 屏幕上，将为你提供受影响服务器的列表，其中必须运行 "Skype for Business 服务器部署向导"。 有关发布已更新拓扑的详细信息，请参阅[发布拓扑](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)。 有关 Skype for Business 服务器部署向导的详细信息，请参阅[Lync Server 管理工具](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。

单击 **"确定"** 保存并提交对拓扑文档所做的更改。

单击 "**取消**" 放弃所做的更改并关闭前端服务器或前端池的 "**编辑属性**"。

单击 "**帮助**" 以阅读本帮助主题。

## <a name="see-also"></a>另请参阅

[定义和配置前端池或标准版服务器](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
