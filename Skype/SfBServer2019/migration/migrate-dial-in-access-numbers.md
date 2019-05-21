---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 将拨入访问号码迁移到 Skype for business 服务器2019需要运行 CsApplicationEndpoint cmdlet 以迁移联系人对象。 在旧式安装和 Skype for business Server 2019 共存期间, 您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧安装中创建的拨入访问号码类似, 如下所述:顶部.
ms.openlocfilehash: 83cf8b75bcf9a8d4794ae0f95962f3627d8592c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280810"
---
# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

将拨入访问号码迁移到 Skype for business 服务器2019需要运行**CsApplicationEndpoint** cmdlet 以迁移联系人对象。 在旧式安装和 Skype for business Server 2019 共存期间, 您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧安装中创建的拨入访问号码类似, 如下所述:顶部. 

在旧安装中创建的拨入接入号码, 但移动到 Skype for business Server 2019, 或者在迁移期间或迁移后的 Skype for business Server 2019 中创建的号码具有以下特征:

- 不会出现在 Office 通信服务器 2007 R2 邀请和 "拨入访问号码" 页面上。

- 显示在 "旧版安装会议邀请" 和 "拨入访问号码" 页面上。

- 显示在 Skype for Business Server 2019 会议邀请和 "拨入访问号码" 页面上。

- 无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。

- 可在旧式安装控制面板和旧式安装命令行中查看和修改。

- 可在 Skype for Business Server 2019 控制面板和 Skype for business Server 2019 管理外壳程序中查看和修改。

- 可通过将 CsDialinConferencingAccessNumber cmdlet 与 Priority 参数一起使用来在区域内重新排序。

在停止旧版安装池之前, 必须完成指向旧安装池的拨入访问号码的迁移。 如果您没有完成拨入访问号码迁移, 如以下过程中所述, 对接入号码的拨入调用将失败。

> [!IMPORTANT]
> 必须先执行此过程, 然后才能解除旧版安装池。 

> [!NOTE]
> 我们建议你在网络使用率较低时移动拨入访问号码, 以防出现短时间的服务中断。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>标识和移动拨入访问号码

1. 启动 Skype for Business Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**", 然后单击 " **skype for business 服务器管理外壳**"。

2. 若要将每个拨入访问号码移到托管在 Skype for Business Server 2019 上的池, 请从命令行运行: 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 打开 "Skype for Business 服务器" 控制面板。

4. 在左侧导航栏中，单击“**会议**”。

5. 单击 "**拨入访问号码**" 选项卡。 

6. 验证你要从中迁移的旧版安装池不会保留拨入访问号码。

    > [!NOTE]
    > 当所有拨入访问号码指向 Skype for business Server 2019 池时, 您就可以停止使用旧安装池。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server "控制面板" 验证拨入访问号码迁移

1. 从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户登录到内部部署中的任何计算机。 

2. 打开 "Skype for Business 服务器" 控制面板。

3. 在左侧导航栏中，单击“**会议**”。

4. 单击 "**拨入访问号码**" 选项卡。 

5. 验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序验证拨入访问号码迁移

1. 打开 Skype for Business Server 命令行管理程序。

2. 要从命令行中返回已迁移的所有拨入式会议访问号码, 请执行以下操作:

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。


