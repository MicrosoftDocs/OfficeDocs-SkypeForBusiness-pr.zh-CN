---
title: 客户端版本规则
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。
ms.openlocfilehash: 44f47f0281d03e63a87ce0e56ecfa1c77c516f27
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597176"
---
# <a name="client-version-rule"></a>客户端版本规则

客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“新建客户端版本配置”或“编辑客户端版本配置”页上执行以下任务：

- 向客户端版本策略添加新规则。

- 修改构成现有客户端版本策略的规则

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **用户代理** 可以从列表中选择客户端类型。 下表定义了用户代理代码。 此列表包括旧版客户端类型，其中一些类型不再受支持。

|**客户端名称**|**用户代理**|
|:-----|:-----|
|Lync 2013、Lync 2010、Office Communicator  <br/> |OC  <br/> |
|Lync Web App，Communicator Web Access  <br/> |CWA  <br/> |
|Lync 电话 Edition，Office Communicator 电话  <br/> |OCPhone  <br/> |
|Communicator Phone Edition 平台  <br/> |CPE  <br/> |
|统一通信平台  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting 外接程序  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|WindowsMessenger  <br/> |WM  <br/> |
|实时通信客户端  <br/> |RTC  <br/> |
|Lync 2010 for iPad  <br/> |iPadLync  <br/> |
|Lync 2010 for iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 for Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 for Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 for Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **版本号** 可以指定以下字段的版本号，或使用通配符指示客户端版本号。

  - **主要版本** 指定与客户端的主要版本对应的数字。

  - **次要版本** 指定与客户端次要版本对应的数字。

  - **内部版本** 指定与客户端的主要版本和次要版本对应的内部版本号。

  - **更新** 指定与客户端的更新版本相对应的数量。

- **比较操作** 您可以指定前面步骤中指定的客户端版本的匹配操作。 可以使用以下操作：

  - **相同**

  - **不是**

  - **更高**

  - **更高或相同**

  - **更低**

  - **更低或相同**

- **操作** 可以指定在满足前面步骤中的条件时要执行的操作。 可以使用以下操作：

  - **允许** 允许客户端登录。

  - **允许和升级** 允许客户端登录并接收来自 Windows Server Update Service 或 Microsoft Update 的更新。 仅当选中用户代理“OC”时，才能进行此操作。

    > [!NOTE]
    > 选择此操作将导致用户在下次登录时显示Skype for Business。 该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。 为了避免混淆，您只应在更新可用后选择此操作。

  - **允许使用 URL** 允许客户端登录并显示有关下载其他客户端版本位置的消息。 可以在“URL”字段中指定 URL。

  - **阻止** 阻止客户端登录。

  - **阻止和升级** 阻止客户端登录并允许客户端接收来自 Windows Update Service 或 Microsoft Update 的更新。 仅当选中用户代理“OC”时，才能进行此操作。

  - **使用 URL 阻止**   阻止客户端登录并显示有关下载其他客户端版本的位置的消息。可以在“URL”字段中指定 URL。

有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的 Client [Interoperability。](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)。