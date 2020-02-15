---
title: 在 Skype for Business Server 中规划使用本地 PSTN 连接的 Office 365 中的电话系统
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
description: 了解有关本地 PSTN 连接的 Office 365 （云 PBX）中的电话系统规划注意事项。
ms.openlocfilehash: be8fbe5671e2959341c08d4efa45829df0cc5e42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42020223"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for Business Server 中规划使用本地 PSTN 连接的 Office 365 中的电话系统

了解有关本地 PSTN 连接的 Office 365 （云 PBX）中的电话系统规划注意事项。

如果你已在本地部署 Skype for Business Server 或 Lync Server 2013，则此内容是相关的。 有关其他方案，请参阅[Microsoft 电话解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)。

 使用本地 PSTN 连接的 Office 365 中的电话系统使您能够为您的用户利用电话系统（云 PBX）功能。 这有助于以下方案：

- 你的某些 Skype for Business 用户驻留在本地，而其他用户驻留在 Skype for Business Online 中。 现在，您可以为驻留在 Skype for Business Online 中的用户启用 Office 365 功能和功能中的电话系统，但继续使用本地 PSTN 连接。

- 你具有本地部署，并且想要将部分或全部用户移动到 Skype for Business Online，但继续使用本地 PSTN 连接。

    > [!IMPORTANT]
    > 若要在具有本地 PSTN 连接的 Office 365 中成功启用电话系统的用户，其 SIP 地址必须位于您自己的域中。 不支持对 Office 365，onmicrosoft.com 使用默认域。 

若要了解有关 Office 365 中的电话系统的详细信息（包括许可和计划），请参阅[适用于 Skype for business 的 PSTN 呼叫计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比较

具有本地 PSTN 连接的云 PBX 不会提供与完全本地企业语音解决方案相同的功能集。 若要帮助您确定具有本地 PSTN 连接的云 PBX 是否会为您的组织提供正确的功能集，请参阅[通过云 PBX 获取](https://go.microsoft.com/fwlink/?LinkId=715517)的功能。

## <a name="benefits-and-planning-considerations"></a>好处和规划注意事项

> [!CAUTION]
> 在迁移到 Skype for business Online 之前，必须将 Lync Phone Edition 设备更新为在本地环境中所需的最低固件。
如果在更新固件之前将用户从本地迁移到联机，用户将无法使用其电话进行连接。 若要解决此问题，必须将用户移回本地环境以将其手机更新为最低固件。 在将用户移回您的本地环境之前，请勿尝试更新到最低固件或硬重置电话。
如果在设备不是最小固件时执行硬重置，将默认使用 PIN 身份验证，这在 Skype for Business Online 中不受支持。 有关详细信息，请参阅[获取适用于 Skype for Business Online 的电话](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

通过使用本地 PSTN 连接部署 Office 365 中的电话系统，你可以按自己的步调将用户移动到云，同时保留其本地 PSTN 连接。 如果你有一个 PBX，你将继续使用它为你移动到云的用户提供 PSTN 连接。 一旦将用户移动到 Skype for business Online 和 Office 365 中的电话系统，他们的旧 PBX 电话将不再起作用，但其电话号码将路由到任何 Skype for business 客户端，以用于电脑或智能手机以及 Skype for business 合规的桌面电话今天. 一旦移植，Office 365 中的电话系统就可以正常通话，并使用其正常电话号码拨打/接听 PSTN 呼叫。

您可能对旧版 PBX （如呼叫中心）具有自定义功能或主要加载项。 如果自定义功能当前在 Office 365 中的电话系统上不可用，则应将需要该自定义功能的那些用户与旧版 PBX 保持在本地，仅将无需访问自定义功能的用户移植到 Office 365 中的电话系统使用本地 PSTN 连接。

有关与 Skype for Business Server 2015 直接交互的旧版 Pbx 的列表，请参阅[适用于 Microsoft Lync 的基础结构](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)。 如果你的 PBX 不在此列表中，则可以使用会话边界控制器在 Skype for business Online 中将你的 PBX 与 Office 365 中的电话系统进行连接。

### <a name="network-considerations-for-quality-and-performance"></a>质量和性能的网络注意事项

在使用本地 PSTN 连接在 Office 365 中部署云托管服务（如电话系统）时，必须记住以下事项。 在单纯的本地 Skype for business Server 2015 企业语音部署中，所有基础结构和客户端都位于企业自己的网络中。 此网络的质量和性能对于高质量的音频和视频而言非常关键，是企业员工的直接控制。 使用具有本地 PSTN 连接的 Office 365 中的电话系统，有三个网络，客户负责的两个网络，但只有一个企业员工可以直接控制以下内容：

- **Microsoft 的全局媒体传递网络**Microsoft 的全球云网络和基础结构。 Office 365 服务器和流量遍历此网络中的 office 365 和电话系统。

- **企业/云 PSTN 互连**这是将企业连接到 Office 365 云的网络。 这并不一定与常规 Internet 连接相同。

- **企业自己的网络**实时媒体的质量很大程度上依赖于您自己的网络：尤其是 WiFi 网络和用于访问 Office 365 云的互连的质量。

> [!NOTE]
> 有关在 Skype for Business Online 中优化性能的详细信息，请参阅[调谐 Skype For Business online 性能](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>在使用本地 PSTN 连接的 Office 365 中使用电话系统的先决条件

在使用本地 PSTN 连接来配置 Office 365 中的电话系统并将用户移动到 Skype for Business Online 之前，必须确认已满足以下先决条件：

 **本地服务器版本。** 您的本地部署中的服务器版本必须在下表中列出，以支持使用本地 PSTN 连接的 Office 365 中的电话系统。


| **服务器角色**                                       | **支持的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 联盟边缘\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 下一个跃点联合路由内部池服务器  <br/> | Skype for Business Server 2015，3月2016累积更新6.0.9319.235 或更高版本（前端或控制器）  <br/> |
| 前端用户服务器  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| 边缘服务器  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 中介服务器  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*支持的最低版本包括：

- Skype for Business Server 2015，3月2016累积更新6.0.9319.235

- Lync Server 2013 月2015累积更新5.0.8308.920

\*\*所有受支持的 SIP 域的联盟路由都必须通过运行3月2016或更高累积更新的 Skype for Business Server 2015 边缘服务器进行路由。 如果用户池在 Lync Server 2013 上，则该外部池流量将保留在 Lync Server 2013 边缘服务器上。 

此外，还必须确保满足以下条件：

- **本地企业语音已配置并测试本地用户**这包括 PSTN 连接组件。 有关详细信息，请参阅以下主题：如果使用的是 Skype for Business Server 2015，请参阅[Plan For Enterprise voice In skype For Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)和[在 Skype for Business Server 中部署企业语音一 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。

    如果您使用的是 Lync Server 2013，请参阅在 lync server [2013 中规划企业语音](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx)和[在 Lync Server 中部署企业语音 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx)。

- **Active Directory 同步**必须使用 Azure AD Connect 配置 Active Directory 同步。 有关详细信息，请参阅[管理 AZURE AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)。

    > [!NOTE]
    > 您使用的 AAD Connect 版本必须是版本1.0.9125.0 或更高版本。 如果使用的是较早版本的 AAD Connect 工具或 DirSync，请升级到支持的版本。 您可以升级当前安装并维护您在环境中定义的任何自定义规则。 

- **配置混合部署**无论您的所有 Skype for Business 用户当前都是联机还是本地托管，或者如果你当前有组合，你必须完成配置 Skype for business Server 或 Lync Server 2013 的混合部署的步骤，如在[Skype for Business server 与 Office 365 之间部署混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)中所述。 有关混合部署的更多背景信息，请参阅[规划 Skype For Business Server 和 Office 365 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 

    如果您使用的是 Lync Server 2013，请参阅[Lync server 2013 混合](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx)。

- **适合Active Directory 联合身份验证服务（AD FS）。** 我们建议部署 AD FS 以支持单一登录。 有关详细信息，请参阅[Active Directory 联合身份验证服务（AD FS）](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx)。

有关在 Office 365 中部署电话系统的信息，请参阅在[Skype For Business Server 中使用本地 PSTN 连接为 office 365 中的电话系统启用用户](enable-users-for-phone-system.md)。


