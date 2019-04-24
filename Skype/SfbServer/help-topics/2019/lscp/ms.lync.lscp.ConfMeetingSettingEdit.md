---
title: 会议配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 会议配置设置中定义的用户安排的会议的用户加入体验。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的立即开会选项创建的临时会议。
ms.openlocfilehash: cc997e2ed523ad958c08325112dc661c5a56e6ca
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216149"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>会议配置：创建新的或编辑现有的

会议配置设置可定义用户预定会议的用户加入体验。这些设置只适用于预定的会议，不适用于通过单击客户端中的“**现在开会**”选项创建的临时会议。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **范围**标识您正在创建或修改的会议配置的范围： 全局、 站点或池。

- **名称**会议配置已命名默认情况下，且不能更改名称。

- **PSTN 呼叫者绕过大厅**选中此复选框，以自动向会议通过公用电话交换网 (pstn) 电话线路允许拨入的用户。 清除，直到会议演示者授予其加入会议的访问权限，它们位于保留路由 PSTN 呼叫者到会议会议厅，此复选框。

- **指定为演示者**选择当用户加入会议时自动指定为演示者 （除了会议组织者） 用户的类别。 此设置，无论演示者可以将明确指定为演示者，计划会议或他们可以显式提升为演示者在会议过程时。 选项如下：

  - **无**如果组织者以外任何人自动指定为演示者，请选择此选项。

  - **公司**选择此选项可自动将只有您的组织的成员指定为演示者。

  - **所有人**选择此选项可自动指定任何人成为演示者。

- **默认情况下已分配会议类型**是否 Outlook 会议外接程序始终安排会议使用组织者的分配会议此设置控制，这意味着始终安排会议具有相同的联接 URL 和音频信息。 选中此复选框具有始终使用相同的 URL 加入安排的会议。 清除此复选框，每个会议都使用不同的联接 URL。

- **默认情况下 Admit 匿名用户**选中此复选框如果匿名 （即，未经身份验证） 允许用户默认情况下参加会议。 如果匿名用户不允许参加会议默认情况下，请清除此复选框。

- **徽标 URL**键入要用于自定义会议邀请的图像的 URL。

- **帮助 URL**键入用户可从中获得加入会议的网站的 URL。

- **法律文本 URL**键入的法律信息的网站的 URL 和会议免责声明。

- **自定义页脚文本**键入要在自定义会议邀请中使用的文本。

有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)。有关设置大型会议的会议配置的详细信息，请参阅规划文档中的[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)。


