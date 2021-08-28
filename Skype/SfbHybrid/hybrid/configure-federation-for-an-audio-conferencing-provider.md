---
title: 在混合部署中为音频会议提供商配置联盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。
ms.openlocfilehash: 25bd691186d5d37dc272b420e68bb71a7d181de1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597886"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>在混合部署中为音频会议提供商配置联盟

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**摘要：** 了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。

如果你希望将音频会议提供商 (ACP) 用于具有联机) 的混合部署 (，则需要将本地部署和 ACP 合作伙伴之间的联盟配置为允许的合作伙伴服务器。 您可以通过添加 ACP 合作伙伴域和边缘服务器来配置联盟 (这也称为访问代理) 到本地部署的联盟域列表。 然后，您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联合域列表中。 有关其他详细信息，请与 ACP 提供商联系。 然后，您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联合域列表中。

- **将 ACP 域和边缘服务器添加为允许的联合域**

    若要将 ACP 域添加为允许的合作伙伴服务器 (联盟域) ，请按照配置对允许的外部域的支持 [中的步骤操作](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)。 对于边缘服务器，添加 ACP 合作伙伴的边缘服务器的 FQDN。 您可能需要与 ACP 合作伙伴联系，以获取其边缘服务器的 FQDN，ACP 也可能将 FQDN 称为其访问代理。

- **向 ACP 合作伙伴提供边缘服务器池的 FQDN**

    ACP 合作伙伴需要配置联盟，通过将边缘服务器池的 FQDN 添加为允许的联合域，将本地域添加为允许的合作伙伴服务器。