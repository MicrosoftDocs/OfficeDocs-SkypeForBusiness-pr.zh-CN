---
title: 配置主管理服务器
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：配置您的主管理服务器、安装 System Center Operations Manager 和导入 Skype for business Server 2019 的管理包。
ms.openlocfilehash: 2ad04419ec60e7c752d22c4cdc5c4e82fdb853f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150549"
---
# <a name="configure-the-primary-management-server"></a>配置主管理服务器

**摘要：** 配置您的主管理服务器，安装 System Center Operations Manager，并导入 Skype for business Server 2019 的管理包。

若要充分利用 Skype for Business Server 2019 中包含的新运行状况监视功能，必须先指定一台计算机作为主管理服务器。 然后，必须在该计算机上安装 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。 此外，必须先安装受支持的 SQL Server 版本，才能充当 Operations Manager 后端数据库。

安装 System Center Operations Manager 时，将需要安装该产品的所有组件，包括：

- 操作数据库

- 服务器

- 控制台

- Windows PowerShell cmdlet

- Web 控制台

- Reporting

- 数据仓库

> [!IMPORTANT]
> 安装 System Center Operations Manager 2012 前，需要安装 "[Microsoft Report Viewer 2010 可再发行组件包](https://www.microsoft.com/download/details.aspx?id=6442)"。

有关这些产品及其安装的详细信息，请参阅以下链接：

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

请注意，每个 Skype for Business Server 部署只能有一个根管理服务器。

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>导入 Skype for Business Server 2019 管理包

您可以通过安装管理包来扩展 System Center Operations Manager 的功能—该软件规定 System Center Operations Manager 可以监视的项目、这些项目的监视方式以及应如何触发警报以及如何触发警报以及报表. Skype for Business Server 2019 包括两个 System Center Operations Manager 管理包，它们提供以下功能：

- **组件和用户管理包**（Microsoft.LS.2019.Monitoring.ComponentAndUser.mp）跟踪在事件日志中记录的、由性能计数器注册的 Skype For business Server 问题，或记录在呼叫详细信息记录（cdr）或体验质量（QoE）数据库中的问题。 对于关键问题，可以将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或 SMS 消息通知管理员。 （SMS 或短信服务）是用于将短信从一个移动设备发送到另一个移动设备的技术。

    > [!NOTE]
    >  有关配置 Operations Manager 通知的详细信息，请参阅[配置通知](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。

- **主动监控管理包**（Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp）主动测试密钥 Skype For business Server 组件，例如登录到系统、交换即时消息或呼叫位于公用电话交换网（PSTN）的电话。 这些测试通过使用 Skype for Business Server 综合事务 cmdlet 进行。 例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。 如果此模拟对话失败，则会生成警报。

导入管理包是一个至关重要的步骤。 如果未导入管理包，你将无法使用 Operations Manager 来监视 Skype for business Server 事件或运行 Skype for Business Server 合成事务。

组件和用户管理包用于仅监视 Skype for Business Server 2019。 如果您处于同时安装 Skype for business Server 2019 和 Skype for business Server 2015 的共存方案中，应继续为 Skype for business Server 2015 计算机使用 Skype for Business Server 2015 管理包。

> [!NOTE]
> 适用于 Skype for business Server 2019 的管理包包括 Skype for Business Server 2019 组件和用户管理包，以及 Skype for Business Server 2019 主动监控管理包。

可使用下列任一工具导入管理包：

- **System Center Operations Manager**使用此方法，可以使用 Operations Manager 为 Skype for business Server 添加监控。

- **Operations Manager 命令行管理**程序您可以使用 Operations Manager 命令行管理程序直接导入，或解决在使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 导入管理包

1. 从 Microsoft Web 下载中下载 SkypeForBusiness2019ManagementPacks，并安装 msi。

2. 在 System Center Operations Manager 中，单击 "**管理**"。

3. 在 "管理" 窗格中，右键单击 "**管理包**"，然后单击 "**导入管理包**"。

4. 在“选择管理包”**** 对话框中，单击“添加”****，然后单击“从磁盘中添加”****。

5. 在 "**联机目录连接**" 对话框中，单击 "**否**"。

6. 在 "**选择要导入的管理包**" 对话框中，找到并选择文件 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp，然后单击 "**打开**"。 若要在对话框中选择多个文件，请单击第一个文件，然后在按住 Ctrl 键的同时单击后续文件。

7. 在“选择管理包”**** 对话框中，单击“安装”****。 如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。 如果出现这种情况，请将文件复制到其他文件夹，然后重新启动导入和安装过程。

8. 在“选择管理包”**** 对话框中，单击“关闭”****。 导入和安装过程可能需要几分钟的时间才能完成。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 命令行管理程序导入管理包

通常情况下，使用 Operations Manager 控制台导入管理包更为简单。 但是，如果发生错误，并且导入失败，则控制台不总是提供足够的错误报告。 通过比较，Operations Manager 命令行管理程序提供了详细信息。 如果您使用的是 Operations Manager，并且在导入管理包时遇到问题，请使用 Operations Manager 命令行管理程序导入该程序包。 Operations Manager 命令行管理程序提供的信息可帮助您确定导入失败的原因。

1. 依次单击 "**开始**"、"**所有程序**"、" **Microsoft System Center 2012**"、" **Operations manager**" 和 " **operations manager Shell**"。

2. 在 Operations Manager 命令行管理程序中，使用文件 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 的副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 导入第一个管理包后，请使用文件 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
