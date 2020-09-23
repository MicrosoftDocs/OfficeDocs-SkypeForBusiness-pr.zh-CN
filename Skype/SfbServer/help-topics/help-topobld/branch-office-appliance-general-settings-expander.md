---
title: 分支机构设备常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 要编辑现有 Survivable Branch Appliance 或 Survivable Branch Server 的设置，可参考以下各节内容：
ms.openlocfilehash: 40ebf4a22bcfc3392c2f1dc8238a46b610d22281
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216123"
---
# <a name="branch-office-appliance-general-settings-expander"></a>分支机构设备常规设置扩展器

要编辑现有 Survivable Branch Appliance 或 Survivable Branch Server 的设置，可参考以下各节内容：

- 常规设置

- 恢复能力设置

- 中介服务器设置



对于 Survivable Branch Appliance 或 Survivable Branch Server，可参考以下内容：

## <a name="general-settings"></a>常规设置

Survivable Branch Appliance 或 Survivable Branch Server 的完全限定域名 (FQDN)。编辑服务器的 FQDN 以更改该值。必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。

您可以选择“使用所有已配置的 IP 地址”**** 或“将服务用途限制为所选 IP 地址”****。如果选择“将服务用途限制为所选 IP 地址”****，则需要定义服务器用于除公用电话交换网 (PSTN) 网关外的所有通信的主 IP 地址。需要定义单独的 IP 地址用于 PSTN。

在“关联”**** 中，可以编辑或指定以下内容：

- 通过关联存档服务器，您可以选择将存档服务器与 Survivable 分支设备或 Survivable 分支服务器相关联。 您可以从已定义的存档服务器中进行选择，方法是从下拉列表中选择服务器，或单击 " **新建** " 以指定新的存档服务器。

    > [!IMPORTANT]
    > 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。

- 通过关联监控服务器，可以选择将监视服务器与 Survivable 分支设备或 Survivable 分支服务器相关联。 您可以从已定义的监视服务器中进行选择，方法是从下拉列表中选择服务器，或单击 " **新建** " 以指定新的监视服务器。

- 使用 "关联边缘池"，您可以选择将边缘服务器或池与 Survivable 分支设备或 Survivable 分支服务器相关联。 通过从下拉列表中选择服务器，可以从已定义的边缘服务器或池中进行选择，或单击 **“新建”** 以指定新的边缘服务器或池。

## <a name="resiliency"></a>功能

复原为注册器池提供了高可用性。它提供了备份注册器，如果主注册器发生故障，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。

从下拉列表中，选择将充当 Survivable 分支机构或 Survivable 分支服务器的备份注册器的企业版前端池或 Standard Edition 前端服务器。 还可以选择启用故障转移和回退时间间隔。 启用故障转移和回退时间设置（以秒为单位指定）后，可自动检测发生故障的注册器，回退时间用于自动确定主注册器是否已备份以及是否可以接管注册器进程。

> [!IMPORTANT]
> 定义故障检测和回退间隔时，应注意不要输入在注册器短时间内未做出响应的情况下会导致发生故障转移和回退的间隔。 主注册器可能会在短时间内没有响应，这取决于池或服务器的加载状况。 Survivable 分支装置或站点中的 Survivable 分支服务器到池或 Standard Edition 前端服务器的默认值为故障转移的120秒，回退为240秒。

## <a name="mediation-server"></a>中介服务器

对于 **“中介服务器”**，可以指定以下内容：

由于中介服务器已并置，因此 Survivable Branch Appliance 或 Survivable Branch Server 中的 **“启用并置中介服务器”** 复选框不可用。

在池服务器上为传输层安全性 (TLS) 定义侦听端口。默认情况下，此端口为 5067。如果选择 **“启用 TCP 端口”**，则必须为并置的中介服务器定义 TCP 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。

定义与并置的中介服务器关联的 PSTN 网关。如果已定义网关，则可以将这些网关与中介服务器关联。如果尚未定义任何网关，但可以进行定义，则选择 **“新建”**。还可以删除已为此中介服务器配置的网关。选择相应的网关，然后单击 **“删除”**。

如果有多个网关与中介服务器关联，会将第一个关联的网关作为默认网关。如果必须选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击 **“设为默认值”**。

## <a name="see-also"></a>另请参阅

有关定义和配置 Survivable Branch Appliance 或 Survivable Branch Server 设置的详细信息，请参阅[分支站点恢复能力解决方案](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)。


