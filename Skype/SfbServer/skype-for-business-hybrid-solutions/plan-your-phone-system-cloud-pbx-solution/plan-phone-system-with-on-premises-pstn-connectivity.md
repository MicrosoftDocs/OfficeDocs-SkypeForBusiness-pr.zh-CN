---
title: 在 Skype for business Server 中通过本地 PSTN 连接计划 Office 365 中的电话系统
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
ms.openlocfilehash: a134b4dbe48d302ee8be8df528e6bbebac336b8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814480"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for business Server 中通过本地 PSTN 连接计划 Office 365 中的电话系统

了解有关本地 PSTN 连接的 Office 365 （云 PBX）中的电话系统规划注意事项。

如果你已有本地部署的 Skype for business 服务器或 Lync Server 2013，则此内容是相关的。 有关其他方案，请参阅[Microsoft 电话解决方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)。

 使用本地 PSTN 连接的 Office 365 中的电话系统使你能够为你的用户利用电话系统（云 PBX）功能。 这在以下情况下可能很有帮助：

- 您有一些 Skype for Business 用户驻留在本地，而其他人驻留在 Skype for business Online 中。 现在，你可以为驻留在 Skype for business Online 中的用户启用 Office 365 功能和功能中的电话系统，但继续使用本地 PSTN 连接。

- 你有一个本地部署，你希望将部分或全部用户移动到 Skype for Business Online，但继续使用本地 PSTN 连接。

    > [!IMPORTANT]
    > 若要在使用本地 PSTN 连接的 Office 365 中成功启用电话系统的用户，其 SIP 地址必须位于您自己的域中。 不支持对 Office 365 使用默认域 onmicrosoft.com。 

若要了解有关 Office 365 中的电话系统的详细信息（包括授权和计划），请参阅[Skype for business 的 PSTN 呼叫计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比较

具有本地 PSTN 连接的云 PBX 不会提供与完全本地企业语音解决方案相同的功能集。 为帮助你确定具有本地 PSTN 连接的云 PBX 是否会为你的组织提供正确的功能集，请参阅[以下是使用云 PBX 获取](https://go.microsoft.com/fwlink/?LinkId=715517)的功能。

## <a name="benefits-and-planning-considerations"></a>好处和规划注意事项

> [!CAUTION]
> 在迁移到 Skype for Business Online 之前，必须更新 Lync Phone Edition 设备以符合最低的必要固件要求。
如果在更新固件之前将用户从本地环境迁移到联机环境，用户将无法使用其电话进行连接。 要更正此问题，必须将用户移回到本地环境以将其电话固件更新为最低要求的固件。 请勿在将用户移回到本地环境之前尝试更新到最低要求的固件或对电话执行硬重置。
如果在设备未安装最低要求的固件时执行了硬重置，设备将默认为使用 PIN 身份验证，而 Skype for Business Online 不支持这种验证方式。 有关详细信息，请参阅[获取 Skype for Business Online 的电话](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

通过使用本地 PSTN 连接在 Office 365 中部署电话系统，你可以按照自己的节奏将用户移动到云，并保留其本地 PSTN 连接。 如果你有 PBX，则可以继续使用它为迁移到云的用户提供 PSTN 连接。 在 Office 365 中将用户移动到 Skype for Business Online 和电话系统后，其旧 PBX 电话将不再有效，但其电话号码将路由到任何 Skype for business 客户端或智能电话，以及 Skype for business 兼容的桌面电话症状. 移植后，Office 365 中的电话系统和传统 PBX 用户可以正常通话，也可以使用其普通电话号码拨打或接收 PSTN 呼叫。

你可以有自定义功能或主要传统 PBX 加载项，如呼叫中心。 如果自定义功能当前在 Office 365 中的电话系统上不可用，则应将需要该自定义功能的用户与旧版 PBX 一起离开，并且仅将不需要访问自定义功能的用户移植到 Office 365 中的电话系统具有本地 PSTN 连接。

有关直接与 Skype for Business Server 2015 互操作的传统 Pbx 的列表，请参阅[Microsoft Lync 合格的基础结构](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)。 如果你的 PBX 不在此列表中，你可以使用会话边界控制器在 Skype for business Online 中使用 Office 365 中的电话系统连接 PBX。

### <a name="network-considerations-for-quality-and-performance"></a>质量和性能相关的网络注意事项

使用本地 PSTN 连接在 Office 365 中部署与云托管的服务（如手机系统）时，必须牢记以下事项。 在纯粹的内部部署 Skype for Business Server 2015 企业语音部署中，所有基础结构和客户都位于企业自己的网络上。 此网络的质量和性能（对于高质量音频和视频至关重要）直接受企业员工控制。 通过具有本地 PSTN 连接的 Office 365 中的电话系统，有三个网络，客户负责的两个网络，但只有一个企业人员可以直接控制以下内容：

- **Microsoft 的全球媒体交付网络**Microsoft 的全球云网络和基础结构。 Office 365 服务器中的 office 365 和电话系统以及流量遍历此网络。

- **企业/云 PSTN 互连**这是将企业连接到 Office 365 云的网络。 这并不一定与一般互联网连接相同。

- **您的企业自己的网络**实时媒体的质量很大程度上取决于您自己的网络：尤其是 WiFi 网络和用于到达 Office 365 云的互连的质量。

> [!NOTE]
> 有关在 Skype for Business Online 中优化性能的详细信息，请参阅[优化 skype for Business online 性能](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>将 Office 365 中的电话系统与本地 PSTN 连接结合使用的先决条件

在使用本地 PSTN 连接配置 Office 365 中的电话系统并将用户移动到 Skype for business Online 之前，必须确认存在以下先决条件：

 **本地服务器版本。** 您的本地部署中的服务器版本必须在下表中列出，以支持 Office 365 中的电话系统和本地 PSTN 连接。


| **服务器角色**                                       | **支持的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 联盟边缘\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| 下一跳联盟路由内部池服务器  <br/> | Skype for Business Server 2015，2016 年 3 月累积更新 6.0.9319.235 或更高版本（前端或控制器）   <br/> |
| 前端用户服务器  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| 边缘服务器  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| 中介服务器  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*支持的最低版本包括：

- Skype for Business Server 2015，2016 年 3 月累积更新 6.0.9319.235

- Lync Server 2013，2015 年 7 月累积更新 5.0.8308.920

\*\*所有支持的 SIP 域的联盟路线必须通过运行3月2016或更高累积更新的 Skype for Business Server 2015 Edge 服务器进行路由。 如果用户池在 Lync Server 2013 中，该外部池流量将保留在 Lync Server 2013 Edge Server 中。 

此外，您必须确保以下内容：

- **本地企业语音已针对本地用户进行配置和测试**这包括 PSTN 连接组件。 有关详细信息，请参阅以下主题如果你使用的是 Skype for Business Server 2015，请参阅在 skype for business [server 2015 中规划企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)和[在 Skype for business Server 2015 中部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。

    如果您使用的是 Lync Server 2013，请参阅在 lync server [2013 中规划企业语音](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx)和[在 Lync Server 中部署企业语音 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)。

- **Active Directory 同步**必须使用 Azure AD Connect 配置 Active Directory 同步。 有关详细信息，请参阅[管理 AZURE AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)。

    > [!NOTE]
    > 您所使用的 AAD Connect 版本必须是版本 1.0.9125.0 或更高版本。如果您使用较早版本的 AAD Connect 工具或 DirSync，请升级到支持的版本。您可以升级您的当前安装并维护您在环境中定义的任何自定义规则。 

- **配置混合部署**无论您的所有 Skype for Business 用户当前是联机还是本地托管，或者如果您当前有混合版，您必须完成配置 Skype for business Server 或 Lync Server 2013 的混合部署的步骤，如在[skype for Business 服务器与 Office 365 之间部署混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)中所述。 有关混合部署的更多背景信息，请参阅在[Skype For Business 服务器和 Office 365 之间规划混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 

    如果您使用的是 Lync Server 2013，请参阅[Lync server 2013 混合](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)。

- **建议您使用Active Directory 联合身份验证服务（AD FS）。** 我们建议部署 AD FS 以支持单一登录。 有关详细信息，请参阅[Active Directory 联合身份验证服务（AD FS）](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)。

有关在 Office 365 中部署电话系统的信息，请参阅在[Skype for Business 服务器中使用本地 PSTN 连接在 office 365 中启用电话系统的用户](enable-users-for-phone-system.md)。


