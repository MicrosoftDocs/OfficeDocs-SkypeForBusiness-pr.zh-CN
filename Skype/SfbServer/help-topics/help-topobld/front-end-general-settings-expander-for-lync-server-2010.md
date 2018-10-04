---
title: Lync Server 2010 的前端常规设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 您可以通过编辑或配置以下属性编辑前端服务器或前端池的属性。 配置页可分为以下几节：
ms.openlocfilehash: 3af82a83afe27ce06a3c41f881154c2850cad521
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374200"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的前端常规设置扩展器

您可以通过编辑或配置以下属性编辑前端服务器或前端池的属性。 配置页可分为以下几节：

 **常规**

- **FQDN**： 前端服务器或前端池的完全限定的域名。

- 选择**使用所有已配置的 IP 地址**，以使使用的所有前端服务器或前端池上配置的地址。

    > [!IMPORTANT]
    > 如果您将并置中介服务器上的前端服务器或前端池，不应选择此选项。 中介服务器和前端服务器需要对其进行通信的专用的 IP 地址。

- 选择**服务使用率限制为所选的 IP 地址**，并输入**主 IP 地址**进行部署的其余部分与前端服务器或前端池通信的 IP 地址。 在**PSTN IP 地址**中键入与中介服务器相关联的 IP 地址。

    **特性和功能**

- **会议**： 如果您希望部署中的会议功能，请选择复选框。 会议包括音频、 视频、 应用程序共享、 桌面共享和 Web 会议。 您将需要创建并将关联的 Office Web Apps Server 的 Web 会议 （以后在此属性页中定义）。

- 如果选择会议，可以选择**拨入式 (PSTN) 会议**。 选中该复选框以启用电话拨入式会议功能。

- 如果您打算部署功能，可以启用 Lync Server 2013 以用作 IP (电话 VoIP) 技术，包括部署话筒电话的选项通过使用语音电话语音系统，SIP 中继或公共，选中此复选框**企业语音**交换的电话网络连接使用中介服务器、 PSTN 网关和 IP-PBX 组合或单独，基于的设计和要求。 企业语音的详细信息，请参阅[企业语音](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)和[规划中的业务服务器 2015 Skype 的企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **关联**

- **SQL Server 存储**： 与前端服务器或前端池关联的 SQL Server （和可选的命名的实例） 的 FQDN。 从列表中选择 SQL Server 存储或通过单击**新建**创建新的 SQL Server 存储

- **文件存储**： 选择 FQDN 的服务器和共享 (格式`\\<FQDN of server>\<share name>`) 的将充当 Lync Server 2013 创建和使用复制、 会议目录和其他目的的共享文件的文件存储位置。 从列表中选择的文件存储或通过单击**新建**创建新文件存储。

- 选择**关联存档服务器**复选框以启用此前端服务器或前端池的存档服务器。 选择复选框后, 从列表中选择现有的存档服务器，或单击**新建**创建新的存档服务器的定义。

- 选择**关联监控服务器**复选框以启用此前端服务器或前端池的监控服务器。 选择复选框后, 从列表中选择现有的监控服务器，或单击**新建**创建新的监控服务器的定义。

- 选择**关联边缘池 (用于媒体组件**复选框以启用此前端服务器或前端池的边缘服务器。 选择复选框后, 从列表中选择一个现有边缘服务器或池，或单击**新建**创建新的边缘服务器或池的定义。

  **复原**

- 选择**关联备份注册器池**复选框，以从列表中选择一个将备份注册器的前端服务器或前端池 (即，指定为辅助注册器前端服务器或前端池的主失败）

- 如果您选择关联备份注册器池，并且选择了备份注册器，您可以用于**自动故障转移和故障回复语音**选中复选框。 现在，您可以定义数字属性**语音故障转移检测内部 （秒）** 和**语音故障回复间隔 （秒）**。 有关详细信息，请参阅[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Web 服务**

- 若要配置**内部 web 服务**，您定义的**HTTP**和**HTTPS****侦听端口**。 默认情况下，这些 TCP 端口 80 和 TCP 端口 443，分别是。 您还可以用于**HTTP**和**HTTPS**配置**已发布端口**。 默认情况下，这些 TCP 端口 80 和 TCP 端口 443，分别是。 根据您的内部 web 服务配置和使用的负载平衡器 （硬件负载平衡器和 DNS 负载平衡），调整要定义侦听的端口值和已发布的端口。

    > [!IMPORTANT]
    > 内部 web 服务定义侦听和已发布的端口供内部客户端和设备。 外部客户端和设备使用侦听的外部 web 服务发布端口，以及定义的外部 web 服务完全限定的域名 (FQDN)。

- 若要配置**外部 web 服务**，您定义的**HTTP**和**HTTPS****侦听端口**。 默认情况下，这些 TCP 端口 80 和 TCP 端口 443，分别是。 您还可以用于**HTTP**和**HTTPS**配置**已发布端口**。 默认情况下，这些 TCP 端口 80 和 TCP 端口 443，分别是。 根据您的内部 web 服务配置和使用的负载平衡器 （硬件负载平衡器和 DNS 负载平衡），调整要定义侦听的端口值和已发布的端口。

    > [!IMPORTANT]
    > 外部 web 服务定义侦听和已发布的端口供外部客户端和设备。 外部客户端和设备使用侦听的外部 web 服务和发布端口，通常由反向代理以及定义的外部 web 服务完全限定的域名 (FQDN)。 外部 web 服务 FQDN 的关系和简单 Url 定义外部客户端将用于访问的外部用户和设备的可用服务的统一资源定位器 (URL) 地址。 简单 Url 的详细信息，请参阅[Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。

  **中介服务器**

- 若要配置**中介服务器**属性并置的中介服务器 （即，在前端服务器或前端池上部署中介服务器），选择**并置中介服务器已启用**。

- 要定义并置的中介服务器**侦听端口**，请键入并置的中介服务器侦听的**TLS**和**TCP**端口值。 默认情况下，TLS 被定义为 TCP 端口 5067。

- 要定义为中介服务器的 TCP 端口值，请选择**启用 TCP 端口**复选框。 默认情况下，中介服务器通过 TCP 协议中使用传输层安全性 (TLS)。 仅当启用时启用 TCP 端口所选内容，TCP 端口是可用。

    > [!NOTE]
    > 这是一个可选的设置，并且您应该网关或 PSTN 的要求，以确定是否需要此引用。 默认情况下，TCP 端口值为 5068。

- 定义与并置的中介服务器关联的中继。 如果已经定义中继，则可以将它们与中介服务器关联。

    如果您有多个网关与中介服务器相关联，您可以通过选择您希望默认情况下，该网关并单击**设为默认值**来指定默认网关。 如果您选择要删除当前的默认网关，则选择网关，然后单击**Unmake 默认**。

> [!IMPORTANT]
> 如果更改此对话中的属性，您必须发布拓扑并受影响的所有服务器上运行 Business Server 部署向导 Skype。 发布新拓扑后的受影响的服务器必须运行 Business Server 部署向导的 Skype 列表会为您提供为成功拓扑发布摘要屏幕上的链接。 发布更新的拓扑的详细信息，请参阅[Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)。 有关业务 Server 部署向导的 Skype 的详细信息，请参阅[Lync Server Administrative Tools](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。

单击**确定**以保存并将更改应用到拓扑文档。

单击**取消**以放弃更改并关闭**编辑属性**的前端服务器或前端池。

单击**帮助**以阅读本帮助主题。

## <a name="see-also"></a>另请参阅

[定义和配置前端池或 Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)