---
title: 采用 PSTN 连接的混合环境中的用户帐户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 了解不同的用户创建和组合的受支持或不受支持的组合。
ms.openlocfilehash: f85a9903c2b1d35d110c26b276305ed4c9ce949a
ms.sourcegitcommit: 5cf9b45ad87aebfd46d3f1f757786c01804143ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "29635721"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>采用 PSTN 连接的混合环境中的用户帐户

## <a name="about-the-environment"></a>有关环境

本文适用于具有以下所有的环境： 
 
- Skype 业务服务器或 Lync Server 2013 
- Office 365 租户 
- Skype 业务服务器和 Skype 业务联机或 Microsoft 团队租户之间配置混合连接性 
- 启用发起和接收和来自客户端的公共公用电话交换网 (PSTN) 呼叫的用户

 
如果您具有不同的环境 （如业务云连接器 edition Skype)、 混合未配置，或您的用户将不会启用 PSTN 呼叫，可支持性矩阵将不同。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>组合以及可支持性语句  

通过 PSTN 连接的业务混合环境 Skype 提供了有关用户服务提供的位置和设置和管理用户帐户的方式的灵活性。 但选项大量可能创建某些不受支持的组合。 本节介绍不同的用户创建，可支持性语句后跟组合。


**定义：**   
- **企业语音：** 提供具有内部部署 Skype 业务用户帐户的用户访问 PSTN 的选项。 业务中介服务器的内部部署 Skype pstn 提供互联性。  
- **混合语音连接性：** 提供与联机 Skype 的 pstn 访问业务帐户的选项。 业务中介服务器的内部部署 Skype pstn 提供互联性。 
- **直接路由：** 具有联机 Skype 业务帐户，Microsoft 团队许可证，使用的 Microsoft 团队客户端的用户提供 PSTN 访问的选项。 SBC 从 Microsoft 连接到 Office 365 中 SIP 代理服务器不需要任何本地软件。

  
**环境支持下列组合：**
- **方案 1:** 用户帐户中的本地业务 Skype 和将 Skype 用于业务客户端与企业语音
- **方案 2:** 用户帐户中 Skype 在线业务和将 Skype 用于业务混合语音连接的客户端
- **方案 3:** 用户帐户中的业务联机 Skype 与 Microsoft 团队许可证，并将使用团队客户端
 
### <a name="supportability-matrix"></a>可支持性矩阵


|**中创建的用户对象**  |**业务服务提供商的用户的 Skype**|**用户的客户端**|**语音选项**|**支持**|
| ------------ | --------- | --------- | --------- | -------- |
|本地 AD| 内部部署 |Skype for Business   | 企业语音   |是|
|本地 AD|Online| Skype for Business  | 混合语音连接   |是 |
|本地 AD|Online |Microsoft Teams |直接路由  |是 |
|**不受支持的组合**    | |         |         |      |
|Azure AD| 部署/online 上 | Skype 业务/Microsoft 团队|企业语音/混合语音连接/直接路由  |否，必须在用户对象中创建的本地 AD 首先 |
|本地 AD  |内部部署| Microsoft Teams| 企业语音/混合语音连接/直接路由   |否，Microsoft 团队客户端不支持的本地 Skype for Business |     
|本地 AD  |Online |Skype for Business  | 直接路由  |否，直接路由中不支持与 Skype for Business 客户端，用户必须先为 Skype for Business 中的企业语音启用  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>与 PSTN 的混合环境的可支持性语句

所有用户的用户对象**必须**在内部部署中创建 AD 和同步到 Azure AD 使用 Azure AD 连接工具。 为用户启用团队/Skype 的业务**不支持**如果直接在 Azure AD 混合配置中创建的用户对象。 为新用户，如新员工，用户将直接为团队启用，用户必须的 Skype 启用业务在本地 Skype 使用的业务管理工具。 在中创建用户联机 Skype 适用于商务或团队没有首先启用它们与企业语音**不支持**的本地池中。 请有关如何为用户启用 for Business 的 Skype 混合配置，参阅[本文](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises)的详细信息。
