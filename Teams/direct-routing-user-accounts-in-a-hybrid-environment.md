---
title: 使用 PSTN 的混合环境中的用户帐户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解用户创建的不同组合以及支持或不支持的组合。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676414"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>采用 PSTN 连接的混合环境中的用户帐户

## <a name="about-the-environment"></a>关于环境

本文适用于具有以下所有内容的环境：

- Skype for Business Server或 Lync Server 2013
- Microsoft 365或Office 365组织
- 在 Skype for Business Server 和 Skype for Business Online 或 Microsoft Teams 租户之间配置的混合连接
- 启用并接收公共交换电话网络 (PSTN 的用户) 客户端和客户端的呼叫


如果具有不同的环境 (（例如Skype for Business 云连接器版本) 、未配置混合或未为用户启用 PSTN 调用，则可支持性矩阵将有所不同。

## <a name="about-the-combinations-and-the-supportability-statement"></a>关于组合和可支持性声明

具有 PSTN 连接的Skype for Business混合环境提供了有关提供用户服务的位置以及如何预配和管理用户帐户的灵活性。 但是，大量的选项可能会创建一些不受支持的组合。 本部分介绍用户创建的不同组合，后跟可支持性语句。

**定义：**

- **企业语音：** 为具有本地Skype for Business用户帐户的用户提供对 PSTN 的访问权限的选项。 本地Skype for Business中介服务器提供与 PSTN 的互连。
- **混合语音连接：** 为具有 Skype for Business Online 帐户的用户提供对 PSTN 的访问权限的选项。 本地Skype for Business中介服务器提供与 PSTN 的互连。
- **直接路由：** 使用Microsoft Teams客户端为具有联机Skype for Business帐户、Microsoft Teams许可证的用户提供对 PSTN 的访问权限的选项。 SBC 在 Microsoft 365 或 Office 365 中连接到 SIP 代理，而无需 Microsoft 提供任何本地软件。

**环境支持以下组合：**

- **方案 1：** 本地Skype for Business中的用户帐户，并将Skype for Business客户端与企业语音
- **方案 2：** 联机业务Skype中的用户帐户，并将Skype for Business客户端与混合语音连接配合使用
- **方案 3：** 使用Microsoft Teams许可证联机Skype for Business用户帐户，并将使用Teams客户端

### <a name="supportability-matrix"></a>可支持性矩阵

|在其中创建的用户对象|用户的Skype for Business服务提供程序|用户的客户端|语音选项|支持|
|---|---|---|---|---|
|本地 AD|内部部署|Skype for Business|企业语音|是|
|本地 AD|Online|Skype for Business|混合语音连接|是|
|本地 AD|Online|Microsoft Teams|直接路由|是|
|**不支持的组合**|||||
|Azure AD|本地/联机|Skype for Business/Microsoft Teams|企业语音/混合语音连接/直接路由|否，必须先在本地 AD 中创建用户对象|
|本地 AD|内部部署|Microsoft Teams|企业语音/混合语音连接/直接路由|否，本地Skype for Business不支持Microsoft Teams客户端|
|本地 AD|Online|Skype for Business|直接路由|否，Skype for Business客户端不支持直接路由|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>使用 PSTN 的混合环境的支持性语句

对于所有用户，**必须在** 本地 AD 中创建用户对象，并使用 Azure AD 连接 工具同步到 Azure AD。 如果直接在混合配置中的 Azure AD 中创建用户对象，**则不支持** 为用户启用Teams/Skype for Business。 对于将直接为Teams启用的新用户（例如新员工），必须为用户启用Skype for Business使用本地Skype for Business管理工具。 **不支持** 在不首先在具有企业语音的本地池中启用用户的情况下，在联机Skype for Business或Teams中创建用户。 有关详细信息，请参阅 Skype for Business Server 中具有[本地 PSTN 连接的计划电话系统](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。
