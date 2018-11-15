---
title: 应答自动助理并直接从团队呼叫队列呼叫
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: 介绍电话系统自动助理和呼叫的队列，并说明如何可以应答团队中的这些呼叫。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b0b533020def2e344991fa758304888c8166436
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530943"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>应答自动助理并直接从团队呼叫队列呼叫
===========================================================

团队用户可接收并从业务 online Skype 应答呼叫自动助理，并直接从其团队客户端调用队列。 团队用户自动助理功能现已可用，并调用队列功能处于预览。 

## <a name="what-are-auto-attendants-and-call-queues"></a>什么是自动助理，并调用队列？

电话系统自动助理提供了一系列语音提示或组织到呼叫时，呼叫者听到而不是人工接线员音频文件。 自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。

队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。 您可以为组织创建单个或多个呼叫的队列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>处理的自动助理或呼叫队列呼叫

用户将能够它们应答呼叫之前区分传入呼叫自动助理或呼叫的队列。 名称和/或将呼叫者数量，以及每个呼叫将包含有关谁将呼叫者尝试通，为用户提供了更好的上下文，解决呼叫者的信息。

下图显示来自自动助理或呼叫队列的传入呼叫到用户的显示方式。

![传入呼叫通知](media/answer-auto-attendant-and-call-queue-calls-image1.png)

一旦应答自动助理或呼叫队列呼叫时，用户可以处理像其他呼叫和 #x 2014; 呼叫他们可以添加或另一个用户或转接到另一方呼叫中的会议。 此外，自动助理将呼叫转接基于用户的配置。

> [!NOTE] 
> 调用基于用户的配置不转接呼叫的队列。 这是为了确保代理可以应答呼叫之前，呼叫者保持队列中没有意外转接呼叫者。

## <a name="supported-clients"></a>支持的客户端

对于自动助理和呼叫队列呼叫支持以下客户端有：

-   Microsoft Teams Windows 客户端 （32 和 64 位版本）
-   Microsoft Teams Mac 客户端
-   Microsoft Teams iPhone 应用
-   Microsoft Teams Android 应用

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>配置支持的 Microsoft 团队的自动助理和呼叫队列

若要接收自动助理和上的 Microsoft 团队呼叫队列呼叫，您需要配置您的互操作性策略和升级策略。 请查看[迁移和组织使用团队一起 for Business 的 Skype 的互操作性](migration-interop-guidance-for-teams-with-skype.md)。 如果您没有自动助理和/或呼叫队列配置，并且想要这样做，请参阅[设置电话系统自动助理](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)和[创建电话系统呼叫队列](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

## <a name="related-topics"></a>相关主题

-   [什么是 Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
-   [创建电话系统呼叫队列](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [什么是电话系统自动助理？](what-are-phone-system-auto-attendants.md)
-   [设置电话系统自动助理](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

