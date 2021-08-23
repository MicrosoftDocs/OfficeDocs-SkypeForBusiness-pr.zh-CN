---
title: 配置主管理服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：配置主管理服务器、System Center Operations Manager 和导入 2019 Skype for Business Server管理包。
ms.openlocfilehash: f7fd7350cb4cf5a9697e789806c963f4fbe46636
ms.sourcegitcommit: 6a87a4180519e493ac115c2faadb9ccae26d5a35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "58372232"
---
# <a name="skype-for-business-server-configure-the-primary-management-server"></a>Skype for Business Server：配置主管理服务器

**摘要：** 为 2019 System Center主管理服务器、安装 Operations Manager 和导入Skype for Business Server包。

若要充分利用 Skype for Business Server 2019 中包含的新运行状况监视功能，必须先指定一台计算机作为主管理服务器。 然后，您必须System Center计算机上安装 Operations Manager 2012 SP1、R2 或 System Center Operations Manager 2007 R2。 此外，您必须先安装受支持的 SQL Server，以用作 Operations Manager 后端数据库。

在 Operations Manager System Center时，需要安装该产品的所有组件，包括：

- 操作数据库

- 服务器

- 控制台

- Windows PowerShell cmdlet

- Web 控制台

- 报表

- 数据仓库

> [!IMPORTANT]
> 在安装 operations Manager[2012 Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442)可再发行软件包之前，需要安装"System Center 2010 可再发行软件包"。

有关这些产品及其安装的详细信息，请参阅以下链接：

- [System CenterOperations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

请记住，每个部署只能有一个根Skype for Business Server服务器。

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>导入 Skype for Business Server 2019 管理包

您可以通过安装管理包（指示 System Center Operations Manager 可以监视哪些项目、应监视这些项目以及如何触发和报告警报的软件）来扩展 System Center Operations Manager 的功能。 Skype for Business Server 2019 System Center两个 Operations Manager 管理包，它们提供以下功能：

- 组件 **和** 用户管理包 (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) 跟踪事件日志中记录的 Skype for Business Server 问题、由性能计数器注册的或记录在呼叫详细信息记录 (CDR) 或用户体验质量 (QoE) 数据库中的问题。 对于关键问题，System Center Operations Manager 配置为立即通过电子邮件、即时消息或短信通知管理员。  (短信服务是一种用于将短信从一个移动设备发送到另一个移动设备的技术。) 

    > [!NOTE]
    >  有关配置 Operations Manager 通知的详细信息，请参阅 [配置通知](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。

- **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) 主动测试关键的 Skype for Business Server 组件，例如登录系统、交换即时消息或呼叫位于公用电话交换网 (PSTN) 上的电话。 这些测试通过使用综合事务 cmdlet Skype for Business Server执行。 例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。 如果此模拟对话失败，将生成警报。

导入管理包是一个关键步骤。 如果未导入管理包，则将无法使用 Operations Manager 监视事件Skype for Business Server或运行Skype for Business Server事务。

Component and User Management Pack is used to monitor only Skype for Business Server 2019. 如果同时安装了 Skype for Business Server 2019 和 Skype for Business Server 2015 的共存方案，您应该继续使用 Skype for Business Server 2015 计算机的 Skype for Business Server 2015 管理包。

> [!NOTE]
> Skype for Business Server 2019 的管理包包括 Skype for Business Server 2019 组件和用户管理包以及 Skype for Business Server 2019 Active Monitoring Management Pack。

可使用下列任一工具导入管理包：

- **System Center Operations Manager** 使用此方法，可使用 Operations Manager 添加对 Skype for Business Server。

- **Operations Manager 外壳** 可以使用此Operations Manager 外壳直接导入，或解决在使用 Operations Manager 控制台导入管理包时遇到的System Center问题。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 Operations Manager 导入System Center包

1. 从 microsoft SkypeForBusiness2019ManagementPacks.msi下载下载文件，然后安装 msi。

2. 在"System Center操作管理器"中，单击"管理 **"。**

3. 在"管理"窗格中，右键单击"**管理包"，** 然后单击"**导入管理包"。**

4. 在“选择管理包”对话框中，单击“添加”，然后单击“从磁盘中添加”。

5. 在"**联机目录连接"** 对话框中，单击"否 **"。**

6. 在 **"选择要导入的管理** 包"对话框中，找到并选择 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp Microsoft.LS.2019.Monitoring.ComponentAndUser.mp 文件，然后单击"打开 **"。** 若要在对话框中选择多个文件，请单击第一个文件，然后按住 Ctrl 键，然后单击后续文件。

7. 在“选择管理包”对话框中，单击“安装”。 如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。 如果发生这种情况，将文件复制到其他文件夹，然后重新启动导入和安装过程。

8. 在“选择管理包”对话框中，单击“关闭”。 导入和安装过程可能需要几分钟才能完成。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>使用管理包导入Operations Manager 外壳

通常，使用 Operations Manager 控制台导入管理包会更容易。 但是，如果发生错误并且导入失败，则控制台不会始终提供足够的错误报告。 相比之下，Operations Manager 外壳提供详细信息。 如果使用的是 Operations Manager，但导入管理包时遇到问题，则使用 Operations Manager 外壳。 用户提供的信息Operations Manager 外壳可帮助您确定导入失败的原因。

1. 单击 **"开始**"，单击"所有程序"，单击 **"Microsoft System Center 2012"，** 单击 **"Operations Manager"，** 然后单击"Operations Manager 外壳"。 

2. 在Operations Manager 外壳，使用文件副本的实际路径在命令提示符下键入以下 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp，然后按 Enter：

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 导入第一个管理包后，使用文件副本的路径重复此过程 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp：

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```