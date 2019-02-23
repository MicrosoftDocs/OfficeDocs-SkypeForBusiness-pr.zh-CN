---
title: 规划 Office 365 中的电话系统与内部部署 PSTN 连接中 Skype 业务 Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 了解 Office 365 (云 PBX) 中的电话系统的规划注意事项的内部部署 PSTN 连接。
ms.openlocfilehash: 234c2966cb887c0adfdd15f518479ad5e363fe73
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210627"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>规划 Office 365 中的电话系统与内部部署 PSTN 连接中 Skype 业务 Server

了解 Office 365 (云 PBX) 中的电话系统的规划注意事项的内部部署 PSTN 连接。

如果您已有 Skype 业务服务器或本地 Lync Server 2013 部署，此内容是相关。 有关其他方案，请参阅[规划 Office 365 (云 PBX) 解决方案中电话系统](plan-your-phone-system-cloud-pbx-solution.md)。

 通过内部部署 PSTN 连接的 Office 365 中的电话系统可以利用您的用户的电话系统 (云 PBX) 功能。 这在以下情况下可能很有帮助：

- 您有一些您 Skype 的业务用户驻留在本地和其他人驻留在 Skype 业务 online。 您现在可以在 Office 365 功能中启用电话系统和功能为您的用户位于 Skype 业务 online，但继续使用内部部署 PSTN 连接。

- 具有本地部署并且您希望为业务 Online 到 Skype 移动部分或所有用户，但继续使用内部部署 PSTN 连接。

    > [!IMPORTANT]
    > 若要成功为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接，其 SIP 地址必须是您自己的域。 不支持对 Office 365 使用默认域 onmicrosoft.com。 

若要详细了解包括许可和计划的 Office 365 中的电话系统，请参阅[PSTN 呼叫 for Business 的 Skype 的计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比较

云与本地 PSTN 连接的 PBX 不提供相同的功能集为完全内部部署企业语音解决方案。 若要帮助您确定是否具有内部部署 PSTN 连接的云 PBX 将提供右功能设置为您的组织，请参阅[下面是与云 PBX 获取的内容](https://go.microsoft.com/fwlink/?LinkId=715517)。

## <a name="benefits-and-planning-considerations"></a>好处和规划注意事项

> [!CAUTION]
> 在迁移到 Skype for Business Online 之前，必须更新 Lync Phone Edition 设备以符合最低的必要固件要求。
如果在更新固件之前将用户从本地环境迁移到联机环境，用户将无法使用其电话进行连接。 要更正此问题，必须将用户移回到本地环境以将其电话固件更新为最低要求的固件。 请勿在将用户移回到本地环境之前尝试更新到最低要求的固件或对电话执行硬重置。
如果在设备未安装最低要求的固件时执行了硬重置，设备将默认为使用 PIN 身份验证，而 Skype for Business Online 不支持这种验证方式。 有关详细信息，请参阅[业务 online Skype 的入门电话](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

通过部署 Office 365 中的电话系统与内部部署 PSTN 连接，可以移动用户到云通过 Skype 业务 online 在自己的速度，同时保留其内部部署 PSTN 连接。 如果你有 PBX，则可以继续使用它为迁移到云的用户提供 PSTN 连接。 一旦业务 Online 和 Office 365 中的电话系统的情况下，用户移至 Skype，其旧式 PBX 电话将不再起作用，但其电话号码将路由到任何 Skype 业务客户端电脑或智能手机以及 Skype 的符合业务的桌面电话s。 一旦移植，在 Office 365 用户和旧版 PBX 用户的电话系统可以调用每个其他通常以及使/接收使用其普通电话号码的 PSTN 呼叫。

你可以有自定义功能或主要传统 PBX 加载项，如呼叫中心。 如果不在 Office 365 中的电话系统上当前可用的自定义功能，您应将保留这些要求的自定义功能在本地与旧版 PBX 和只端口不需要访问到 Office 365 中的电话系统的自定义功能的用户的用户通过内部部署 PSTN 连接。

直接与 Skype 的业务服务器 2015年旧 Pbx 的互操作的列表，请参阅[Microsoft lync 基础结构限定](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)。 如果 PBX 不在此列表中，您可以使用会话边界控制器业务 online 与 Skype 中的 Office 365 中的电话系统连接 PBX。

### <a name="network-considerations-for-quality-and-performance"></a>质量和性能相关的网络注意事项

当使用内部部署 PSTN 连接部署与 Office 365 中的电话系统类似云承载的服务，您必须记住以下。 在业务 Server 2015 企业语音部署完全内部 Skype，所有的基础结构和客户端位于企业的网络上。 此网络的质量和性能（对于高质量音频和视频至关重要）直接受企业员工控制。 与通过内部部署 PSTN 连接的 Office 365 中的电话系统，有所涉及的三个网络，两种客户负责为但唯一一种企业人员具有直接控制通过：

- **Microsoft 的全局媒体传递网络**Microsoft 的全局云网络和基础结构。 Office 365 和 Office 365 服务器和通信中的电话系统遍历此网络。

- **企业/云 PSTN 互连**这是连接到 Office 365 云企业的网络。 这不一定是通用 Internet 连接相同。

- **企业的网络**实时媒体质量非常依赖于自己的网络： 尤其是 WiFi 网络和用于访问 Office 365 云互连质量。

> [!NOTE]
> 对业务 online Skype 中优化性能的详细信息，请参阅[业务联机性能调整 Skype](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Office 365 中的电话系统使用内部部署 PSTN 连接的先决条件

您可以配置电话系统 Office 365 中与内部部署 PSTN 连接和用户移动到 Skype 业务 online 之前，您必须确认您在具有以下先决条件：

 **本地服务器版本。** 在本地部署中的服务器的版本必须支持在 Office 365 中的电话系统与内部部署 PSTN 连接下表中列出。


| **服务器角色**                                       | **受支持的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 联合身份验证边缘\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 下一跳联盟路由内部池服务器  <br/> | Skype for Business Server 2015，2016 年 3 月累积更新 6.0.9319.235 或更高版本（前端或控制器）   <br/> |
| 前端用户服务器  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| 边缘服务器  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 中介服务器  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*最小的受支持的版本是：

- Skype for Business Server 2015，2016 年 3 月累积更新 6.0.9319.235

- Lync Server 2013，2015 年 7 月累积更新 5.0.8308.920

\*\*联盟路由的所有受支持的 SIP 域必须穿业务 Server 2015 边缘服务器正在运行 Skype 2016 或更高版本年 3 月累积更新。 如果用户池在 Lync Server 2013 中，该外部池流量将保留在 Lync Server 2013 Edge Server 中。 

此外，您必须会确保以下：

- **内部部署企业语音是配置和测试内部部署用户**这包括 PSTN 连接组件。 详细信息，请参阅以下主题，如果您使用的业务服务器 2015 Skype，请参阅[中的业务服务器 2015 Skype 的企业语音规划](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)和[部署中的业务服务器 2015 Skype 的企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。

    如果您使用 Lync Server 2013，请参阅[Lync Server 2013 中的企业语音规划](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx)和[部署 Lync Server 2013 中的企业语音](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)。

- **Active Directory 同步**您必须配置 Active Directory 同步使用 Azure AD 连接。 有关详细信息，请参阅[管理 Azure AD 连接](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)。

    > [!NOTE]
    > 您所使用的 AAD Connect 版本必须是版本 1.0.9125.0 或更高版本。如果您使用较早版本的 AAD Connect 工具或 DirSync，请升级到支持的版本。您可以升级您的当前安装并维护您在环境中定义的任何自定义规则。 

- **配置混合部署**是否所有业务用户您 Skype 目前驻留之一联机或本地，或如果当前有组合，在[部署混合中所述，必须完成业务服务器或 Lync Server 2013 配置混合部署的 Skype 的步骤Skype 业务 server 和 Office 365 之间的连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。 在混合部署的更多背景信息，请参阅[Plan Business Server 和 Office 365 的 Skype 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 

    如果您使用 Lync Server 2013，请参阅[Lync Server 2013 hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)。

- **Active Directory 联合身份验证服务 (AD FS) （推荐）** 我们建议部署 AD FS 以支持单一登录。 有关详细信息，请参阅[Active Directory 联合身份验证服务 (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)。

有关部署 Office 365 中的电话系统的信息，请参阅[启用通过内部部署中的业务服务器 Skype 的 PSTN 连接的 Office 365 中的电话系统的用户](enable-users-for-phone-system.md)。


