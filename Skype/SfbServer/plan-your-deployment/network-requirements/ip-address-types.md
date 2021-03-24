---
title: 在 Skype for Business 中配置 IP 地址类型
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：在实施 Skype for Business Server 之前，请查看下面的 IP 地址类型注意事项。
ms.openlocfilehash: ba10dd223e7e099d27e31bddce478603f50e49a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101248"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>在 Skype for Business 中配置 IP 地址类型

**摘要：** 在实施 Skype for Business Server 之前，请查看下面的 IP 地址类型注意事项。

通过使用在拓扑生成器中配置的拓扑设置来部署 IP 地址类型。 本节介绍如何在前端服务器、中介服务器和边缘服务器上部署 IP 地址类型。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

使用拓扑生成器，执行以下过程中的步骤以在前端服务器上部署 IP 地址类型。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

1. 在“Enterprise Edition 前端池”下，右键单击池中的服务器，然后选择“编辑属性”。（也可以选择服务器，然后单击“操作”菜单中的“编辑属性”。）

2. 在“编辑属性”对话框中，选择您要配置的 IP 地址类型。 对于双协议栈配置，请选择"**启用 IPv4"** 和"**启用 IPv6"。**

   **前端服务器池的“编辑属性”对话框**

   - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。

     > [!NOTE]
     > 这是针对 IP 版本 6 (IPv6) 配置的建议选项。

   - **服务仅供选定 IP 地址使用**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“主 IP 地址”的值。

   - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。

   - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。

> [!NOTE]
> 不支持安装其他网络接口 (NIC) 以支持 PSTN IP 地址配置 (或出于任何其他) 原因在前端服务器上安装网络接口卡。 有关 Skype for Business Server 支持的 NIC 配置的详细信息，请参阅[Server hardware platforms for Lync Server 2013。](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

使用拓扑生成器，执行以下过程中的步骤以在中介服务器上部署 IP 地址类型。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

- 在拓扑生成器的"**中介池"下**，右键单击池中的服务器，然后选择"编辑 **属性"。**  (选择服务器，然后从"操作"菜单中单击 **"编辑属性**"。) 

- 在“编辑属性”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“启用 IPv4”和“启用 IPv6”，如下图所示。

   **用于中介服务器池的“编辑属性”对话框**

  - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。

    > [!NOTE]
    > 这是用于 IP 版本 6 (IPv6) 配置的建议选项。

  - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须为主 IP 地址输入值。

  - **主 IP 地址**。输入服务器将用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。输入的 IP 地址必须与选定地址类型的格式匹配。

  - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。
> [!IMPORTANT]
> 我们仅在专用中介服务器上支持 *两个* 网卡。 如果中介 Sserver 角色并位于前端，则不支持双网卡。 

> [!NOTE]
> - 有关 Skype for Business Server 2015 支持的 NIC 配置详细信息，请参阅 [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - 有关 Skype for Business Server 2019 支持的 NIC 配置详细信息，请参阅 [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>在边缘服务器上部署 IP 地址类型

使用拓扑生成器执行以下步骤：

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>在边缘服务器上部署 IP 地址类型

1. 在拓扑生成器的"**边缘池"下**，右键单击池中的服务器，然后选择"编辑 **属性"。**  (选择服务器，然后从"操作"菜单中单击 **"编辑属性**"。) 

2. 在“编辑属性”窗口中，选择要支持的 IP 地址配置。

3. 对于您选择的每个地址类型，必须提供适当的内部和外部地址。