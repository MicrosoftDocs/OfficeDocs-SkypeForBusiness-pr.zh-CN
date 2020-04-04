---
title: 应答自动助理和呼叫队列呼叫
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理和通话队列，并介绍如何在团队中回答这些呼叫。
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
ms.openlocfilehash: d630ea41915cb89013e407a6fa0b1cc21cb21abf
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137432"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>直接从 Teams 回答自动助理和呼叫队列
===========================================================

团队用户可以直接从其团队客户端接收和应答来自云自动助理的调用和调用队列。 对于团队用户，"自动助理" 功能现在通常可用，并且呼叫队列功能位于 "预览" 中。 

## <a name="what-are-auto-attendants-and-call-queues"></a>什么是自动助理和呼叫队列？

云自动助理提供一系列语音提示或音频文件，当呼叫者呼叫组织时，呼叫者将听到该提示，而不是人工操作员。 自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。

云呼叫队列包括当某人拨入到您的组织的电话号码时使用的问候语、自动将呼叫置于保持状态的功能，以及搜索下一个可用的呼叫代理以处理呼叫的功能，同时呼叫正在收听音乐的用户。 您可以为您的组织创建单个或多个通话队列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>处理自动助理或呼叫队列呼叫

用户在应答呼叫之前，将能够在自动助理或呼叫队列中区分来电。 除了呼叫者的姓名和/或号码，每个调用都将包含有关呼叫者试图访问的人员的信息，从而为用户提供了更好的解决呼叫者的上下文。

下图显示了来自自动助理或呼叫队列的传入呼叫如何显示给用户。

![传入呼叫通知的屏幕截图](media/answer-auto-attendant-and-call-queue-calls-image1.png)

应答自动助理或呼叫队列呼叫后，用户可以像处理任何其他呼叫一样处理呼叫，&#x2014; 他们可以在其他用户中添加或加入会议，或者将呼叫转接到另一方。 此外，将根据用户的配置转发自动助理呼叫。

> [!NOTE] 
> 呼叫队列呼叫不会根据用户的配置转发。 这是为了确保呼叫者保留在队列中，直到工程师可以接听呼叫且呼叫者不会被意外转发。

## <a name="supported-clients"></a>支持的客户端

自动助理和呼叫队列呼叫支持在以下客户端中可用：

-    Microsoft Teams Windows 客户端 （32 和 64 位版本）
-    Microsoft Teams Mac 客户端
-    Microsoft Teams iPhone 应用
-    Microsoft Teams Android 应用

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>为 Microsoft 团队配置自动助理和呼叫队列支持

若要在 Microsoft 团队中接收自动助理和呼叫队列呼叫，需要配置你的互操作性策略和升级策略。 请查看[与 Skype For business 一起使用团队的组织的迁移和互操作性](migration-interop-guidance-for-teams-with-skype.md)。 如果您没有配置自动助理和/或呼叫队列，请参阅[设置云自动助理](create-a-phone-system-auto-attendant.md)和[创建云呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="related-topics"></a>相关主题

-    [什么是 Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
-    [创建云呼叫队列](create-a-phone-system-call-queue.md)
-    [什么是云自动助理？](what-are-phone-system-auto-attendants.md)
-    [设置云自动助理](create-a-phone-system-auto-attendant.md)

