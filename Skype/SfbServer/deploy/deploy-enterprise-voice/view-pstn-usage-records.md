---
title: 查看 Skype for Business 中的 PSTN 使用记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：了解如何使用 Skype for business 服务器控制面板或 Skype for business Server 命令行管理程序查看 PSTN 使用情况记录。
ms.openlocfilehash: 96a96898bf728b4f05ba473bc750635e41be19fa
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002722"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>查看 Skype for Business 中的 PSTN 使用记录

**摘要：** 了解如何使用 Skype for business 服务器控制面板或 Skype for business Server 命令行管理程序查看 PSTN 使用情况记录。

公用电话交换网 (PSTN) 用法记录指定组织中各个用户或用户组所能发出的呼叫类别（如内部、本地或长途）。有关详细信息，请参阅规划文档中的 [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)。

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板查看 PSTN 使用记录

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“语音路由”****，然后单击“PSTN 用法”****。

3. 在“PSTN 用法”**** 页上，突出显示要查看的 PSTN 用法记录，单击“编辑”****，然后单击“显示详细信息”****。

    > [!NOTE]
    > 所选 PSTN 用法记录的只读页面会显示关联的路由和关联的语音策略。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用 Skype for Business Server Management Shell cmdlet 查看 PSTN 使用信息

- 若要查看有关所有 PSTN 用法的信息，请在 Skype for Business Server 命令行管理程序中键入以下命令，然后按 ENTER：

  ```powershell
  Get-CsPstnUsage
  ```

    此命令会返回类似下列信息：

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>另请参阅

[在 Skype for Business 中创建或修改语音策略和配置 PSTN 使用记录](voice-policy-and-pstn-usage-records.md)

