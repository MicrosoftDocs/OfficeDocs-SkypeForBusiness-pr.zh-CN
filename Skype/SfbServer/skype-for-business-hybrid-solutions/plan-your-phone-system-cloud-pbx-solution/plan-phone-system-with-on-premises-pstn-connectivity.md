---
title: Office 365 中的电话系统内部在 Skype 的 PSTN 连接规划业务服务器
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 了解 Office 365 (云 PBX) 中的电话系统的规划考虑因素与内部的 PSTN 连接性。
ms.openlocfilehash: 5b244ea55305d88cc214875dc74837f027cc3dd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Office 365 中的电话系统内部在 Skype 的 PSTN 连接规划业务服务器
 
了解 Office 365 (云 PBX) 中的电话系统的规划考虑因素与内部的 PSTN 连接性。
  
如果您已经具有的业务服务器 Skype 或 Lync Server 2013 部署内部，此内容是相关的。 对于其他情况，请参阅[规划 Office 365 (云 PBX) 解决方案中的电话系统](plan-your-phone-system-cloud-pbx-solution.md)。
  
 在 Office 365 的 PSTN 连接内部电话系统使您能够利用电话系统 (云 PBX) 为您的用户的能力。 这在以下情况下可能很有帮助：
  
- 有一些您的业务用户穴内部 Skype 和其他人驻留在 Skype 的在线业务。 现在可以在 Office 365 功能启用电话系统和功能为您的用户在 Skype 穴的业务联机，但继续使用内部部署的 PSTN 连接性。
    
- 必须在内部部署和想要进入某些或所有用户 Skype 的在线业务，但继续使用内部部署的 PSTN 连接性。
    
    > [!IMPORTANT]
    > 要成功地与内部的 PSTN 连接使 Office 365 中的电话系统的用户，他们的 SIP 地址必须是您自己的域。 不支持对 Office 365 使用默认域 onmicrosoft.com。 
  
若要了解更多有关 Office 365 包括授权和计划中的电话系统，请参阅[PSTN 调用 Skype 业务的计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
  
## <a name="feature-comparison"></a>功能比较

内部的 PSTN 连接云 PBX 不提供相同的功能作为一个完全内部的企业语音解决方案集。 为了帮助您决定内部的 PSTN 连接云 PBX 是否将提供您为组织设置正确的特征，看到[这里是云 PBX 与获取的内容](https://go.microsoft.com/fwlink/?LinkId=715517)。
  
## <a name="benefits-and-planning-considerations"></a>好处和规划注意事项

> [!CAUTION]
> 在迁移到 Skype for Business Online 之前，必须更新 Lync Phone Edition 设备以符合最低的必要固件要求。
如果在更新固件之前将用户从本地环境迁移到联机环境，用户将无法使用其电话进行连接。 要更正此问题，必须将用户移回到本地环境以将其电话固件更新为最低要求的固件。 请勿在将用户移回到本地环境之前尝试更新到最低要求的固件或对电话执行硬重置。
如果在设备未安装最低要求的固件时执行了硬重置，设备将默认为使用 PIN 身份验证，而 Skype for Business Online 不支持这种验证方式。 有关详细信息，请参阅[获得电话的 Skype 的在线业务](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
通过内部的 PSTN 连接部署 Office 365 中的电话系统，可以移动用户到云通过 Skype 的在线业务在您自己的节奏，同时保留其内部的 PSTN 连接性。 如果您有 PBX，您可以继续使用它为迁移到云的用户提供 PSTN 连接。 一旦将用户移动到 Skype 的在线业务和 Office 365 中的电话系统，其传统的 PBX 电话将不再起作用，但他们的电话号码将路由到任何 Skype 业务客户端电脑或智能手机以及 Skype 业务符合服务台电话s。 一旦移植，在 Office 365 提供用户和传统 PBX 用户电话系统可以互相通常调用以及使/接收 PSTN 呼叫使用他们的普通电话号码。
  
您可以有自定义功能或主要传统 PBX 加载项。 如果自定义功能当前不可用 Office 365 中的电话系统上，您应将那些用户需要的自定义功能内部与传统 PBX 和只是端口的用户不需要访问到 Office 365 中的电话系统自定义功能与内部的 PSTN 连接性。
  
直接与业务服务器 2015年的 Skype 传统 Pbx，可互操作的列表，请参阅[Microsoft Lync 为合格的基础结构](https://technet.microsoft.com/en-us/office/dn788945.aspx)。 如果您 PBX 不在此列表中，您可以使用会话边框控制器您 PBX 与 Skype 在 Office 365 中的电话系统的在线业务。
  
### <a name="network-considerations-for-quality-and-performance"></a>质量和性能相关的网络注意事项

在部署 Office 365 中的电话系统如云托管服务内部的 PSTN 连接时，您必须记住以下。 商业服务器 2015年企业语音部署纯粹是内部部署 Skype，在所有基础结构和客户端是企业自己的网络上。 此网络的质量和性能（对于高质量音频和视频至关重要）直接受企业员工控制。 与内部的 PSTN 连接 Office 365 中的电话系统，有三个网络涉及到，客户的负责的两个，但只有一种企业人员所具有的通过的直接控制：
  
- **Microsoft 的全球媒体传递网络**Microsoft 的全球云网络和基础结构。 Office 365 和电话系统在 Office 365 提供服务器和通讯通过此网络。
    
- **企业/云 PSTN 互联**这是到 Office 365 云连接企业网络。 这不一定是泛型 Internet 连接相同。
    
- **企业自己的网络**质量的实时媒体非常依赖自己的网络： 尤其是 WiFi 网络和用于到达 Office 365 云互连的质量。
    
> [!NOTE]
> Skype 的在线业务的优化性能的详细信息，请参阅[调整的 Skype 的在线业务性能](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 
  
## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>在 Office 365 的电话系统使用内部部署的 PSTN 连接性的先决条件

可以配置电话系统 Office 365 中内部的 PSTN 连接和移动用户 Skype 的在线业务之前，您必须确认您在的地方有以下先决条件：
  
 **内部服务器版本。** 在内部部署中的服务器的版本必须列入下表，以支持 Office 365 的 PSTN 连接内部电话系统。
  
|**服务器角色**|**受支持的版本\***|
|:-----|:-----|
|联合身份验证边缘\*\*  <br/> |Skype for Business Server 2015  <br/> |
|下一跳联盟路由内部池服务器  <br/> |Skype for Business Server 2015，2016 年 3 月累积更新 6.0.9319.235 或更高版本（前端或控制器）  <br/> |
|前端用户服务器  <br/> |Skype for Business Server 2015  <br/> Lync Server 2013  <br/> |
|边缘服务器  <br/> |Skype for Business Server 2015  <br/> |
|中介服务器  <br/> |Skype for Business Server 2015  <br/> Lync Server 2013  <br/> |
   
\*支持的最低版本是：
  
- Skype for Business Server 2015，2016 年 3 月累积更新 6.0.9319.235
    
- Lync Server 2013，2015 年 7 月累积更新 5.0.8308.920
    
\*\*联合身份验证路由的所有受支持的 SIP 域必须穿业务服务器 2015年边缘服务器运行 Skype 2016 或更高版本 3 月累计更新。 如果用户池在 Lync Server 2013 中，该外部池流量将保留在 Lync Server 2013 Edge Server 中。 
  
此外必须确保以下：
  
- **配置和测试为内部用户内部企业语音**这包括 PSTN 连接组件。 详细信息，请参阅下列主题，如果您使用 Skype 业务服务器 2015年，请参阅[规划业务服务器 2015年的 Skype 在企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)和[业务服务器 2015年的 Skype 在部署企业语音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
    
    如果您正在使用 Lync Server 2013，请参阅[企业语音 Lync Server 2013 在规划](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx)和[部署中 Lync Server 2013 的企业语音](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)。
    
- **活动目录同步**您必须配置使用 Azure AD 连接 Active Directory 同步。 有关详细信息，请参阅[管理 Azure AD 连接](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-whats-next/)。
    
    > [!NOTE]
    > 您所使用的 AAD Connect 版本必须是版本 1.0.9125.0 或更高版本。如果您使用较早版本的 AAD Connect 工具或 DirSync，请升级到支持的版本。您可以升级您的当前安装并维护您在环境中定义的任何自定义规则。 
  
- **配置混合部署**是否所有您的业务用户的 Skype 目前穴可以联机或内部，或如果您当前有多，[部署混合所述，您必须完成配置业务服务器或 Lync Server 2013，Skype 的混合部署的步骤Skype 业务服务器和 Skype 的在线业务之间的连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。 在混合部署的更多背景信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。 
    
    如果您正在使用 Lync Server 2013，看到[Lync Server 2013 混合](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)。
    
- **Active Directory 联合身份验证服务 (AD FS) （推荐）**我们建议部署 AD FS 可支持单一登录。 有关详细信息，请参阅[Active Directory 联合身份验证服务 (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)。
    
有关部署 Office 365 中的电话系统的信息，请参阅[启用内部 Skype 业务服务器中的 PSTN 连接与 Office 365 中的电话系统的用户](enable-users-for-phone-system.md)。
  

