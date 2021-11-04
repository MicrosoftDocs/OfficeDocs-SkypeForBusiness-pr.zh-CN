---
title: 查看 PSTN 用法记录Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：了解如何使用命令行管理程序或命令行管理程序Skype for Business Server PSTN 用法Skype for Business Server记录。
ms.openlocfilehash: 2b09ed19de6ff205ee7d76e7379c8b4c5fc12d06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771517"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>查看 PSTN 用法记录Skype for Business

**摘要：** 了解如何使用命令行管理程序或命令行管理程序Skype for Business Server PSTN 用法Skype for Business Server记录。

公用电话交换网 (PSTN) 用法记录指定组织中各种用户或用户组可以拨打的呼叫 (类，如内部、本地或长途) 。 有关详细信息，请参阅规划 [文档中的 PSTN](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) Usage Records。

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>使用控制面板查看 PSTN Skype for Business Server记录

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击"**语音路由"，** 然后单击 **"PSTN 用法"。**

3. 在 **"PSTN 用法"** 页上，突出显示要查看的 PSTN 用法记录，单击"编辑 **"，然后单击**"显示 **详细信息"。**

    > [!NOTE]
    > 所选 PSTN 用法记录的只读页面显示关联的路由和关联的语音策略。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用命令行管理程序 cmdlet 查看 PSTN Skype for Business Server信息

- 若要查看有关所有 PSTN 用法的信息，请在命令行管理程序中键入Skype for Business Server命令，然后按 Enter：

  ```powershell
  Get-CsPstnUsage
  ```

    此命令会返回类似下列信息：

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>另请参阅

[创建或修改语音策略，并配置 PSTN 用法Skype for Business](voice-policy-and-pstn-usage-records.md)