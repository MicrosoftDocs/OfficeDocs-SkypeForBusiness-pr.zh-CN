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
localization_priority: Normal
description: 将拨入访问号码迁移到 Skype for business Server 2019 需要运行 CsApplicationEndpoint cmdlet 来迁移 contact 对象。 在旧版安装和 Skype for business Server 2019 共存期间，您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧版安装中创建的拨入访问号码类似，如本节中所述。
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752694"
---
# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

将拨入访问号码迁移到 Skype for business Server 2019 需要运行**CsApplicationEndpoint** cmdlet 来迁移 contact 对象。 在旧版安装和 Skype for business Server 2019 共存期间，您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧版安装中创建的拨入访问号码类似，如本节中所述。 

您在旧版安装中创建但移动到 Skype for business Server 2019 的拨入访问号码，或者在迁移过程中、迁移过程中或迁移之后，您在 Skype for business Server 2019 中创建的号码具有以下特征：

- 不会出现在 Office 通信服务器 2007 R2 会议邀请和 "拨入访问号码" 页上。

- 显示在旧版 "安装会议邀请" 和 "拨入访问号码" 页上。

- 出现在 Skype for Business Server 2019 会议邀请和 "拨入访问号码" 页上。

- 无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。

- 可以在旧版安装控制面板和旧版安装命令行管理程序中进行查看和修改。

- 可以在 Skype for Business Server 2019 控制面板和 Skype for Business Server 2019 命令行管理程序中查看和修改。

- 可以通过使用 Set-csdialinconferencingaccessnumber cmdlet 和 Priority 参数在区域内重新排序。

在停止旧版安装池之前，必须完成指向旧版安装池的拨入访问号码的迁移。 如果您未按以下过程所述完成拨入访问号码迁移，则对访问号码的传入呼叫将失败。

> [!IMPORTANT]
> 必须先执行此过程，然后才能解除旧版安装池。 

> [!NOTE]
> 我们建议您在网络使用率较低时移动拨入访问号码，以防出现短时间的服务中断。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>标识和移动拨入访问号码

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。

2. 若要将每个拨入访问号码移到托管在 Skype for Business Server 2019 上的池，请在命令行中运行： 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 打开 "Skype for Business Server 控制面板"。

4. 在左侧导航栏中，单击“会议”****。

5. 单击 "**拨入访问号码**" 选项卡。 

6. 验证您要从中迁移的旧版安装池不会保留任何拨入访问号码。

    > [!NOTE]
    > 当所有拨入访问号码都指向 Skype for Business Server 2019 池时，您就可以停止使用旧版安装池了。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板验证拨入访问号码迁移

1. 从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户中，登录到内部部署中的任何计算机。 

2. 打开 "Skype for Business Server 控制面板"。

3. 在左侧导航栏中，单击“会议”****。

4. 单击 "**拨入访问号码**" 选项卡。 

5. 验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序验证拨入访问号码迁移

1. 打开 Skype for Business Server 命令行管理程序。

2. 若要从命令行运行，以返回已迁移的所有电话拨入式会议访问号码，请执行以下操作：

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。


