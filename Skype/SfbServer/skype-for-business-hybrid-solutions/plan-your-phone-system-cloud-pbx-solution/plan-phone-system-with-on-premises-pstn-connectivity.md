---
title: Skype for Business Server 中本地 PSTN 连接的计划电话系统
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 了解使用本地 PSTN 连接电话系统 (云 PBX) 规划注意事项。
ms.openlocfilehash: efaba8aae1175db526d9607e2eb8c7e382dbaf1f95ec948a0c34758a055d5c1e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339868"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server 中本地 PSTN 连接的计划电话系统

> [!Important]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持通过 Skype for Business Server 或云连接器版本与 Skype for Business Online 本地环境之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

了解使用本地 PSTN 连接电话系统 (云 PBX) 规划注意事项。

如果您已经在本地部署了 Skype for Business Server Lync Server 2013，则此内容是相关的。 有关其他方案，请参阅 [Microsoft 电话解决方案](/microsoftteams/cloud-voice-landing-page)。

 电话系统本地 PSTN 连接，可以利用电话系统 (云 PBX) 功能。 这有助于处理以下方案：

- 你拥有一些本地Skype for Business用户，另一些用户则位于 Skype for Business Online 中。 现在可以为 电话系统 Online 中的用户启用本地 PSTN Skype for Business功能，但继续使用本地 PSTN 连接。

- 你拥有本地部署，并且希望将部分或所有用户移动到 Skype for Business Online，但继续使用本地 PSTN 连接。

    > [!IMPORTANT]
    > 若要为用户电话系统本地 PSTN 连接，其 SIP 地址必须位于您自己的域中。 不支持将默认域用于Microsoft 365或Office 365，onmicrosoft.com 默认域。 

若要详细了解电话系统，包括许可和计划，请参阅[pstN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比较

具有本地 PSTN 连接的云 PBX 不提供与完全本地部署部署解决方案相同的企业语音集。 为了帮助你确定具有本地 PSTN 连接的云 PBX 是否将为组织提供正确的功能集，请参阅以下是使用云 [PBX 获取的功能](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)。

## <a name="benefits-and-planning-considerations"></a>优点和规划注意事项

> [!CAUTION]
> Lync 电话 Edition 设备必须更新为本地环境中所需的最低固件，才能迁移到 Skype for Business Online。
如果在更新固件之前将用户从本地移动到联机，用户将无法使用其电话进行连接。 若要更正此问题，必须将用户移回本地环境，以便其电话更新到最低固件。 在将用户移回本地环境之前，不要尝试更新到最低固件或硬重置电话。
如果在设备不是最低固件时执行硬重置，它将默认使用 PIN 身份验证，Skype for Business Online 中不支持。 有关详细信息，请参阅获取适用于 Skype for Business [Online 的电话](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

通过电话系统本地 PSTN 连接来部署本地 PSTN 连接，你可以按自己的节奏通过 Skype for Business Online 将用户移动到云，同时保留其本地 PSTN 连接。 如果你有 PBX，可以继续使用它为移动到云的用户提供 PSTN 连接。 将用户移至 Skype for Business Online 和 电话系统 后，其旧版 PBX 电话将不再工作，但他们的电话号码将路由到任何适用于电脑或智能手机的 Skype for Business 客户端，以及符合 Skype for Business 标准的桌面电话。 移植后，电话系统和旧版 PBX 用户可以正常相互呼叫，以及使用其正常电话号码拨打/接听 PSTN 呼叫。

你可以将自定义功能或主要加载项添加到旧版 PBX，如呼叫中心。 如果自定义功能当前在 电话系统 上不可用，则应该让那些需要本地自定义功能的用户使用旧版 PBX，并且只需将不需要访问自定义功能的用户移植到具有本地 PSTN 连接的 电话系统。

有关直接与 Skype for Business Server 2015 进行互操作的旧 PBX 的列表，请参阅[Infrastructure Qualified for Microsoft Lync。](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 如果 PBX 不在此列表上，可以使用会话边界控制器将 PBX 与 电话系统 Online 中的Skype for Business连接。

### <a name="network-considerations-for-quality-and-performance"></a>质量和性能的网络注意事项

部署云托管的服务（电话系统本地 PSTN 连接）时，必须记住以下事项。 在纯本地 Skype for Business Server 2015 企业语音部署中，所有基础结构和客户端都位于企业自己的网络中。 此网络的质量和性能（对于高质量音频和视频至关重要）由企业员工直接控制。 使用电话系统 PSTN 连接时，涉及三个网络，其中两个网络由客户负责，但只有一个企业员工直接控制：

- **Microsoft 的全局媒体传递网络** Microsoft 的全球云网络和基础结构。 电话系统服务器和流量遍历此网络。

- **Enterprise/云 PSTN 互连** 这是将企业连接到云的网络。 这不一定与常规 Internet 连接相同。

- **企业自己的网络** 实时媒体的质量很大程度上取决于你自己的网络：尤其是 WiFi 网络和用于到达云的互连的质量。

> [!NOTE]
> 有关在 Skype for Business Online 中优化性能Skype for Business[请参阅优化联机性能](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>将本地 PSTN 电话系统 PSTN 连接的先决条件

在可以使用本地 PSTN 电话系统配置本地 PSTN 连接，以及将用户移动到 Skype for Business Online 之前，您必须确认已满足以下先决条件：

 **本地服务器版本。** 必须在下表中列出本地部署中的服务器版本，以支持电话系统 PSTN 连接。


| **服务器角色**                                       | **支持的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 联盟边缘\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 下一个跃点联盟路由内部池服务器  <br/> | Skype for Business Server 2015 年 3 月累积更新 6.0.9319.235 或更高版本 (前端或控制器)   <br/> |
| 前端用户服务器  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| 边缘服务器  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 中介服务器  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*受支持的最低版本为：

- Skype for Business Server 2015 年 3 月，2016 年 3 月累积更新 6.0.9319.235

- Lync Server 2013 2015 年 7 月累积更新 5.0.8308.920

\*\*所有受支持的 SIP 域的联盟路由必须通过运行 2016 年 3 月或更高版本累积更新的 Skype for Business Server 2015 边缘服务器进行路由。 如果用户池位于 Lync Server 2013 上，则外部池流量仍保留在 Lync Server 2013 边缘服务器上。 

此外，您必须确保：

- **为本地企业语音配置** 和测试本地用户这包括 PSTN 连接组件。 有关详细信息，请参阅以下主题（如果使用的是 Skype for Business Server 2015，请参阅在[Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)中规划 企业语音 和[Deploy 企业语音 in Skype for Business Server 2015。](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)

    如果您使用的是 Lync Server 2013，请参阅[Planning for 企业语音 in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice)和[Deploying 企业语音 in Lync Server 2013。](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)

- **Active Directory 同步** 必须使用 Azure AD 策略配置 Active Directory 连接。 有关详细信息，请参阅管理[Azure AD 连接。](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > 使用的 AAD 连接必须为版本 1.0.9125.0 或更高版本。 如果你使用的是较早版本的 AAD 连接工具或 DirSync，请升级到受支持的版本。 您可以升级当前安装并维护环境中定义的任何自定义规则。 

- **配置混合部署** 无论所有 Skype for Business 用户当前是联机还是本地，或者如果您当前拥有混合环境，都必须完成配置 Skype for Business Server 或 Lync Server 2013 的混合部署的步骤，如D部署 Skype for Business Server 和 [Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)之间的混合连接所述。 有关混合部署的背景详细信息，请参阅在混合部署和混合部署[Skype for Business Server Office 365。](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 

    如果您使用的是 Lync Server 2013，请参阅 [Lync Server 2013 hybrid](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)。

- **(AD FS) Active Directory 联合身份验证服务 (推荐) 。** 我们建议部署 AD FS 以支持单一登录。 有关详细信息，请参阅[Active Directory 联合身份验证服务 (AD FS) 。 ](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))

有关部署 PSTN 电话系统，请参阅在 电话系统 中为用户启用本地[PSTN Skype for Business Server。](enable-users-for-phone-system.md)