---
title: 在混合部署中为音频会议提供商配置联盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '摘要: 了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160440"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>在混合部署中为音频会议提供商配置联盟

**摘要:** 了解如何在 Skype for Business Online 中为音频会议提供商配置联盟。

如果要在混合部署中使用音频会议提供商 (ACP) (本地和联机), 您需要在本地部署和 ACP 合作伙伴之间配置联盟, 作为允许的合作伙伴服务器。 您可以通过将 ACP 合作伙伴域和边缘服务器 (也称为 "访问代理服务器") 添加到本地部署的 "联盟域" 列表中来配置联盟。 然后, 您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。 有关其他详细信息, 请与您的 ACP 提供商联系。 然后, 您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。

- **将 ACP 域和边缘服务器添加为允许的联盟域**

    若要将 ACP 域添加为允许的合作伙伴服务器 (允许的联盟域), 请按照[Configure Support for An External](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)domain 中的步骤操作。 对于边缘服务器, 添加 ACP 合作伙伴的边缘服务器的 FQDN。 您可能需要与您的 ACP 合作伙伴联系, 以获取其边缘服务器的 FQDN, 而您的 ACP 也可能将其称为访问代理。

- **向 ACP 合作伙伴提供您的边缘服务器池的 FQDN**

    ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加为允许的联盟域, 从而配置联合以将您的本地域作为允许的合作伙伴服务器添加。


