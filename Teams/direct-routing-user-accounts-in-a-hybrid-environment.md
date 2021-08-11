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
ms.openlocfilehash: 5b272ba42235b37b15c44d69fb4d96a444bd3b79498d0ade02aa0e1d15668a4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279729"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>采用 PSTN 连接的混合环境中的用户帐户

## <a name="about-the-environment"></a>关于环境

本文适用于具有以下所有功能的环境： 
 
- Skype for Business Server Lync Server 2013 
- 组织Microsoft 365或Office 365组织 
- 在 Skype for Business Server 与 Skype for Business Online 或 Microsoft Teams 租户之间配置的混合连接 
- 已启用与客户端建立和接收公用电话交换网 (PSTN) 呼叫的用户

 
如果具有不同的环境 (例如 Skype for Business 云连接器版本) 、未配置混合或未为用户启用 PSTN 呼叫，则可支持性矩阵会有所不同。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>关于组合和可支持性声明  

使用Skype for Business PSTN 连接的混合环境在提供用户服务以及如何预配和管理用户帐户方面提供了灵活性。 但是，选项的丰富可能会创建一些不受支持的组合。 本部分介绍用户创建的不同组合，后跟可支持性声明。


**定义：**   
- **企业语音：** 为使用本地用户帐户的用户提供 PSTN Skype for Business选项。 本地中介Skype for Business提供与 PSTN 的互连。  
- **混合语音连接：** 为具有联机帐户的用户提供 PSTN Skype for Business的选项。 本地中介Skype for Business提供与 PSTN 的互连。 
- **直接路由：** 为具有联机登录帐户的用户提供 PSTN Skype for Business选项，Microsoft Teams许可证，Microsoft Teams客户端。 SBC 连接到 Microsoft 365 或 Office 365 中的 SIP 代理，无需 Microsoft 提供的任何本地软件。

  
**环境支持以下组合：**
- **方案 1：** 本地Skype for Business用户帐户，Skype for Business客户端企业语音
- **方案 2：** 适用于企业Skype中的用户帐户，将 Skype for Business 客户端与混合语音连接一起使用
- **方案 3：** 使用许可证Skype for Business联机Microsoft Teams用户帐户，Teams客户端
 
### <a name="supportability-matrix"></a>可支持性矩阵


|**在 中创建的用户对象**  |**用户的 Skype for Business 服务提供商**|**用户的客户端**|**语音选项**|**支持**|
| ------------ | --------- | --------- | --------- | -------- |
|本地 AD| 内部部署 |Skype for Business   | 企业语音   |是|
|本地 AD|Online| Skype for Business  | 混合语音连接   |是 |
|本地 AD|Online |Microsoft Teams |直接路由  |是 |
|**不支持的组合**    | |         |         |      |
|Azure AD| 本地/联机 | Skype for Business/Microsoft Teams|企业语音/混合语音连接/直接路由  |否，必须先在本地 AD 中创建用户对象 |
|本地 AD  |内部部署| Microsoft Teams| 企业语音/混合语音连接/直接路由   |否Microsoft Teams，本地客户端不支持Skype for Business |     
|本地 AD  |Online |Skype for Business  | 直接路由  |否，客户端不支持直接Skype for Business路由  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>使用 PSTN 的混合环境的可支持性声明

对于所有用户，必须在本地 AD 中创建用户对象，然后使用 Azure AD 连接 Azure AD。  如果用户对象是在混合Teams Azure AD中直接创建的，则不支持为用户启用 Teams/Skype for Business。 对于新用户（例如新雇员）将直接启用Teams，必须使用本地 Skype for Business管理工具为Skype for Business启用用户。 不支持在不Skype for Business或Teams本地池中先启用用户的情况下创建联机企业语音 **用户**。 有关详细信息，请参阅使用 电话系统 中的本地[PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)连接规划Skype for Business Server。