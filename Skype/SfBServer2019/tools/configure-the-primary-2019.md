---
title: 配置主管理服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 配置你的主管理服务器、安装 System Center Operations Manager 以及导入 Skype for business Server 2019 的管理包。'
ms.openlocfilehash: 316931aff5379de10b0301cc65e94443ed0f7675
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284037"
---
# <a name="configure-the-primary-management-server"></a>配置主管理服务器

**摘要:** 配置你的主管理服务器、安装 System Center Operations Manager 以及导入 Skype for business Server 2019 的管理包。

若要充分利用 Skype for Business Server 2019 中包含的新运行状况监视功能, 必须首先指定一个计算机作为你的主管理服务器。 然后, 必须在该计算机上安装 System Center Operations Manager 2012 SP1 或 System Center Operations Manager 2007 R2。 此外, 必须首先安装支持的 SQL Server 版本, 才能充当 Operations Manager 后端数据库。

安装 System Center Operations Manager 时, 你将需要安装该产品的所有组件, 包括:

- 操作数据库

- 服务器

- 控制台

- Windows PowerShell cmdlet

- Web 控制台

- 报告

- 数据仓库

> [!IMPORTANT]
> 必须先安装 "[Microsoft Report Viewer 2010 可再发行组件包](https://www.microsoft.com/en-us/download/details.aspx?id=6442)", 然后才能安装 System Center Operations Manager 2012。

有关这些产品及其安装方法的详细信息，请参阅以下链接：

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

请记住, 每个 Skype for business 服务器部署只能有一个根管理服务器。

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>导入 Skype for Business Server 2019 管理包

你可以通过安装管理包来扩展 System Center Operations Manager 的功能-该软件规定 System Center Operations Manager 可以监视哪些项目、应如何监视这些项目以及应如何触发警报以及据. Skype for Business 服务器2019包括两个 System Center Operations Manager 管理包, 它们提供以下功能:

- **组件和用户管理包**(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) 跟踪事件日志中记录的 Skype for Business 服务器问题, 这些问题由性能计数器注册, 或者记录在通话详细记录 (CDRs) 或体验质量 (QoE) 数据库中。 对于严重问题, System Center Operations Manager 可以配置为通过电子邮件、即时消息或 SMS 消息立即通知管理员。 （SMS，即短消息服务，是一种用来将文本消息从一个移动设备发送到另一个移动设备的技术）。

    > [!NOTE]
    >  有关配置 Operations Manager 通知的详细信息, 请参阅[配置通知](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。

- **活动监视管理包**(Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) 主动测试关键 Skype for business 服务器组件, 如登录到系统、交换即时消息或拨打公共交换电话网络上的电话 (PSTN). 这些测试是使用 Skype for Business Server 综合事务 cmdlet 来执行的。 例如，**Test-CsIM** cmdlet 用来模拟一对测试用户之间的即时消息对话。 如果这种模拟的对话失败，就会生成警报。

导入管理包是关键的一步。如果未导入管理包，就不能使用 Operations Manager 来监视 Skype for Business Server 事件，也不能运行 Skype for Business Server 综合事务。

组件和用户管理包仅用于监控 Skype for Business Server 2019。 如果你处于安装 Skype for business Server 2019 和 Skype for business Server 2015 的共存方案中, 你应继续使用 Skype for business server 2015 计算机的 Skype for business Server 2015 管理包。

> [!NOTE]
> Skype for business Server 2019 的管理包包括 Skype for business Server 2019 组件和用户管理包以及 Skype for Business Server 2019 活动监视管理包。

可使用下列任一工具导入管理包：

- **System Center Operations Manager**使用此方法, 你可以使用 Operations Manager 添加针对 Skype for Business 服务器的监视。

- **Operations Manager Shell**你可以使用 Operations Manager 外壳直接导入, 或解决在使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 导入管理包

1. 从 Microsoft Web 下载下载 SkypeForBusiness2019ManagementPacks, 然后安装 msi。

2. 在 System Center Operations Manager 中, 单击 "**管理**"。

3. 在 "管理" 窗格中, 右键单击 "**管理包**", 然后单击 "**导入管理包**"。

4. 在“选择管理包”**** 对话框中，单击“添加”****，然后单击“从磁盘中添加”****。

5. 在“联机目录连接”**** 对话框中，单击“否”****。

6. 在 "**选择要导入的管理包**" 对话框中, 找到并选择 "文件 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp" 和 "Microsoft.LS.2019.Monitoring.ComponentAndUser.mp", 然后单击 "**打开**"。 若要在对话框中选择多个文件，请单击第一个文件，按住 Ctrl 键，然后单击后续文件。

7. 在“选择管理包”**** 对话框中，单击“安装”****。如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。如果出现此情况，请将文件复制到其他文件夹中，然后重新开始导入和安装过程。

8. 在“选择管理包”**** 对话框中，单击“关闭”****。导入和安装过程可能需要几分钟时间才能完成。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager Shell 导入管理包

一般来说，使用 Operations Manager 控制台导入管理包要更容易。但是，如果发生错误并且导入失败，则控制台不会总是提供足够的错误报告。相比之下，Operations Manager Shell 提供了详细信息。如果您使用的是 Operations Manager 并且导入管理包时遇到问题，请使用 Operations Manager Shell 导入包。Operations Manager Shell 提供了可帮助您确定导入失败原因的信息。

1. 依次单击“开始”****、“所有程序”****、“Microsoft System Center 2012”****、“Operations Manager”**** 和“Operations Manager Shell”****。

2. 在 Operations Manager Shell 中, 使用文件 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 副本的实际路径在命令提示符处键入以下命令, 然后按 ENTER:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 导入第一个管理包后, 请使用文件 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp 副本的路径重复该过程:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
