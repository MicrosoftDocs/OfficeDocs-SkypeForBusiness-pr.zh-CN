---
title: 安装和打开管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题介绍如何安装和打开所需部署和管理 for Business 的 Skype 的管理工具。
ms.openlocfilehash: f914864ee1844ac52d5a8c1ab63da2f7036acaf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915085"
---
# <a name="install-and-open-administrative-tools"></a>安装和打开管理工具

本主题介绍如何安装部署和管理 Skype 的业务服务器所需的管理工具。 默认情况下，运行 Business Server Skype 每台服务器上安装这些管理工具。 此外，您可以在其他计算机，如专用的管理控制台上安装管理工具。 我们强烈建议为您创建的业务服务器部署 Skype 位于同一个域或林的计算机上安装管理工具，以确保该 Active Directory 域服务准备步骤已完成，这样可使您可以使用管理工具的计算机上更高版本以发布拓扑。 此外请务必查看所必需的条件，才能安装或者使用 Skype Business Server 管理工具。 请参阅中[的业务服务器 2019 Skype](../../SfBServer2019/plan/system-requirements.md)或[业务服务器 2015年的 Skype](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)的要求文档。
 
> [!Important]
> 如果您的组织需要在非系统驱动器驱动器上找到 Internet 信息服务 (IIS) 和所有 Web 服务，您可以更改设置对话框中的业务服务器文件的 Skype 安装位置路径。 如果安装文件安装到此路径，包括 OCSCore.msi 业务服务器文件的 Skype 的其余部分将部署到以及此驱动器。 

## <a name="to-install-the-administrative-tools"></a>安装管理工具

1. 登录到要安装管理工具的计算机的本地管理员 （最低要求）。 如果您要为已启用 Windows 中的标准用户和用户帐户控制 (UAC) 登录，系统将提示您的本地管理员或域等效用户名和密码。
2. 在您的计算机上找到安装媒体，然后双击 \Setup\amd64\Setup.exe。
3. 如果提示您安装 Microsoft Visual c + + 可发行软件包，请单击**是**。
4. 在安装位置页上单击**确定**。 如果您需要安装到另一个位置的文件，请将此路径更改为另一个位置或驱动器。

    > [!Important]
    > 如果您的组织需要在非系统驱动器驱动器上找到 Internet 信息服务 (IIS) 和所有 Web 服务，您可以更改设置对话框中的业务服务器文件的 Skype 安装位置路径。 如果安装文件安装到此路径，包括 OCSCore.msi 业务服务器文件的 Skype 的其余部分将部署到此驱动器太。 

5. 在最终用户许可协议页上，查看许可条款，单击**我接受**，，，然后单击**确定**。 此步骤是必需的然后才能继续。
6. 在部署向导页上，单击**安装管理员工具**。 
7. 安装成功完成后，单击**退出**。

使用以下过程来打开管理工具，以便部署、 配置，或解决您 Skype 企业服务器拓扑。

- [部署向导](#deployment-wizard)
- [拓扑生成器](#topology-builder) 
- [Skype for Business Server 控制面板](#skype-for-business-server-control-panel)
- [Skype for Business Server 管理程序](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>部署向导

使用以下过程来启动部署向导本地以添加或删除组件文件。

**若要启动 Skype 的业务 Server 部署向导**

1. 登录到计算机的业务 Server 部署向导 Skype 的 Domain Admins 组和 RTCUniversalServerAdmins 组成员身份的安装。
2. 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 部署向导**。


## <a name="topology-builder"></a>拓扑生成器 

使用以下过程打开拓扑生成器以定义要部署您 Skype 中的企业服务器拓扑的服务器。

**要打开 Skype 的业务 Server 拓扑生成器以设计拓扑**

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    > [!NOTE]
    > 您可以使用本地用户组的成员的帐户定义拓扑，但要阅读、 发布或启用拓扑，它所必需的企业服务器的服务器上安装 Skype，必须使用的 Domain Admins 组和 th 成员的帐户e RTCUniversalServerAdmins 组，并且您打算用于存档文件存储，以便拓扑生成器可以配置所需的随机访问控制列表 （的文件共享上具有完全控制权限 （即，读取、 写入和修改）Dacl)，或具有同等用户权限的帐户。
 
2. 启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 拓扑生成器**。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server 控制面板 

使用以下过程之一打开业务 Server 控制面板管理的服务器、 用户、 客户端和设备环境中的配置的 Skype。

> [!NOTE]
> 您可以使用分配给 CsAdministrator 角色业务 Server Control Panel Skype 中执行任何任务的用户帐户。 其他角色可用于登录到业务 Server Control Panel 执行特定的管理任务，您需要执行该任务相关的 Skype。 例如，CSArchivingAdministrator 可用于管理业务 Server Control Panel 中 Skype 的存档。 有关角色的详细信息，请参阅[规划基于角色的访问控制](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)。 有关可用来执行特定任务的角色的详细信息，请参阅文档的任务。 

**若要从组织防火墙内的任何计算机的业务 Server Control Panel 打开 Skype**

1. 使用分配给 CsAdministrator 角色或其他有相应的用户权限和要执行的任务的权限的角色的用户帐户，登录到内部部署与屏幕分辨率至少为 1024 x 768 中的任何计算机。

    > [!IMPORTANT]
    > 如果已配置管理简单的统一资源定位器 (URL)，您可以从组织防火墙内的任何计算机运行 Internet 浏览器的业务 Server Control Panel 访问 Skype。 有关配置管理简单 URL 的详细信息，请参阅[规划简单 Url](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx)和[编辑或配置简单 Url](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx)。 

2. 打开一个浏览器窗口，然后输入管理 URL 为组织配置的。

**若要运行 Skype 业务服务器的计算机上打开业务 Server Control Panel Skype**

1. 是 CsAdministrator 角色或其他有相应的用户权限和要执行的任务的权限的角色的成员的用户帐户，登录到计算机安装了 Skype 业务服务器或，最少业务 Server 管理工具的 Skype。 若要配置设置，计算机必须屏幕分辨率至少为 1024 x 768。
2. 为业务 Server Control Panel 启动 Skype： 单击**开始**，单击**所有程序**、**管理工具**，指向**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Control Panel**。

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理程序 

使用以下过程打开 Skype 的业务 Server Management Shell，以通过使用命令行管理服务器、 用户、 客户端和设备中您的环境。

> [!NOTE]
> 您可以使用分配给 CsAdministrator 角色业务 Server 命令行管理程序中 Skype 执行任何任务的用户帐户。 您可以使用登录其他角色执行特定的管理任务，具体取决于您需要执行的任务。 例如，您可以使用 CSArchivingAdministrator 运行与存档管理相关的 cmdlet。 有关角色的详细信息，请参阅[规划基于角色的访问控制](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)。 有关可用于运行特定 cmdlet 的角色的详细信息，请参阅 cmdlet 文档。<br/><br/>您还可以使用 RTCUniversalServerAdmins、 RTCUniversalUserAdmins、 或 RTCUniversalReadOnlyAdmins 组，具体取决于 cmdlet 中的用户帐户来运行某些 cmdlet。 

**若要打开 Skype 业务 Server 命令行管理程序**

如果您的业务 Server 命令行管理程序中打开 Windows PowerShell 窗口而不是 Skype 后，不能默认情况下运行 Business Server cmdlet Skype。 若要运行从 Windows PowerShell 中的 Business Server cmdlet Skype，在 Windows PowerShell 命令提示符处键入以下内容：

`Import-Module Lync`

为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。
