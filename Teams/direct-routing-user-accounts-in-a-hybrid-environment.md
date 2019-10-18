---
title: 采用 PSTN 连接的混合环境中的用户帐户
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
description: 了解用户创建的不同组合以及支持或不支持的组合。
ms.openlocfilehash: bf2fee0646e5230964673af4dbfa4fed22086cdc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572109"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>采用 PSTN 连接的混合环境中的用户帐户

## <a name="about-the-environment"></a>关于环境

本文适用于您拥有以下所有内容的环境： 
 
- Skype for Business 服务器或 Lync Server 2013 
- Office 365 租户 
- 在 Skype for Business 服务器与 Skype for business Online 或 Microsoft 团队租户之间配置的混合连接 
- 在客户端上启用和接收公共交换电话网络（PSTN）呼叫的用户

 
如果你有其他环境（如 Skype for business 云连接器版）、混合未配置或你的用户未启用 PSTN 呼叫，则 "可支持性" 矩阵将有所不同。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>关于组合和可支持性语句  

具有 PSTN 连接的 Skype for business 混合环境提供了有关提供用户服务的位置以及如何设置和管理用户帐户的灵活性。 但是，丰富的选项可能会创建一些不受支持的组合。 本部分介绍用户创建的不同组合，后跟一个可支持性语句。


**码**   
- **企业语音：** 用于向使用本地 Skype for business 用户帐户的用户提供对 PSTN 的访问的选项。 本地 Skype for Business 中介服务器向 PSTN 提供 interconnectivity。  
- **混合语音连接：** 用于为使用 Skype for business Online 帐户的用户提供对 PSTN 的访问的选项。 本地 Skype for Business 中介服务器向 PSTN 提供 interconnectivity。 
- **直接路由：** 选项，为使用 Microsoft 团队客户端的联机 Skype for Business 帐户、Microsoft 团队许可证的用户提供对 PSTN 的访问。 SBC 已连接到 Office 365 中的 SIP 代理，无需任何本地的 Microsoft 软件。

  
**环境支持以下组合：**
- **情形1：** 本地 Skype for Business 中的用户帐户，并且将使用具有企业语音的 Skype for Business 客户端
- **方案2：** Skype for business online 中的用户帐户，并将使用具有混合语音连接的 Skype for Business 客户端
- **情形3：** Skype for business online 中使用 Microsoft 团队许可证的用户帐户，并将使用团队客户端
 
### <a name="supportability-matrix"></a>支持列表


|**在中创建的用户对象**  |**用户的 Skype for Business 服务提供商**|**用户的客户端**|**语音选项**|**支持**|
| ------------ | --------- | --------- | --------- | -------- |
|本地广告| 内部部署 |Skype for Business   | 企业语音   |是|
|本地广告|Online| Skype for Business  | 混合语音连接   |是 |
|本地广告|Online |Microsoft Teams |直接路由  |是 |
|**不支持的组合**    | |         |         |      |
|Azure AD| 本地/联机 | Skype for Business/Microsoft 团队|企业语音/混合语音连接/直接路由  |否，必须先在本地广告中创建用户对象 |
|本地广告  |内部部署| Microsoft Teams| 企业语音/混合语音连接/直接路由   |否，本地 Skype for business 不支持 Microsoft 团队客户端 |     
|本地广告  |Online |Skype for Business  | 直接路由  |否，Skype for Business 客户端不支持直接路由，用户必须在 Skype for business 中首先启用企业语音  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>适用于具有 PSTN 的混合环境的可支持性声明

对于所有用户，**必须**在本地广告中创建用户对象，并使用 Azure ad Connect 工具将该对象同步到 Azure ad。 如果在混合配置中直接在 Azure AD 中创建用户对象，则**不支持**为团队/Skype for business 启用用户。 对于要直接为团队启用的新用户（如新员工），用户必须使用本地 Skype for business 管理工具启用 Skype for business。 在**不支持**企业语音的本地池中的情况下，在联机 Skype for Business 或团队中创建用户。 有关此操作的详细信息，请在[Skype for Business 服务器中通过本地 PSTN 连接在 Office 365 中查找计划电话系统](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。
