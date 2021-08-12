---
title: 应答自动助理和呼叫队列呼叫
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理和呼叫队列，并说明如何在 Teams。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b9510b3e7c31005c2ec75d6358c1f911daba752298b726e960bf38c63e11e4e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314258"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>直接从 Teams 回答自动助理和呼叫队列

Teams用户可以直接从云自动助理接收和接听来自云自动助理的呼叫，并直接从其Teams呼叫队列。

## <a name="what-are-auto-attendants-and-call-queues"></a>什么是自动助理和呼叫队列？

云自动助理提供一系列语音提示或音频文件，呼叫者在呼叫组织时可以听到这些提示或音频文件，而不是人工接线员。 自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。

云呼叫队列包括当某人呼叫组织的电话号码时使用的问候语、自动将呼叫置于保持状态的能力，以及搜索下一个可用的呼叫代理以在呼叫者收听保持音乐时处理呼叫的能力。 你可以为组织创建单个或多个呼叫队列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>处理自动助理或呼叫队列呼叫

用户在接听呼叫之前，能够区分来自自动助理或呼叫队列的传入呼叫。 除了呼叫者的姓名和/或号码外，每个呼叫都将包含有关呼叫者尝试联系的用户的信息，为用户提供了一个更好的上下文来向呼叫者进行寻址。

下图显示了来自自动助理或呼叫队列的传入呼叫如何向用户显示。

![传入呼叫通知的屏幕截图](media/answer-auto-attendant-and-call-queue-calls-image1.png)

应答自动助理或呼叫队列呼叫后，用户可以像处理任何其他呼叫一样处理呼叫&#x2014;他们可在其他用户中添加或会议，或者将呼叫转接到另一方。 此外，自动助理呼叫将基于用户的配置进行转发。

> [!NOTE] 
> 不会根据用户的配置转发呼叫队列调用。 这是为了确保调用方保留在队列中，直到代理可以应答呼叫并且调用方不会意外转发。

> 对于呼叫队列呼叫，代理不会收到任何错过的呼叫或语音邮件的通知。

## <a name="supported-clients"></a>支持的客户端

以下客户端支持自动助理和呼叫队列呼叫：

-    Microsoft Teams Windows 客户端 （32 和 64 位版本）
-    Microsoft Teams Mac 客户端
-    Microsoft Teams iPhone 应用
-    Microsoft Teams Android 应用

只有 Teams 共存模式才支持 Teams[客户端](/microsoftteams/setting-your-coexistence-and-upgrade-settings)。

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>为呼叫配置自动助理和呼叫队列Microsoft Teams

若要在客户端上接收自动助理Microsoft Teams呼叫队列呼叫，需要配置互操作性策略和升级策略。 请查看将 Teams 与 Skype for Business[一起用于组织的迁移和Skype for Business。](migration-interop-guidance-for-teams-with-skype.md) 如果没有配置自动助理和/或呼叫队列，并且希望这样做，请参阅设置云自动[助理和](create-a-phone-system-auto-attendant.md)[创建云呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="known-issues"></a>已知问题

当呼叫队列代理在移动设备上收到呼叫时，如果设备已锁定，呼叫可能会保持。 用户必须先解锁设备，然后接听呼叫。


## <a name="related-topics"></a>相关主题

-    [电话系统或Microsoft 365中Office 365](what-is-phone-system-in-office-365.md)
-    [创建云呼叫队列](create-a-phone-system-call-queue.md)
-    [什么是云自动助理？](what-are-phone-system-auto-attendants.md)
-    [设置云自动助理](create-a-phone-system-auto-attendant.md)

