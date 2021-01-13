---
title: 安装和打开管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本主题介绍如何安装和打开部署和管理 Skype for Business 所需的管理工具。
ms.openlocfilehash: d31fe784b62a5d709049dc5061e323034065df37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835092"
---
# <a name="install-and-open-administrative-tools"></a>安装和打开管理工具

本主题介绍如何安装部署和管理 Skype for Business Server 所需的管理工具。 默认情况下，管理工具安装在每台运行 Skype for Business Server 的服务器上。 此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。 强烈建议您在与您创建的 Skype for Business Server 部署位于同一个域或林中的计算机上安装管理工具，以确保 Active Directory 域服务准备步骤已完成，这样您稍后可以使用该计算机上管理工具发布拓扑。 此外，请确保在安装或使用 Skype for Business Server 管理工具之前查看必要的要求。 请参阅 [Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) 或 Skype for Business Server [2015 中的要求文档](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。
 
> [!Important]
> 如果你的组织要求你在系统驱动器Internet Information Services (IIS) 以及所有 Web 服务，可以在"安装"对话框中更改 Skype for Business Server 文件的安装位置路径。 如果将安装程序文件（包括 OCSCore.msi）安装到此路径，则其余的 Skype for Business Server 文件也将部署到此驱动器。 

## <a name="to-install-the-administrative-tools"></a>安装管理工具

1. 以本地管理员身份登录（最低要求）要安装管理工具的计算机。 如果在 Windows 和用户帐户控制 (UAC) 中以标准用户身份登录，系统将提示你输入本地管理员或域等效用户名和密码。
2. 在计算机上找到安装媒体，然后双击 \Setup\amd64\Setup.exe。
3. 如果系统提示你安装 Microsoft Visual C++ 可分发，请单击"**是"。**
4. 在"安装位置"页上，单击"**确定"。** 如果要将文件安装至其他位置，请将此路径更改为相应的位置或驱动器。

    > [!Important]
    > 如果你的组织要求你在系统驱动器Internet Information Services (IIS) 以及所有 Web 服务，可以在"安装"对话框中更改 Skype for Business Server 文件的安装位置路径。 如果将安装程序文件（包括 OCSCore.msi）安装到此路径，则其余的 Skype for Business Server 文件也将部署到此驱动器。 

5. 在“最终用户许可协议”页上，查看许可条款，单击 **“我接受”**，然后单击 **“确定”**。 必须完成此步骤，才能继续安装。
6. 在"部署向导"页上，单击 **"安装管理员工具"。** 
7. 安装成功完成后，单击 **“退出”**。

使用以下过程打开管理工具，以部署、配置 Skype for Business Server 拓扑或对其进行故障排除。

- [部署向导](#deployment-wizard)
- [拓扑生成器](#topology-builder) 
- [Skype for Business Server 控制面板](#skype-for-business-server-control-panel)
- [Skype for Business Server 命令行管理程序](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>部署向导

使用以下过程在本地启动部署向导以添加或删除组件文件。

**启动 Skype for Business Server 部署向导**

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组的成员登录到安装了 Skype for Business Server 部署向导的计算机。
2. 单击 **"开始**"，**单击"所有** 程序"，再 **单击"Skype for Business Server"，** 然后单击 **"Skype for Business Server 部署向导"。**


## <a name="topology-builder"></a>拓扑生成器 

使用以下过程打开拓扑生成器，以定义要部署在 Skype for Business Server 拓扑中的服务器。

**打开 Skype for Business Server 拓扑生成器以设计拓扑**

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    > [!NOTE]
    > 可以使用作为本地 Users 组的成员的帐户定义拓扑，但要读取、发布或启用拓扑（在服务器上安装 Skype for Business Server 需要此拓扑， 您必须使用一个帐户，该帐户是 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，并且对要用于存档文件存储的文件共享具有完全控制权限 (即读取、写入和修改) ，以便拓扑生成器可以配置所需的任意访问控制列表 (DACLs) 或具有同等用户权限的帐户。
 
2. 启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 拓扑生成器"。**

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server 控制面板 

使用以下过程之一打开 Skype for Business Server 控制面板，以管理环境中服务器、用户、客户端和设备的配置。

> [!NOTE]
> 可以使用分配给 CsAdministrator 角色的用户帐户在 Skype for Business Server 控制面板中执行任何任务。 可以使用其他角色登录到 Skype for Business Server 控制面板，以执行特定管理任务，具体视需要执行的任务而定。 例如，可以使用 CSArchivingAdministrator 在 Skype for Business Server 控制面板中管理存档。 有关角色的详细信息，请参阅 [规划基于角色的访问控制](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)。 有关可用于执行某项特定任务的角色的详细信息，请参阅该任务的文档。 

**从组织防火墙内的任何计算机打开 Skype for Business Server 控制面板**

1. 从分配给 CsAdministrator 角色的用户帐户或其他具有要执行的任务的适当用户权限的角色，以最低屏幕分辨率 1024 x 768 登录到内部部署中的任意计算机。

    > [!IMPORTANT]
    > 如果已配置管理简单统一资源定位器 (URL) ，则可以通过在组织防火墙内的任何计算机上运行的 Internet 浏览器访问 Skype for Business Server 控制面板。 有关配置管理简单 URL 的详细信息，请参阅规划[简单 URL 和编辑](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx)[或配置简单 URL。](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx) 

2. 打开浏览器窗口，然后输入为组织配置的管理 URL。

**在运行 Skype for Business Server 的计算机上打开 Skype for Business Server 控制面板**

1. 从作为 CsAdministrator 角色成员或其他角色的用户帐户，对于要执行的任务具有相应的用户权限，请登录到已安装 Skype for Business Server 的计算机，或者至少登录到 Skype for Business Server 管理工具。 若要配置设置，计算机的最低屏幕分辨率必须为 1024 x 768。
2. 启动 Skype for Business Server控制面板：单击"开始"，单击"所有程序"，指向 **"** 管理工具"，指向 **Skype for Business Server，** 然后单击 **"Skype for Business Server 控制面板"。**

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 命令行管理程序 

使用以下过程打开 Skype for Business Server 命令行管理程序，以使用命令行管理环境中的服务器、用户、客户端和设备。

> [!NOTE]
> 可以使用分配给 CsAdministrator 角色的用户帐户在 Skype for Business Server 命令行管理程序 中执行任何任务。 可使用其他角色登录以执行特定的管理任务，具体取决于需执行的任务。 例如，可以使用 CSArchivingAdministrator 运行与存档管理相关的 cmdlet。 有关角色的详细信息，请参阅 [规划基于角色的访问控制](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)。 有关可用于运行某个特定 cmdlet 的角色的详细信息，请参阅该 cmdlet 的文档。<br/><br/>还可以使用 RTCUniversalServerAdmins 组、RTCUniversalUserAdmins 组或 RTCUniversalReadOnlyAdmins 组中的用户帐户来运行某些 cmdlet，具体取决于该 cmdlet。 

**打开 Skype for Business Server 命令行管理程序**

如果打开Windows PowerShell而不是 Skype for Business Server 命令行管理程序，则默认情况下无法运行 Skype for Business Server cmdlet。 若要从内部运行 Skype for Business Server cmdlet Windows PowerShell，在命令提示符Windows PowerShell以下命令：

`Import-Module Lync`

启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
