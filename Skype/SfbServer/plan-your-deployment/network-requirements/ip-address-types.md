---
title: 在 Skype for Business 中配置 IP 地址类型
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
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要：在实施 Skype for Business 服务器之前，请查看下面的 IP 地址类型注意事项。
ms.openlocfilehash: 74cb0738c7c6eb0518d8ab4ed4fae7db66921bfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802112"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>在 Skype for Business 中配置 IP 地址类型

**摘要：** 在实施 Skype for Business 服务器之前，请查看下面的 IP 地址类型注意事项。

通过使用拓扑生成器中配置的拓扑设置来部署 IP 地址类型。 本部分介绍了如何在前端服务器、中介服务器和边缘服务器上部署 IP 地址类型。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

使用拓扑生成器，执行以下过程中的步骤以在前端服务器上部署 IP 地址类型。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

1. 在“**Enterprise Edition 前端池**”下，右键单击池中的服务器，然后选择“**编辑属性**”。（也可以选择服务器，然后单击“**操作**”菜单中的“**编辑属性**”。）

2. 在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。 对于双栈配置，请选择 "**启用 IPv4** " 并**启用 IPv6**。

   **前端服务器池的“编辑属性”对话框**

   - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。

     > [!NOTE]
     > 这是针对 IP 版本 6 (IPv6) 配置的建议选项。

   - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“**主 IP 地址**”的值。

   - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。

   - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。

> [!NOTE]
> 在前端服务器上安装支持 PSTN IP 地址配置（或出于任何其他原因）的其他网络接口卡（Nic）不受支持。 有关 Skype for business 服务器支持的 NIC 配置的详细信息，请参阅[Lync server 2013 的服务器硬件平台](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

使用拓扑生成器，执行以下过程中的步骤以在中介服务器上部署 IP 地址类型。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

- 在拓扑生成器中的 "**中介池**" 下，右键单击池中的服务器，然后选择 "**编辑属性**"。 （或者，选择服务器，然后从 "**操作**" 菜单中单击 "**编辑属性**"。）

- 在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。

   **用于中介服务器池的“编辑属性”对话框**

  - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。

    > [!NOTE]
    > 这是针对 IP 版本 6 (IPv6) 配置的建议选项。

  - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入主 IP 地址的值。

  - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。

  - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。
> [!IMPORTANT]
> 我们仅支持*专用*中介服务器上的两个网卡。 如果在前端 collocated 中介 Sserver 角色，则不支持双网卡。 

> [!NOTE]
> - 有关 Skype for business Server 2015 支持的 NIC 配置的详细信息，请参阅 Skype for business [server 2015 的硬件](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - 有关 Skype for business Server 2019 支持的 NIC 配置的详细信息，请参阅 Skype for business [server 2019 的硬件](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>在边缘服务器上部署 IP 地址类型

使用拓扑生成器，请执行以下步骤：

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>在边缘服务器上部署 IP 地址类型

1. 在拓扑生成器中，在 "**边缘池**" 下，右键单击池中的服务器，然后选择 "**编辑属性**"。 （或者，选择服务器，然后从 "**操作**" 菜单中单击 "**编辑属性**"。）

2. 在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。

3. 对于您选择的每个地址类型，必须提供适当的内部和外部地址。
