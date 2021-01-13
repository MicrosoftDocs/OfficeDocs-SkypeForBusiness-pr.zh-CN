---
title: 在 Skype for Business 中查看 PSTN 用法记录
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：了解如何使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看 PSTN 用法记录。
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830532"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>在 Skype for Business 中查看 PSTN 用法记录

**摘要：** 了解如何使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看 PSTN 用法记录。

公用电话交换网 (PSTN) 用法记录指定呼叫 (的一类，例如内部、本地或长途) ，该呼叫类型由组织的各个用户或用户组进行。 有关详细信息，请参阅规划 [文档中的 PSTN](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) 用法记录。

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板查看 PSTN 用法记录

1. 打开 Skype for Business Server 控制面板。

2. 在左侧导航栏中，单击 **"语音路由**"，然后单击 **"PSTN 用法"。**

3. 在 **"PSTN** 用法"页上，突出显示要查看的 PSTN 用法记录，单击"编辑"，然后单击"**显示详细信息"。**

    > [!NOTE]
    > 所选 PSTN 用法记录的只读页面显示关联的路由和关联的语音策略。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用 Skype for Business Server 命令行管理程序 cmdlet 查看 PSTN 用法信息

- 若要查看有关所有 PSTN 用法的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：

  ```powershell
  Get-CsPstnUsage
  ```

    此命令会返回类似下列信息：

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>另请参阅

[在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录](voice-policy-and-pstn-usage-records.md)

