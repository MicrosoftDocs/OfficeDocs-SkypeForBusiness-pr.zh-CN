---
title: 使用 PSTN 的混合环境中用户帐户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解用户创建的不同组合以及支持或不支持的组合。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096322"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>采用 PSTN 连接的混合环境中的用户帐户

## <a name="about-the-environment"></a>关于环境

本文适用于具有以下所有功能的环境： 
 
- Skype for Business Server 或 Lync Server 2013 
- Microsoft 365 或 Office 365 组织 
- 在 Skype for Business Server 和 Skype for Business Online 或 Microsoft Teams 租户之间配置的混合连接 
- 已启用与客户端建立和接收公用电话交换网 (PSTN) 呼叫的用户

 
如果你有不同的环境 (如 Skype for Business Cloud Connector Edition) 、未配置混合，或者未为用户启用 PSTN 呼叫，则可支持性矩阵会有所不同。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>关于组合和可支持性声明  

具有 PSTN 连接的 Skype for Business 混合环境在提供用户服务以及如何预配和管理用户帐户方面提供了灵活性。 但是，选项的丰富可能会创建一些不受支持的组合。 本部分介绍用户创建的不同组合，后跟可支持性声明。


**定义：**   
- **企业语音：** 为具有本地 Skype for Business 用户帐户的用户提供 PSTN 访问权限的选项。 本地 Skype for Business 中介服务器提供与 PSTN 的互连。  
- **混合语音连接：** 为使用 Skype for Business Online 帐户的用户提供 PSTN 访问权限的选项。 本地 Skype for Business 中介服务器提供与 PSTN 的互连。 
- **直接路由：** 为具有在线 Skype for Business 帐户、Microsoft Teams 许可证、使用 Microsoft Teams 客户端的用户提供 PSTN 访问权限的选项。 SBC 连接到 Microsoft 365 或 Office 365 中的 SIP 代理，无需 Microsoft 提供的任何本地软件。

  
**环境支持以下组合：**
- **方案 1：** 本地 Skype for Business 中的用户帐户，将 Skype for Business 客户端与 企业语音
- **方案 2：** Skype for business Online 中的用户帐户，将 Skype for Business 客户端与混合语音连接一起使用
- **方案 3：** 具有 Microsoft Teams 许可证的 Skype for Business Online 用户帐户，将使用 Teams 客户端
 
### <a name="supportability-matrix"></a>可支持性矩阵


|**在 中创建的用户对象**  |**用户的 Skype for Business 服务提供商**|**用户的客户端**|**语音选项**|**支持**|
| ------------ | --------- | --------- | --------- | -------- |
|本地 AD| 内部部署 |Skype for Business   | 企业语音   |是|
|本地 AD|Online| Skype for Business  | 混合语音连接   |是 |
|本地 AD|Online |Microsoft Teams |直接路由  |是 |
|**不支持的组合**    | |         |         |      |
|Azure AD| 本地/联机 | Skype for Business/Microsoft Teams|企业语音/混合语音连接/直接路由  |否，必须先在本地 AD 中创建用户对象 |
|本地 AD  |内部部署| Microsoft Teams| 企业语音/混合语音连接/直接路由   |否，本地 Skype for Business 不支持 Microsoft Teams 客户端 |     
|本地 AD  |Online |Skype for Business  | 直接路由  |否，Skype for Business 客户端不支持直接路由  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>使用 PSTN 的混合环境的可支持性声明

对于所有用户，必须在本地 AD 中创建用户对象，然后使用 Azure AD Connect 工具同步到 Azure AD。  如果用户对象是在混合配置中直接在 Azure AD 中创建的，则不支持为用户启用 Teams/Skype for **Business。** 对于新用户（例如将直接为 Teams 启用的新员工）来说，必须使用本地 Skype for Business 管理工具为该用户启用 Skype for Business。 不支持在联机 Skype for Business 或 Teams 中创建用户，而不首先在本地池中使用 企业语音 **用户**。 有关详细信息，请参阅在 Skype for Business Server 中使用本地 [PSTN 连接规划电话系统](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。