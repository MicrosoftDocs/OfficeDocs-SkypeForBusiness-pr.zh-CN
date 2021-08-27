---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 将拨入访问号码迁移到 Skype for Business Server 2019 需要运行 Move-CsApplicationEndpoint cmdlet 来迁移联系对象。 在旧安装和 Skype for Business Server 2019 共存期间，在 Skype for Business Server 2019 中创建的拨入访问号码的行为类似于在旧版安装中创建的拨入访问号码，如本节所述。
ms.openlocfilehash: 4d5d0ad88c241685e7ea86c7adc9dc536d3180a8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589332"
---
# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

将拨入访问号码迁移到 Skype for Business Server 2019 需要运行 **Move-CsApplicationEndpoint** cmdlet 来迁移联系人对象。 在旧安装和 Skype for Business Server 2019 共存期间，在 Skype for Business Server 2019 中创建的拨入访问号码的行为类似于在旧版安装中创建的拨入访问号码，如本节所述。 

在旧版安装中创建但移动到 Skype for Business Server 2019 或在迁移之前、迁移期间或之后在 Skype for Business Server 2019 中创建的拨入访问号码具有以下特征：

- Communications Server 2007 R2 Office邀请和拨入访问号码页面上不显示。

- 显示在旧版安装会议邀请和拨入访问号码页面上。

- 显示在 Skype for Business Server 2019 会议邀请和拨入访问号码页面上。

- 无法在 Communications Server 2007 R2 Office中查看或修改。

- 可以在旧版安装控制面板和旧版安装命令行管理程序中查看和修改。

- 可以在 Skype for Business Server 2019 控制面板和 Skype for Business Server 2019 命令行管理程序 中查看和修改。

- 可以使用带 Priority 参数的 Set-CsDialinConferencingAccessNumber cmdlet 在区域内重新排序。

在停用旧安装池之前，必须完成指向旧安装池的拨入访问号码的迁移。 如果未按照以下过程所述完成拨入访问号码迁移，则对访问号码的传入呼叫将失败。

> [!IMPORTANT]
> 在停用旧安装池之前，必须执行此过程。 

> [!NOTE]
> 建议在网络使用率较低时移动拨入访问号码，以防服务中断时间短。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>标识和移动拨入访问号码

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Microsoft Skype for Business Server 2019"，** 然后单击"Skype for Business Server **命令行管理程序"。** 

2. 若要将每个拨入访问号码移动到 Skype for Business Server 2019 上托管的池，请从命令行运行： 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 打开Skype for Business Server控制面板"。

4. 在左侧导航栏中，单击“会议”。

5. 单击" **拨入访问号码"** 选项卡。 

6. 确认要迁移的旧安装池没有保留拨入访问号码。

    > [!NOTE]
    > 当所有拨入访问号码都指向 Skype for Business Server 2019 池时，您可以停用旧安装池。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>使用控制面板验证拨入访问号码Skype for Business Server迁移

1. 从分配给 **CsUserAdministrator** 角色或 **CsAdministrator** 角色的用户帐户，登录到内部部署中的任意计算机。 

2. 打开Skype for Business Server控制面板"。

3. 在左侧导航栏中，单击“会议”。

4. 单击" **拨入访问号码"** 选项卡。 

5. 验证所有拨入访问号码是否都迁移到 2019 年 10 月Skype for Business Server池。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>使用命令行管理程序验证拨入访问号码Skype for Business Server迁移

1. 打开 Skype for Business Server 命令行管理程序。

2. 要返回迁移的所有电话拨入式会议访问号码，请从命令行运行：

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 验证所有拨入访问号码是否都迁移到 2019 年 10 月Skype for Business Server池。


