---
title: 客户端版本规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。
ms.openlocfilehash: 497b11e2d25abbaade29a040ef5d5e834ab3ccb2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691587"
---
# <a name="client-version-rule"></a>客户端版本规则

客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建客户端版本配置**”或“**编辑客户端版本配置**”页上执行以下任务：

- 向客户端版本策略添加新规则。

- 修改构成现有客户端版本策略的规则

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **用户代理**可以从列表中选择一种客户端类型。 下表定义了用户代理代码。 此列表包含旧客户端类型，其中一些不再受支持。

|**客户端名称**|**用户代理**|
|:-----|:-----|
|Lync 2013、Lync 2010、Office Communicator  <br/> |OC  <br/> |
|Lync Web App、Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition、Office Communicator Phone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition 平台  <br/> |CPE  <br/> |
|统一通信平台  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting 外接程序  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|实时通信客户端  <br/> |RTC  <br/> |
|Lync 2010 for iPad  <br/> |iPadLync  <br/> |
|Lync 2010 for iPhone  <br/> |iPhoneLync  <br/> |
|适用于 Windows Phone 的 Lync 2010  <br/> |WPLync  <br/> |
|适用于 Nokia 的 Lync 2010  <br/> |NokiaLync  <br/> |
|适用于 Android 的 Lync 2010  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **版本号**你可以指定以下字段的版本号，或使用通配符指示客户端版本号。

  - **主要版本**指定与客户端的主版本相对应的数字。

  - **次要版本**指定与客户端的次要版本相对应的数字。

  - **内部版本**指定与客户端的主要和次要版本相对应的版本号。

  - **更新**指定与客户端更新版本对应的数字。

- **比较操作**你可以为你在前面的步骤中指定的客户端版本指定匹配操作。 以下操作可用：

  - **相同**

  - **不是**

  - **更高**

  - **更高或相同**

  - **更低**

  - **更低或相同**

- **操作**你可以指定在满足前面步骤中的条件时要执行的操作。 以下操作可用：

  - **允许**允许客户端登录。

  - **允许和升级**允许客户端登录并接收来自 Windows Server 更新服务或 Microsoft Update 的更新。 仅当选择了 "用户代理**OC** " 时，此操作才可用。

    > [!NOTE]
    > 选择此操作会导致在用户下次登录 Skype for Business 时显示通知。 该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。 为了避免混淆，您只应在更新可用后选择此操作。

  - **允许 URL**允许客户端登录，并显示有关从何处下载另一个客户端版本的消息。 可以在“**URL**”字段中指定 URL。

  - **阻止**阻止客户端登录。

  - **阻止和升级**阻止客户端登录，并允许客户从 Windows Server 更新服务或 Microsoft 更新接收更新。 仅当选择了 "用户代理**OC** " 时，此操作才可用。

  - **使用 URL 阻止**   阻止客户端登录并显示有关下载其他客户端版本的位置的消息。可以在“**URL**”字段中指定 URL。

有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[客户端互操作](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。 有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。

