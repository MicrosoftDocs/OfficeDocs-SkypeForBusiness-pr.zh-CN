---
title: 会议配置新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 会议配置设置为用户计划的会议定义用户加入体验。 这些设置仅适用于计划的会议。 它们不适用于通过单击客户端中的 "立即开会" 选项创建的临时会议。
ms.openlocfilehash: 002550fadb845a15178567a62ad3189df7d652ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300208"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>会议配置：创建新的或编辑现有的

会议配置设置可定义用户预定会议的用户加入体验。这些设置只适用于预定的会议，不适用于通过单击客户端中的“**现在开会**”选项创建的临时会议。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **范围**标识要创建或修改的会议配置的范围: 全局、网站或池。

- **名称**会议配置默认命名, 无法更改名称。

- **PSTN 呼叫者绕过大厅**选中此复选框以自动允许通过公共交换电话网络 (PSTN) 电话线路拨入会议的用户。 清除此复选框可将 PSTN 呼叫者路由到会议厅, 在会议演示者授予他们访问会议的权限之前, 这些呼叫者将处于暂停状态。

- **指定为演示者**选择在加入会议时自动指定为演示者的用户的类别 (会议组织者除外)。 无论此设置如何, 在安排会议时, 演示者都可以显式指定为演示者, 也可以在会议期间将其显式提升为演示者。 选项包括:

  - **无**如果不是组织者的任何人自动指定为演示者, 请选择此选项。

  - **公司**选择此选项可自动将组织的成员指定为演示者。

  - **所有人**选择此选项可自动将任何人指定为演示者。

- **默认为分配的会议类型**此设置控制 Outlook 会议加载项是否始终使用组织者分配的会议安排会议, 这意味着计划的会议始终具有相同的联接 URL 和音频信息。 选中此复选框以让计划的会议始终使用相同的联接 URL。 清除此复选框可对每个会议使用不同的联接 URL。

- **默认情况下, 承认匿名用户**如果在默认情况下允许匿名用户 (即未经身份验证的) 用户出席会议, 请选中此复选框。 如果默认情况下不允许匿名用户出席会议, 请清除此复选框。

- **徽标 URL**键入包含要用于自定义会议邀请的图像的 URL。

- **帮助 URL**键入用户可在其中获取加入会议的帮助的网站的 URL。

- **合法文本 URL**键入包含该会议的法律信息和免责声明的网站的 URL。

- **自定义页脚文本**键入要在自定义会议邀请中使用的文本。

有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)。有关设置大型会议的会议配置的详细信息，请参阅规划文档中的[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)。


