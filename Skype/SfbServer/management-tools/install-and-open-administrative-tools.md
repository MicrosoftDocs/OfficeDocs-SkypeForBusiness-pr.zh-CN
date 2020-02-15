---
title: 安装和打开管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本主题介绍如何安装和打开部署和管理 Skype for business 所需的管理工具。
ms.openlocfilehash: b2d06d14263174229d35ff2e5108574296bb5034
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031066"
---
# <a name="install-and-open-administrative-tools"></a>安装和打开管理工具

本主题介绍如何安装部署和管理 Skype for business Server 所需的管理工具。 默认情况下，在运行 Skype for Business Server 的每台服务器上安装管理工具。 此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。 强烈建议您在与您正在创建的 Skype for Business Server 部署相同的域或林中的计算机上安装管理工具，以确保已完成 Active Directory 域服务的准备步骤。这使您可以在以后使用该计算机上的管理工具发布拓扑。 此外，在安装或使用 Skype for Business Server 管理工具之前，请务必查看必需的要求。 请参阅[skype For Business server 2019](../../SfBServer2019/plan/system-requirements.md)或[Skype for business server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)中的要求文档。
 
> [!Important]
> 如果您的组织要求您在除系统驱动器之外的驱动器上查找 Internet 信息服务（IIS）和所有 Web 服务，则可以在 "安装程序" 对话框中更改 Skype for business Server 文件的安装位置路径。 如果将安装文件安装到此路径（包括 OCSCore），则其他 Skype for Business Server 文件也将同时部署到此驱动器。 

## <a name="to-install-the-administrative-tools"></a>安装管理工具

1. 以本地管理员身份登录（最低要求）要安装管理工具的计算机。 如果您作为 Windows 和用户帐户控制（UAC）中的标准用户登录，则系统将提示您输入本地管理员或与域等效的用户名和密码。
2. 在计算机上找到安装媒体，然后双击 \Setup\amd64\Setup.exe。
3. 如果系统提示您安装 Microsoft Visual c + + 可分发，请单击 **"是"**。
4. 在 "安装位置" 页上，单击 **"确定"**。 如果要将文件安装至其他位置，请将此路径更改为相应的位置或驱动器。

    > [!Important]
    > 如果您的组织要求您在除系统驱动器之外的驱动器上查找 Internet 信息服务（IIS）和所有 Web 服务，则可以在 "安装程序" 对话框中更改 Skype for business Server 文件的安装位置路径。 如果将安装文件安装到此路径（包括 OCSCore），则其他 Skype for Business Server 文件也将同时部署到此驱动器。 

5. 在“最终用户许可协议”页上，查看许可条款，单击 **“我接受”**，然后单击 **“确定”**。 必须完成此步骤，才能继续安装。
6. 在 "部署向导" 页上，单击 "**安装管理员工具**"。 
7. 安装成功完成后，单击 **“退出”**。

使用以下过程打开管理工具，以部署、配置或解决 Skype for Business Server 拓扑。

- [部署向导](#deployment-wizard)
- [拓扑生成器](#topology-builder) 
- [Skype for Business Server 控制面板](#skype-for-business-server-control-panel)
- [Skype for Business Server 命令行管理程序](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>部署向导

使用以下过程可在本地启动部署向导，以添加或删除组件文件。

**启动 Skype for Business Server 部署向导**

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组的成员身份登录到安装 Skype for Business Server 部署向导的计算机。
2. 依次单击 "**开始**"、"**所有程序**"、" **skype for Business server**" 和 " **skype for business server 部署向导**"。


## <a name="topology-builder"></a>拓扑生成器 

使用以下过程打开拓扑生成器以定义要在 Skype for Business Server 拓扑中部署的服务器。

**打开 Skype for Business Server 拓扑生成器以设计拓扑**

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    > [!NOTE]
    > 您可以通过使用属于本地用户组成员的帐户来定义拓扑，但要读取、发布或启用拓扑（在服务器上安装 Skype for Business Server 时需要），必须使用属于 Domain Admins 组成员的帐户以及第e RTCUniversalServerAdmins group，具有对要用于存档文件存储的文件共享的完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（Dacl）或具有等效用户权限的帐户。
 
2. 启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **skype for business server**"，然后单击 " **skype for business server 拓扑生成器**"。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server 控制面板 

使用以下过程之一打开 Skype for Business Server 控制面板，以管理环境中的服务器、用户、客户端和设备的配置。

> [!NOTE]
> 您可以使用分配给 CsAdministrator 角色的用户帐户在 Skype for Business Server 控制面板中执行任何任务。 您可以使用其他角色登录到 Skype for Business Server 控制面板，以执行特定的管理任务，具体取决于需要执行的任务。 例如，可以使用 CSArchivingAdministrator 在 Skype for Business Server 控制面板中管理存档。 有关角色的详细信息，请参阅[规划基于角色的访问控制](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)。 有关可用于执行某项特定任务的角色的详细信息，请参阅该任务的文档。 

**从组织的防火墙内的任何计算机中打开 Skype for Business Server 控制面板**

1. 从分配给 CsAdministrator 角色或其他角色且具有要执行的任务的相应用户权限的用户帐户，以最小屏幕分辨率为 1024 x 768 登录到内部部署中的任何计算机。

    > [!IMPORTANT]
    > 如果已配置了管理简单的统一资源定位器（URL），则可以从组织的防火墙内的任何计算机上运行的 Internet 浏览器访问 Skype for Business Server 控制面板。 有关配置管理简单 URL 的详细信息，请参阅[规划简单 url](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx)和[编辑或配置简单 url](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx)。 

2. 打开浏览器窗口，然后输入为组织配置的管理 URL。

**在运行 Skype for Business Server 的计算机上打开 Skype for Business Server 控制面板**

1. 从属于 CsAdministrator 角色的成员或其他角色且具有要执行的任务的相应用户权限和权限的用户帐户，登录到已安装 Skype for Business Server 的计算机上，或者至少（Skype for Business Server 管理工具）。 若要配置设置，计算机的最小屏幕分辨率必须为 1024 x 768。
2. 启动 Skype for Business Server 控制面板：单击 "**开始**"，单击 "**所有程序**"，指向 "**管理工具**"，指向 " **skype for Business server**"，然后单击 " **skype for business server 控制面板**"。

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 命令行管理程序 

使用以下过程打开 Skype for Business Server 命令行管理程序，以使用命令行管理环境中的服务器、用户、客户端和设备。

> [!NOTE]
> 您可以使用分配给 CsAdministrator 角色的用户帐户在 Skype for Business Server 命令行管理程序中执行任何任务。 可使用其他角色登录以执行特定的管理任务，具体取决于需执行的任务。 例如，可以使用 CSArchivingAdministrator 运行与存档管理相关的 cmdlet。 有关角色的详细信息，请参阅[规划基于角色的访问控制](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)。 有关可用于运行某个特定 cmdlet 的角色的详细信息，请参阅该 cmdlet 的文档。<br/><br/>还可以使用 RTCUniversalServerAdmins 组、RTCUniversalUserAdmins 组或 RTCUniversalReadOnlyAdmins 组中的用户帐户来运行某些 cmdlet，具体取决于该 cmdlet。 

**打开 Skype for Business Server 命令行管理程序**

如果打开的是 Windows PowerShell 窗口而不是 Skype for Business Server 命令行管理程序，则默认情况下无法运行 Skype for Business Server cmdlet。 若要从 Windows PowerShell 中运行 Skype for Business Server cmdlet，请在 Windows PowerShell 命令提示符处键入以下内容：

`Import-Module Lync`

启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business server**"，然后单击 " **skype for business server Management Shell**"。
