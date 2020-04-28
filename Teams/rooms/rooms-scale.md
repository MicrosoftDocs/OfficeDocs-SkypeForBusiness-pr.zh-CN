---
title: 使用 Microsoft 终结点配置管理器部署 Microsoft 团队聊天室
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft 终结点配置管理器在大规模部署中部署 Microsoft 团队聊天室。
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: f96b970165996cc27308ce616fb4875d741f8869
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905314"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft 终结点配置管理器部署 Microsoft 团队聊天室

本文提供使用 Microsoft 终结点配置管理器创建 Microsoft 团队聊天室部署的所有必要信息。

通过配置管理器提供的易于使用的方法，你可以将操作系统和其他应用程序部署到多台目标设备。

使用下面所示的方法指导你完成 Configuration Manager 配置，并根据组织的需要自定义本指南中提供的示例程序包和脚本。

![使用配置管理器的 Microsoft 团队会议室部署流程](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 此解决方案仅通过基于 Surface Pro 的部署进行了测试。 按照制造商指南，了解不基于 Surface Pro 的配置。

## <a name="validate-prerequisites"></a>验证先决条件

若要通过 Configuration Manager 部署 Microsoft 团队聊天室，请确保满足以下先决条件和要求。

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft 终结点配置管理器要求

-   Microsoft 终结点配置管理器版本必须至少为1706或更高版本。 我们建议使用1710或更高版本。 请查看[配置管理器中的 windows 10 支持](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)，了解 configuration manager 支持的 windows 10 版本。

-   必须安装支持的 windows 10 版本的 Windows 评估和部署工具包（ADK）。 查看可用于不同版本的 Configuration Manager 的[Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk)版本，并确保你的部署包含正确的版本。

-   必须为站点系统服务器分配分发点角色，并且应为[预启动执行环境（PXE）支持](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)启用启动映像以启用网络启动的部署。 如果未启用 PXE 支持，你可以将[可启动媒体](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用于你的部署。

-   必须将网络访问帐户配置为支持新计算机（裸机）部署方案。 若要了解有关网络访问帐户配置的详细信息，请参阅[配置管理器中使用的帐户](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

-   如果你可能同时将同一 Microsoft 团队会议室图像部署到多个单元，我们建议你启用[多路广播支持](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)。

### <a name="networking-requirements"></a>网络要求

-   您的网络应该具有动态主机配置协议（DHCP）服务器，该服务器已配置为将部署 Microsoft 团队聊天室单元的子网自动分配 IP 地址。

    > [!NOTE]
    > DHCP 租用期必须设置为比映像部署持续时间更长的值。 否则，部署可能失败。

-   您的网络（包括交换机和虚拟 Lan （Vlan））应配置为支持 PXE。 有关 IP 帮助程序和 PXE 配置的详细信息，请参阅您的网络供应商。 或者，如果未启用 PXE 支持，你可以将[可启动媒体](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用于部署。

    > [!NOTE]
    > 对于 Surface Pro 设备，仅在使用以太网适配器或来自 Microsoft 的插接站时，才支持从网络启动（PXE 启动）。 第三方以太网适配器不支持与 Surface Pro 进行 PXE 启动。 有关详细信息，请参阅[以太网适配器和 Surface 部署](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)。

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>为操作系统部署配置 Microsoft 终结点配置管理器

本文假定你已具有正常的 Configuration Manager 部署，并且不详细介绍了从头开始部署和配置 Configuration Manager 所需的所有步骤。 Microsoft 终结点配置管理器上的[文档和配置指南](https://docs.microsoft.com/configmgr/)是一个很好的资源;如果尚未部署配置管理器，建议您从这些资源开始。

按照以下说明验证是否正确配置了操作系统部署（OSD）功能。

### <a name="validate-and-upgrade-configuration-manager"></a>验证和升级 Configuration Manager

1.  在 Configuration Manager 控制台中，转到 "**管理** \> **更新和服务**"。

2.  检查已安装的内部版本和适用的更新（尚未安装）。

3.  [在配置管理器中查看 Windows 10 的支持](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client);如果需要升级你的部署，请选择要安装的更新，然后选择 "**下载**"。

4.  下载完成后，选择更新，然后选择 "**安装更新包**"。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>配置分发点以支持 PXE 和多播

1.  在 Configuration Manager 控制台中，转到 "**管理** \> **分发点**"。

2.  选择将为 Microsoft 团队聊天室部署提供服务的分发点服务器，然后选择 "**属性**"。

3.  选择 " **PXE** " 选项卡，确保启用以下设置：
    -   为客户端启用 PXE 支持
    -   允许此分发点响应传入的 PXE 请求
    -   启用未知计算机支持

4.  *可选：* 若要启用多址广播支持，请选择 "**多播**" 选项卡，并确保启用以下设置：
    -   启用多播以同时向多个客户端发送数据
    -   根据网络团队的建议配置 UDP 端口范围

### <a name="configure-the-network-access-account"></a>配置网络访问帐户

1.  在 Configuration Manager 控制台中，转到 "**管理** \> **网站配置** \> **网站**"，然后选择网站。

2.  在 "**设置**" 组中，选择 "**配置网站组件** \> **软件分发**"。

3.  选择 "**网络访问帐户**" 选项卡。设置一个或多个帐户，然后选择 **"确定"**。

> [!NOTE]
> 帐户不需要任何特殊权利，除非分发点服务器上的 "**从网络访问此计算机**" 权利除外。 常规域用户帐户将非常合适。 有关详细信息，请参阅[配置管理器中使用的帐户](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

### <a name="configure-a-boot-image"></a>配置启动映像

1.  在 Configuration Manager 控制台中，转到 "**软件库** \> **操作系统** \> **启动" 图像**。

2.  选择 "**启动映像（x64）**"，然后选择 "**属性**"。

3.  选择 "**数据源**" 选项卡，然后**从启用 PXE 的分发点启用 "从启用 PXE 的分发点部署此启动映像"**。

4.  选择 "**可选组件**" 选项卡以安装所需组件：

    1.  选择星号图标，然后搜索**HTML （WinPE-HTA）**

    2.  选择 **"确定"** 将 HTML 应用程序支持添加到启动映像。

5.  *可选：* 若要自定义部署体验，请选择 "**自定义**" 选项卡。
    -   如果希望在部署期间有权访问命令提示符，请启用**命令支持（仅限测试）** 。 如果启用了此功能，你可以在部署期间随时选择**F8**来启动命令提示符。
    -   你还可以指定要在部署期间显示的自定义背景图像。 若要设置图像，请启用 "**指定自定义背景图像文件（UNC 路径"** 和 "选择你的背景"。

6.  当系统询问时，选择 **"是"** ，然后将更新后的启动映像分发到分发点。

有关详细信息，请参阅[通过 Configuration Manager 管理启动映像](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)。

> [!NOTE]
> 你可以创建可启动 USB 媒体，以针对没有 PXE 支持的环境启动基于配置管理器任务序列的部署。 可启动媒体仅包含启动映像、可选预启动命令及其所需的文件，以及配置管理器二进制文件以支持启动到 Windows PE 并连接到配置管理器以执行其余的部署过程。 有关详细信息，请参阅[创建可启动媒体](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。

## <a name="create-configuration-manager-packages"></a>创建 Configuration Manager 程序包

> [!IMPORTANT]
> 每个 SRS 安装程序版本所需的操作系统版本随每个 MSI 版本更改。 若要确定给定 MSI 的最佳操作系统版本，请运行一次控制台安装脚本。 若要了解详细信息，请参阅[使用 Microsoft 终结点配置管理器部署 Microsoft 团队聊天室](rooms-scale.md)。

配置管理器需要多个程序包来部署和配置 Microsoft 团队聊天室单元。

您需要创建和配置以下程序包，然后将它们分发到分配有分发点服务器角色的 Configuration Manager 站点系统。

| **程序包名称**                     | **类型**               | **说明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-SRS 应用程序包     | 软件包       | Microsoft 团队聊天室部署工具包的程序包                                      |
| SRS v2-Sysprep 程序包             | 软件包       | 用于配置 Microsoft 团队聊天室单元的自定义无人参与的程序包            |
| SRS v2-Set-SRSComputerName 程序包 | 软件包       | 用于 HTML 应用程序（HTA）的程序包在部署期间分配计算机名称    |
| SRS v2-配置 SRS 设置         | 软件包       | 用于配置 Microsoft 团队聊天室应用的部署的程序包                          |
| SRS v2-OS 更新程序包          | 软件包       | 用于部署强制操作系统更新的程序包                                      |
| SRS v2-根证书程序包    | 软件包       | 可选-用于部署根证书的程序包（对于域加入的设备不需要）  |
| SRS v2-Microsoft Monitoring Agent 程序包 | 软件包       | 可选-用于部署和配置 Microsoft Operations Management Suite 代理的程序包|
| SRS v2-WinPE 后台程序包    | 软件包       | 用于与启动映像一起使用的自定义背景图像的程序包                           |
| Windows 10 企业版                | 操作系统映像 | 操作系统安装文件（安装 .wim）的程序包                          |
| Surface Pro                          | 驱动程序包         | 适用于 Microsoft Surface Pro 的设备驱动程序和固件的程序包                     |
| Surface Pro 4                        | 驱动程序包         | 适用于 Microsoft Surface Pro 4 的设备驱动程序和固件的程序包                   |

有关详细信息，请参阅[Configuration Manager 中的程序包和程序](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。

### <a name="create-folders-for-the-package-source-files"></a>为程序包源文件创建文件夹

配置管理器要求程序包源文件在首次创建时和更新时组织在特定文件夹结构中。

在 Microsoft 终结点配置管理器管理中心网站或主网站上创建以下文件夹结构，或者在用于托管程序包源文件的服务器共享上创建以下文件夹结构：

-   SRS v2-Microsoft Monitoring Agent 程序包
-   SRS v2-OS 更新程序包
-   SRS v2-根证书程序包
-   SRS v2-Set-SRSComputerName 程序包
-   SRS v2-SRS 应用程序包
-   SRS v2-配置 SRS 设置
-   SRS v2-Sysprep 程序包
-   设备
    -   Surface Pro
    -   Surface Pro 4
-   操作系统
    -   Windows 10 企业版

> [!TIP]
> 你还可以[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)和使用 zip 文件，该文件包含要导入的程序包的文件夹结构、你需要使用的脚本和任务序列模板。

### <a name="create-the-monitoring-agent-package"></a>创建监视 agent 程序包

1. 从<https://go.microsoft.com/fwlink/?LinkId=828603>下载监视代理。

2. 通过打开命令提示符窗口并在命令提示符处输入**MMASetup-AMD64/c：** 将程序包解压缩到 " **SRS V2-Microsoft Monitoring Agent" 程序包**文件夹中。

3. 在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

4. 输入以下信息以创建程序包：

   - 名称<strong>： SRS v2-Microsoft Monitoring Agent 程序包</strong>

   - 制造商<strong>： Microsoft Corporation</strong>

   - 版本<strong>： 8.1.11081.0</strong> （输入下载的安装文件的版本）

   - 选中 "**此程序包包含源文件**" 复选框，输入 SRS v2 的路径 **-Microsoft Monitoring Agent 程序包**文件夹，然后选择 "**下一步**"。

5. 选择 "**不创建程序**"，然后选择 "**下一步**"。

6. 查看**确认设置**页面，然后选择 "**下一步**"。

7. 选择 "**关闭**"。

### <a name="create-the-operating-system-updates-package"></a>创建操作系统更新程序包

1. 在 " **SRS v2-OS 更新" 程序包**文件夹中，创建一个名为**Install-SRSv2-OS-Updates**的新 PowerShell 脚本。

2. 将下面的脚本复制到**Install-SRSv2-OS-Updates**脚本中。 或者，你也可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 Install-SRSv2-OS-Updates 脚本。
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. 将强制性的 Windows 更新包下载到同一文件夹中。
   > [!NOTE]
   > 发布本文时，只需[KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 。 选中 "[配置 Microsoft 团队聊天室" 控制台](console.md)，查看是否需要任何其他更新。

4. 在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

5. 输入以下信息以创建程序包：
   -   名称： **SRS v2-OS 更新程序包**
   -   制造商： **Microsoft Corporation**
   -   版本： **1.0.0**
   -   选中 "**此程序包包含源文件**" 复选框，输入**SRS V2-OS 更新程序包**文件夹的路径，然后选择 "**下一步**"。

6. 选择 "**不创建程序**"，然后选择 "**下一步**"。

7. 查看**确认设置**页面，然后选择 "**下一步**"。

8. 选择 "**关闭**"。

### <a name="create-the-root-certificate-package-optional"></a>创建根证书程序包（可选）

创建此程序包以分配不会加入 Active Directory 域的设备的根证书。 仅当满足下列两个条件时才创建此程序包：
-   你的部署包括本地 Lync 或 Skype for business 服务器。
-   Microsoft 团队房间单元配置为在工作组中工作，而不是域成员。

1.  将根证书复制到 " **SRS v2-根证书包**" 文件夹中。

2.  在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

3.  输入以下信息以创建程序包：
    -   名称： **SRS v2-根证书程序包**
    -   制造商：*你的组织的名称*
    -   版本： **1.0.0**
    -   选中 "**此程序包包含源文件**" 复选框，输入 " **SRS V2-根证书程序包**" 文件夹的路径，然后选择 "**下一步**"。

4.  选择 "**不创建程序**"，然后选择 "**下一步**"。

5.  查看**确认设置**页面，然后选择 "**下一步**"。

6.  选择 "**关闭**"。

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>创建 Microsoft 团队聊天室部署套件程序包

1.  从<https://go.microsoft.com/fwlink/?linkid=851168>下载最新版本的**Microsoft 团队会议室部署工具包**，并将其安装到工作站。

2.  将内容从**C：\\Program Files （x86）\\Skype 会议室系统部署工具包**复制到**srs v2-srs 应用程序包**文件夹。

3.  在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

4.  输入以下信息以创建程序包：
    -   名称： **srs v2 – Srs 应用程序包**
    -   制造商： **Microsoft Corporation**
    -   版本： **3.1.104.0** （输入下载的安装文件的版本）
    -   选中 "**此程序包包含源文件**" 复选框，输入**SRS V2-srs 应用程序包**文件夹的路径，然后选择 "**下一步**"。
5.  选择 "**不创建程序**"，然后选择 "**下一步**"。

6.  查看**确认设置**页面，然后选择 "**下一步**"。

7.  选择 "**关闭**"。

### <a name="create-the-computer-name-assignment-package"></a>创建计算机名称分配包

1.  在 " **SRS V2 SRSComputerName 包**" 文件夹中，创建名为**SET-SRSCOMPUTERNAME**的新 HTML 应用程序。

2.  将以下脚本复制到**Set-SRSComputerName**文件中。 或者，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 Set-SRSComputerName 文件。
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

4.  输入以下信息以创建程序包：

    -   名称： **SRS v2-Set-SRSComputerName 程序包**

    -   制造商： **Microsoft Corporation**

    -   版本： **1.0.0**

    -   选中 "**此程序包包含源文件**" 复选框，输入**SRS v2 SRSComputerName 程序包**文件夹的路径，然后选择 "**下一步**"。

5.  选择 "**不创建程序**"，然后选择 "**下一步**"。

6.  查看**确认设置**页面，然后选择 "**下一步**"。

7.  选择 "**关闭**"。

### <a name="create-the-sysprep-package"></a>创建 Sysprep 程序包

1. 在**SRS v2-Sysprep 程序包**文件夹中，创建名为**UNATTEND.XML**的新 XML 文件。

2. 将以下文本复制到**unattend.xml**文件中。 或者，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 unattend.xml 文件。
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. 在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

4. 输入以下信息以创建程序包：
   -   名称： **SRS v2-Sysprep 程序包**
   -   制造商： **Microsoft Corporation**
   -   版本： **1.0.0**
   -   选中 "**此程序包包含源文件**" 复选框，输入 SRS v2 的路径 **-"Sysprep 程序包**" 文件夹，然后选择 "**下一步**"。
5. 选择 "**不创建程序**"，然后选择 "**下一步**"。

6. 查看**确认设置**页面，然后选择 "**下一步**"。

7. 选择 "**关闭**"。

### <a name="create-the-windows-10-enterprise-package"></a>创建 Windows 10 企业版程序包

1.  获取 Windows 10 企业版 x64 媒体，并将**install**文件复制到**操作系统\\Windows 10 企业版**文件夹。

2.  在 Configuration Manager 控制台中，转到 "**软件库** \> **操作系统** \> "**操作系统映像**，然后选择 "**添加操作系统映像**"。

3.  指定刚复制的**install**文件的路径，然后选择 "**下一步**"。

4.  将 "**版本**" 字段更新为与 Windows 10 企业版映像的内部版本号相匹配，然后选择 "**下一步**"。

5.  查看 "**详细信息**" 页面，然后选择 "**下一步**"。

6.  选择 "**关闭**"。

有关详细信息，请参阅[通过 Configuration Manager 管理 OS 映像](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)。

### <a name="create-surface-pro-device-driver-packages"></a>创建 Surface Pro 设备驱动程序包

Surface Pro 和 Surface Pro 4 均支持 Microsoft 球队会议室。 您需要为环境中的每个 Surface Pro 模型创建一个驱动程序包。

> [!IMPORTANT]
> 驱动程序必须与 Windows 10 企业版内部版本和 Microsoft 团队聊天室部署工具包版本兼容。 有关详细信息，请参阅[下载 Surface 设备的最新固件和驱动程序](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)和[配置控制台](console.md)。

1.  下载最新的驱动程序和固件。
    -   对于 Surface Pro：<https://www.microsoft.com/download/details.aspx?id=55484>
    -   对于 Surface Pro 4：<https://www.microsoft.com/download/details.aspx?id=49498>

2.  提取已下载的驱动程序和固件。 打开命令提示符窗口，在命令提示符处输入以下命令之一：
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  在 Configuration Manager 控制台中，转到 "**软件库** \> **操作系统** \> **驱动程序**"，然后选择 "**导入驱动程序**"。

4.  选择 **"导入以下网络路径（UNC）中的所有驱动程序**"，选择源文件夹（例如，\\C\\：\\_Sources 驱动 Surface Pro），然后选择 "**下一步**"。

5.  在 "**指定导入的驱动程序的详细信息**" 页面上，选择列出的所有驱动程序，然后选择 "**启用这些驱动程序并允许计算机安装它们**"。

6.  选择 "**类别**"，创建与曲面模型相匹配的新类别，选择 **"确定**"，然后选择 "**下一步**"。

7.  选择 "**新建程序包**"。

8.  指定与 Surface Pro 模型相匹配的程序包名称，输入用于存储驱动程序包文件的文件夹路径，选择 **"确定**"，然后选择 "**下一步**"。

9.  在 "**启动映像**" 页面上，确保未选中任何启动映像，然后选择 "**下一步**"。

10. 选择 "**关闭**"。

11. 转到 "**软件库** \> **操作系统** \> **驱动程序**"，选择 "**文件夹\>创建文件夹**"，然后输入与您刚为其导入驱动程序的 Surface Pro 模型相匹配的文件夹名称。

12. 将所有导入的驱动程序移动到新创建的文件夹，以便更轻松地进行导航和操作。

> [!NOTE]
> 对您可能拥有的其他 Surface Pro 模型重复相同步骤。 有关详细信息，请参阅[在 Configuration Manager 中管理驱动程序](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>创建 Microsoft 团队聊天室配置包

1.  在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> **程序包**"，然后选择 "**创建程序包**"。

2.  输入以下信息以创建程序包：

    -   名称： **SRS v2-配置 SRS 安装程序包**

    -   制造商： **Microsoft Corporation**

    -   版本： **1.0.0**

    -   选中 "**此程序包包含源文件**" 复选框，输入 SRS v2 的路径 **-"配置 srs 设置**" 文件夹，然后选择 "**下一步**"。

3.  选择 "**不创建程序**"，然后选择 "**下一步**"。

4.  查看**确认设置**页面，然后选择 "**下一步**"。

5.  选择 "**关闭**"。



## <a name="distribute-configuration-manager-packages"></a>分发 Configuration Manager 程序包

必须将所有程序包分发到在 Configuration Manager 层次结构中分配有分发点角色的服务器。 按照以下说明启动软件包分发。

1.  分发软件包。

    1.  在 Configuration Manager 控制台中，转到 "**软件库** \> **应用程序管理** \> "**程序包**。 选择要分发的所有软件包，然后选择 "**分发内容**"。

    2.  查看程序包列表，然后选择 "**下一步**"。

    3.  将所有分发点服务器（或分发点组，具体取决于您的 Configuration Manager 层次结构）添加到列表，然后选择 "**下一步**"。

    4.  选择 "**下一步**"，然后选择 "**关闭**"。

2.  分发驱动程序包。

    1.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **驱动程序包**。 选择要分发的所有驱动程序包，然后选择 "**分发内容**"。

    2.  查看程序包列表，然后选择 "**下一步**"。

    3.  将所有分发点服务器（或分发点组，具体取决于您的 Configuration Manager 层次结构）添加到列表，然后选择 "**下一步**"。

    4.  选择 "**下一步**"，然后选择 "**关闭**"。

3.  分发操作系统程序包。

    1.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \>的操作系统**映像**。 选择要分发的所有操作系统映像，然后选择 "**分发内容**"。

    2.  查看程序包列表，然后选择 "**下一步**"。

    3.  将所有分发点服务器（或分发点组，具体取决于您的 Configuration Manager 层次结构）添加到列表，然后选择 "**下一步**"。

    4.  选择 "**下一步**"，然后选择 "**关闭**"。

> [!NOTE]
> 程序包分发可能需要一些时间，具体取决于程序包大小、Configuration Manager 层次结构、分发点服务器数以及网络中可用的带宽。
> 
> 必须先分发所有程序包，然后才能开始部署 Microsoft 团队聊天室单元。
> 
> 你可以通过转到**监视** \> **分发状态** \> **内容状态**来查看 Configuration Manager 控制台中程序包分发的状态。

## <a name="configuration-manager-task-sequences"></a>配置管理器任务序列

使用 "配置管理器" 的任务序列自动执行将操作系统映像部署到目标计算机的步骤。 若要以自动方式部署 Microsoft 团队会议室，请创建一个任务序列，该序列引用用于启动目标 Microsoft 团队聊天室计算机的启动映像、要安装的 Windows 10 企业操作系统映像以及其他任何其他内容（如其他应用程序或软件更新）。

### <a name="import-the-sample-task-sequence"></a>导入示例任务序列

你可以下载并轻松导入示例任务序列，并对其进行自定义以满足你的需求。

1.  [**下载**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)示例任务序列，并将下载的 zip 文件复制到共享位置。
2.  在 Configuration Manager 控制台中，转到 "**软件库** \> **操作系统** \> "**任务序列**，然后选择 "**导入任务序列**"。

3.  选择 "**浏览**"，转到步骤1中使用的共享文件夹位置，选择 " **Microsoft 团队聊天室部署（en-us） .zip** " 文件，然后选择 "**下一步**"。

4.  将**操作**设置为 "**新建**"，然后选择 "**下一步**"。

5.  确认设置，然后选择 "**下一步**"。

6.  选择 "**关闭**"。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>验证引用程序包是否正确链接到每个任务序列步骤。

1. 选择导入的任务序列，然后选择 "**编辑**"。

    任务序列编辑器随即打开，并显示部署和配置 Microsoft 团队聊天室单元所需的每个连续步骤。

2. 演练每个步骤并完成推荐的更新：

   1. **在 WINDOWS PE 中重启**：此步骤将重新启动，然后将计算机启动到 Windows PXE。 此步骤不需要任何更改。

   2. **分区磁盘 0-UEFI**：此步骤将擦除磁盘配置，并基于已配置的设置创建分区。 我们建议您不要对此步骤进行任何更改。

   3. **设置 SRS 计算机名**：此步骤包括一个 HTML 应用程序，用于在部署期间提供用于为 Microsoft 团队聊天室单元设置计算机名称的 UI。
      -  这是一个可选步骤，但仅当你希望通过备用进程管理计算机命名时，才可以禁用它。
      -  验证是否已选中 " **SRS v2-SRSComputerName** " 程序包。 如果不是，请浏览到程序包并将其选中。

   4. **应用操作系统**：此步骤指定要部署的操作系统映像和要使用的无人参与 Sysprep 应答文件。
      -  验证是否选择了正确的 Windows 10 企业操作系统映像文件。
      -  验证是否已启用 "**为自定义安装使用无人参与或 Sysprep 应答文件**"，并选中 " **SRS V2-sysprep 程序包**"。 此外 **，请确保文件名设置**为**unattend.xml**。

   5. **应用 Windows 设置**：此步骤收集有关 Windows 安装的信息。
      -  提供授权和注册信息，包括产品密钥、本地管理员帐户密码和时区（取决于你的需要）。

   6. **应用网络设置**：此步骤允许你指定工作组或 Active Directory 域名和组织单位。
      > [!NOTE]
      > 请参阅[Skype 会议室系统域加入](domain-joining-considerations.md)有关建议操作的注意事项，在部署 Microsoft 团队聊天室单元作为 Actve Directory 域的成员时需要执行此操作。
   7. **应用驱动程序：** 此步骤及其子步骤用于基于你所拥有的 Surface Pro 模型部署适用的设备驱动程序和固件。 更新每个步骤以指定与此部署关联的相关驱动程序包。
      -   每个驱动程序包都配置为利用 Windows Management Instrumentation （WMI）筛选器，根据 Surface Pro 和 model 部署相关的驱动程序和固件。
      -   我们强烈建议您不要更改这些驱动程序的配置，否则部署可能会失败。

   8. **设置 Windows 和配置管理器**：此步骤可部署和配置 Configuration Manager 客户端。 更新此步骤以指定内置的 Configuration Manager 客户端包。

   9. **安装根证书**：此步骤为非域加入的设备分发根证书，因此默认情况下为可选和禁用。
      -   如果需要将根证书部署到 Microsoft 团队聊天室单元，请启用此步骤。
      -   如果确实需要执行此步骤，请验证**SRS v2 –根证书程序包**和 "**禁用64位文件系统重定向**" 是否已选中。

   10. **安装和配置监视代理**：此步骤安装64位版本的 Microsoft Azure 监视器代理并将代理配置为连接到 Log Analytics 工作区。
       -   此步骤默认情况下处于禁用状态。 只有当你要使用监视 Agent 监视 Microsoft 团队会议室的运行状况时，才启用此步骤。
       -   编辑此步骤并更新命令行参数以指定你的**工作区 ID**和**工作区密钥**。
       -   有关获取 Operations Management Suite 工作区 ID 和主键的详细信息，请参阅[配置 Azure 监视的测试设备](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)。
       -   验证**SRS v2-Microsoft Monitoring Agent 程序包**和 "**禁用64位文件系统重定向**" 是否已选中。
       -   有关监视 Microsoft 团队聊天室部署的运行状况的详细信息，请参阅通过[azure 监视器规划 Microsoft 团队会议室管理](azure-monitor-plan.md)、通过[Azure 监视器部署 microsoft 团队聊天室管理](azure-monitor-deploy.md)和[利用 Azure 监视器管理 Microsoft 团队聊天室设备](azure-monitor-manage.md)。

   11. **复制 SRS V2 配置文件**：此步骤将所需的设置和配置文件从 Microsoft 团队聊天室部署工具包复制到本地硬盘。 此步骤不需要自定义。
       -   验证**srs v2 – Srs 应用程序包**和 "**禁用64位文件系统重定向**" 是否已选中。

   12. **安装-SRSv2-OS-更新**：此步骤将部署 Microsoft 团队聊天室部署所需的任何必需的操作系统更新。 执行以下操作：
       -   选中 "[配置 Microsoft 团队聊天室" 控制台](console.md)以查看需要哪些更新。
       -   验证**SRS v2-OS 更新程序包**中是否包含所有必需的更新。
       -   验证 " **SRS v2-OS 更新" 程序包**是否已选中。
       -   验证是否已将 PowerShell 执行策略设置为 "**回避**"。

   13. **重新启动计算机**：此步骤会在安装必需的操作系统更新后重新启动计算机。 此步骤不需要自定义。

   14. **配置 Windows 组件**：此步骤配置所需的 Windows 功能。 此步骤不需要自定义。

   15. **重新启动计算机**：此步骤将在配置 Windows 功能后重新启动计算机。 此步骤不需要自定义。

   16. **添加本地 Skype 用户**：此步骤创建用于自动登录 Windows 和启动 Microsoft 球队聊天室应用程序的本地 skype 帐户。 此步骤没有与之关联的任何软件包，并且不需要进行自定义。

   17. **设置和配置 SRS 应用程序**：此步骤为操作系统的下一次启动配置 Microsoft 团队聊天室应用程序安装。
       -   验证**srs v2-"配置 Srs 安装程序包**" 和 "**禁用64位文件系统重定向**" 是否已选中。

> [!IMPORTANT]
> 任务序列步骤必须按所提供的顺序排列，这一点非常重要。 修改步骤顺序或配置其他步骤可能会中断部署。
>
> **设置和配置 SRS 应用程序**步骤必须是任务序列中的最后一步，否则部署可能失败。

### <a name="create-deployment-for-the-task-sequence"></a>为任务序列创建部署

1. 选择任务序列，然后选择 "**部署**"。

2. 选择 "**浏览**"，选择要部署的目标集合。

3. 选择 "**所有未知计算机**"，然后选择 **"确定"**。

4. 选择 "**下一步**"。

5. 在 "**用途**" 下拉列表中选择 "**可用**"。

6. 仅在 "**可用于以下**列表" 列表中选择 "**媒体和 PXE** "，然后选择 "**下一步**"。
   > [!WARNING]
   > 将 "**用途**" 设置为 "**可用**" 非常重要。 请确保 "**用途**"**未**设置为 "**必需**"。 此外，请确保仅选择 "在**以下情况下可用**的**媒体和 PXE** "。
   >
   > 将这些值设置为其他值可能会导致所有计算机在引导时获得 Microsoft 团队会议室部署映像。
7. 不要指定任何计划，然后选择 "**下一步**"。

8. 不要更改 "**用户体验**" 部分中的任何内容，然后选择 "**下一步**"。

9. 不要更改 "**通知**" 部分中的任何内容，然后选择 "**下一步**"。

10. 不要更改 "**分发点**" 部分中的任何内容，然后选择 "**下一步**"。

11. 确认设置，然后选择 "**下一步**"。

12. 选择 "**关闭**"。

<a name="validate-and-troubleshoot-the-solution"></a>验证和解决解决方案
--------------------------------------

完成 Microsoft 终结点配置管理器任务序列后，需要执行测试运行以验证任务序列是否可以部署和配置 Microsoft 团队会议室单元。

1.  使用受支持的以太网适配器之一或使用 Surface dock 将测试设备连接到有线网络。 如果尚未针对你的环境配置 PXE 启动功能，你可以使用[之前创建](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media)的 usb 闪存驱动器上的启动映像从 usb 启动并连接到 Configuration Manager。

2.  访问固件并启动 PXE 启动：

    1.  确保已关闭 Surface 设备电源。

    2.  按住**音量**按钮。

    3.  按下并释放 "**电源**" 按钮。

    4.  在设备开始启动后，释放 "**音量**" 按钮。

    5.  选择 "**启动配置**"。

    6.  执行下列操作之一：

        -   选择 " **PXE 启动**"，然后将其拖动到列表顶部。 或者，你可以在网络适配器上向左轻扫以立即启动到设备。 这不会影响启动顺序。
        -   选择包含启动媒体的 u 盘。

3.  选择 "**退出**"，然后选择 "**立即重启**"。

4.  出现提示时，选择 "**输入**网络启动服务"。

5.  Windows PE 将加载到内存中，任务序列向导将启动。 选择 "**下一步**" 继续。

6.  选择之前导入的任务序列，然后选择 "**下一步**"。

7.  在应用磁盘配置后，系统将提示你为设备指定计算机名称。 用户界面将根据 Surface Pro 设备的序列号显示推荐的计算机名称。 你可以接受建议的名称，也可以指定一个新名称。 按照 "计算机名称分配" 屏幕上的说明进行操作。 选择 "**接受**" 时，将开始部署。

8.  部署过程的其余部分是自动完成的，不会询问更多用户输入。

9.  部署任务序列完成配置设备后，你将看到以下配置屏幕，该屏幕要求你配置 Microsoft 团队聊天室应用程序设置。

    ![Microsoft 团队聊天室应用程序的初始设置屏幕](../media/room-systems-scale-image2.png)

10.  将 Surface Pro 插入 Microsoft 团队聊天室控制台，然后配置应用程序设置。

11.  验证[Microsoft 团队聊天室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能是否帮助正在使用部署的设备。


若要解决安装失败的问题，请检查**SMSTS**文件，该文件将记录配置管理器任务序列中执行的所有步骤。

SMSTS 文件存储在多条路径中，具体取决于生成过程的阶段。 检查下表以标识 SMSTS 文件的路径。


| **部署阶段**                                                            | **任务序列日志路径**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| 在 HDD 格式之前的 WinPE                                                        | X：\\Windows\\Temp\\smstslog\\smsts             |
| 在 HDD 格式后进行 WinPE                                                         | C：\\_SMSTaskSequence\\日志\\Smstslog\\smsts    |
| 在安装 Configuration Manager 代理之前已部署操作系统 | c：\\_SMSTaskSequence\\日志\\Smstslog\\smsts    |
| 操作系统和配置管理器代理已部署                   | % windir%\\System32\\ccm\\log\\Smstslog\\smsts |
| 任务序列执行完成                                                | % windir%\\System32\\ccm\\\\smsts 日志           |

> [!TIP]
> 你可以在任务序列期间随时选择**F8**以打开命令控制台，然后获取对 SMSTS 文件的访问权限。

若要解决 PXE 启动问题，请检查 Configuration Manager 服务器上特定于 PXE 操作的两个日志文件：

-   **Pxecontrol**，位于 Configuration Manager 安装日志目录中

-   **Smspxe**，位于 Configuration Manager 管理点（MP）日志目录中

有关可用于进一步对 Configuration Manager 安装进行故障排除的日志文件的完整列表，请参阅 Microsoft 终结点配置管理器[日志文件参考](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)。
