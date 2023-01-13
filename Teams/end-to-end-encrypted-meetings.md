---
title: 需要对敏感 Teams 会议进行端到端加密
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 了解如何为 Teams 会议启用端到端加密。
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800144"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>需要对敏感 Teams 会议进行端到端加密

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

端到端加密是在其源头对信息进行加密，在其预期目标处进行解密，中间节点无法解密。 当 Teams 中的会议经过端到端加密时，除会议参与者外，任何人都无法听到或看到通信。 其他任何一方（包括 Microsoft）都无权访问解密的对话。

当双方使用适用于 Windows 或 Mac 的最新版本的 Teams 桌面客户端、在具有 iOS 和 Android 最新更新的移动设备上或使用最新更新的 Windows 设备上的Teams 会议室时，可以在双方之间进行端到端加密会议。 不支持通过浏览器参加的会议进行端到端加密。

> [!Note]
> 端到端会议加密需要Teams 高级版。

如果不启用端到端加密，Teams 仍会根据行业标准使用加密来保护会议。 会议期间交换的数据在传输中和静态时始终是安全的。 有关详细信息，请参阅 [Teams 的媒体加密](teams-security-guide.md#media-encryption)。

在端到端加密会议期间，Teams 保护以下功能：

- 音频

- 视频

- 屏幕共享

[Microsoft 365 中的加密](/microsoft-365/compliance/encryption) 可保护会议中的聊天、文件共享、状态和其他内容。 应用、头像、反应、聊天和 Q&A 未进行端到端加密。

在端到端加密会议期间，以下功能不可用：

- 实时字幕和听录

- 录制

- 一起模式、配套模式、大型库

- 分组讨论室

如果组织使用合规性记录，则端到端加密不可用。 有关 Teams 如何支持合规性录制的详细信息，请参阅[基于 Teams 策略的通话和会议录制简介](teams-recording-policy.md)。

## <a name="enable-end-to-end-encryption-for-meetings"></a>为会议启用端到端加密

默认情况下，不启用会议的端到端加密。 可以使用 Teams 管理员增强加密策略来启用它。

启用端到端加密后，会议组织者可以选择端到端加密，然后创建会议。 还可以使用会议模板或敏感度标签强制实施端到端加密。

为会议启用端到端加密

1. 在 Teams 管理中心，选择“ **增强的加密策略**”。

1. 选择要更新的策略。

1. 将 **“端到端会议加密**”设置为 **“未启用，但用户可以替代**”。

1. 选择“**保存**”。

## <a name="related-topics"></a>相关主题

[使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md)

[将端到端加密用于一对一 Microsoft Teams 通话](teams-end-to-end-encryption.md)
