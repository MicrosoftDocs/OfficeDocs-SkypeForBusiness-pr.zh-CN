---
title: 会议配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 会议配置设置定义用户安排的会议的用户加入体验。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的"现在开会"选项创建临时会议。
ms.openlocfilehash: 87d07100e7f9411f139711de3302ce384e71cb01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824812"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>会议配置：创建新的或编辑现有的

会议配置设置定义用户安排的会议的用户加入体验。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的"现在开会"选项创建临时会议。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **范围** 标识要创建或修改的会议配置的范围：全局、站点或池。

- **名称** 默认情况下会命名会议配置，并且无法更改名称。

- **PSTN 呼叫者绕过大厅** 选中此复选框可自动允许使用 PSTN 电话线路通过公用电话交换网 (拨入) 会议。 清除此复选框以将 PSTN 呼叫者路由到会议厅，在会议演示者授予他们参加会议的访问权限之前，这些呼叫者将一直等待。

- **指定为演示者** 选择除会议 (组织者) 加入会议时自动指定为演示者的用户类别。 无论此设置如何，都可以在安排会议时明确将演示者指定为演示者，或者可以在会议期间将演示者显式提升为演示者。 选项包括：

  - **无** 如果没有自动将组织者指定为演示者，请选择此选项。

  - **Company** 选择此选项可自动仅将组织成员指定为演示者。

  - **所有人** 选择此选项可自动指定任何人为演示者。

- **默认情况下分配的会议类型** 此设置控制 Outlook 会议外接程序是否始终使用组织者分配的会议安排会议，这意味着安排的会议始终具有相同的加入 URL 和音频信息。 选中此复选框，计划的会议始终使用相同的加入 URL。 清除此复选框以针对每个会议使用不同的加入 URL。

- **默认情况下允许匿名用户** 如果默认情况下允许匿名 (，即未经身份验证) 用户参加会议，请选中此复选框。 如果默认情况下不允许匿名用户参加会议，请清除此复选框。

- **徽标 URL** 键入包含要用于自定义会议邀请的图像的 URL。

- **帮助 URL** 键入网站 URL，用户可在该网站中获取有关加入会议的帮助。

- **法律文本 URL** 键入具有会议法律信息和免责声明的网站的 URL。

- **自定义页脚文本** 键入要用于自定义会议邀请的文本。

有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)。 有关设置大型会议的会议配置的详细信息，请参阅规划文档中的[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)。


