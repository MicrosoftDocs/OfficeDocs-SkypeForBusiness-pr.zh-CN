---
title: 应答自动助理和呼叫队列呼叫
ms.reviewer: colongma
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理和呼叫队列，并说明如何在Teams中接听这些呼叫。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 595be9303c0d9732c3e2580b06bf3a0a55a27088
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853073"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>直接从 Teams 回答自动助理和呼叫队列

Teams用户可以直接从其Teams客户端接收和接听云自动助理和呼叫队列的呼叫。

## <a name="what-are-auto-attendants-and-call-queues"></a>什么是自动助理和呼叫队列？

云自动助理提供一系列语音提示或音频文件，呼叫者在呼叫组织时听到而不是人工操作员。 自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。

云呼叫队列包括当有人为你的组织拨打电话号码时使用的问候语、自动暂停呼叫的功能，以及搜索下一个可用呼叫代理以在呼叫人员收听音乐时处理呼叫的能力。 可以为组织创建单个或多个呼叫队列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>处理自动助理或呼叫队列呼叫

用户将能够在接听呼叫之前将传入呼叫与自动助理或呼叫队列区分开来。 除了调用方的名称和/或号码，每个调用将包括有关调用方尝试联系谁的信息，为用户提供更好的上下文来寻址调用方。

下图显示了来自自动助理或呼叫队列的传入呼叫将如何显示给用户。

![传入呼叫通知的屏幕截图。](media/answer-auto-attendant-and-call-queue-calls-image1.png)

响应自动助理或呼叫队列呼叫后，用户可以像处理任何其他呼叫一样处理呼叫&#x2014;他们可以在其他用户中添加或会议，或将呼叫转移到另一方。 此外，将根据用户的配置转发自动助理呼叫。

> [!NOTE] 
> 呼叫队列调用不会基于用户的呼叫应答规则配置进行转发。 这是为了确保调用方保留在队列中，直到代理可以接听呼叫，并且调用方不会意外转发。

> 代理不会收到呼叫队列呼叫的任何未接听电话或语音邮件的通知。

## <a name="supported-clients"></a>支持的客户端

以下客户端提供对自动助理和呼叫队列呼叫的支持：

-    Microsoft Teams Windows 客户端 （32 和 64 位版本）
-    Microsoft Teams Mac 客户端
-    Microsoft Teams iPhone 应用
-    Microsoft Teams Android 应用

仅Teams共[存模式支持Teams](/microsoftteams/setting-your-coexistence-and-upgrade-settings)客户端。

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>为Microsoft Teams配置自动助理和呼叫队列支持

若要在Microsoft Teams接收自动助理和呼叫队列呼叫，需要配置互操作性策略和升级策略。 请查看[使用Teams和Skype for Business的组织迁移和互操作性](migration-interop-guidance-for-teams-with-skype.md)。 如果未配置自动助理和/或呼叫队列并想要执行此操作，请参阅 [设置云自动助理](create-a-phone-system-auto-attendant.md) 并 [创建云呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="known-issues"></a>已知问题

当呼叫队列代理在其移动设备上收到呼叫时，如果设备已锁定，呼叫可能会暂停。 用户必须先解锁设备，然后接听呼叫。


## <a name="related-topics"></a>相关主题

[创建云呼叫队列](create-a-phone-system-call-queue.md)

[什么是云自动助理？](what-are-phone-system-auto-attendants.md)

[设置云自动助理](create-a-phone-system-auto-attendant.md)

