---
title: 使用 System Center Configuration Manager 部署 Skype 会议室系统
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读此主题以了解有关部署在大型部署的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 3602422779a405376893a3a7e6663520ed6a4a4c
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210871"
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a>使用 System Center Configuration Manager 部署 Skype 会议室系统 v2

本文为您提供了所有必要的信息以创建 Skype 会议室系统 v2 部署通过使用 System Center Configuration Manager。

与提供的 System Center Configuration Manager 中的简单易用的方法，您可以部署操作系统和其他应用程序到多个目标设备。

使用指导您完成您的配置管理器配置，如下所示的方法和自定义的示例包和脚本提供整个本指南中，根据需要为您的组织。

![使用 Configuration Manager Skype 会议室系统 v2 部署过程](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 仅基于 Surface Pro 部署已测试此解决方案。 按照配置非基于 Surface Pro 的制造商的指南。

## <a name="validate-prerequisites"></a>验证先决条件

若要部署 Skype 会议室系统 v2 使用配置管理器中，确保您满足以下先决条件和要求。

### <a name="system-center-configuration-manager-requirements"></a>System Center Configuration Manager 要求

-   System Center Configuration Manager 版本必须至少 1706年或以上。 我们建议使用 1710年或更高版本。 签出[System Center Configuration Manager 中支持的 10 Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)若要了解有关配置管理器支持的 Windows 10 版本。

-   必须安装 Windows 评估和部署工具包 (ADK) Windows 10 的受支持的版本。 请参阅[Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) ，您可以使用不同版本的配置管理器中，并确保您的部署包括正确版本的版本。

-   网站系统服务器必须已分配了分发点角色，并应[启动前执行环境 (PXE) 支持](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)启用网络启动部署为其启用启动映像。 如果没有启用 PXE 支持，可以将[引导介质](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用于您的部署。

-   网络访问帐户必须被配置为支持新的计算机 （裸机） 部署方案。 若要了解更多有关配置的网络访问帐户，请参阅[管理帐户以访问 System Center Configuration Manager 中的内容](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

-   我们建议您启用[多播的支持](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)，如果您可能要将相同的 Skype 会议室系统 v2 图像同时部署到多个单位。

### <a name="networking-requirements"></a>网络要求

-   您的网络应该有一个动态主机配置协议 (DHCP) 服务器，配置为自动的 IP 地址分发到将在其中部署 Skype 会议室系统 v2 单位子网。

    > [!NOTE]
    > DHCP 租约持续时间必须设置为超过图像部署持续时间值。 否则，部署可能会失败。

-   应将您的网络，包括开关和虚拟 Lan (Vlan) 配置为支持 PXE。 请参阅您的网络供应商有关 IP 帮助程序和 PXE 配置的详细信息。 或者，您可以使用[可启动媒体](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)对于您的部署，如果 PXE 支持未启用。

    > [!NOTE]
    > 为 Surface Pro 时使用以太网适配器或 Microsoft 从扩展坞，仅支持设备，从网络 （PXE 启动） 引导。 第三方以太网适配器不支持与 Surface Pro PXE 启动。 有关详细信息，请参阅[以太网适配器和表面的部署](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)。

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>配置操作系统部署 System Center Configuration Manager

本文假定您已有的正常运行的 System Center Configuration Manager 部署，并不需要部署和配置配置管理器从零开始的所有步骤的详细信息。 [文档和配置指南](https://docs.microsoft.com/sccm/)在 System Center Configuration Manager 是很好的资源;我们建议您与这些资源开始如果您尚未尚未部署配置管理器。

以下说明用于验证正确配置了操作系统部署 (OSD) 功能。

### <a name="validate-and-upgrade-configuration-manager"></a>验证并升级配置管理器

1.  在 Configuration Manager 控制台中，转到**管理** \> **更新和服务**。

2.  检查安装的生成和适用您尚未安装程序的更新。

3.  查看[支持 Windows 10 中 System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client);如果您需要升级部署，请选择您想要安装的更新，然后选择**下载**。

4.  下载完毕后，选择更新，，然后选择**安装更新包**。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>配置为支持 PXE 和多播的分发点

1.  在 Configuration Manager 控制台中，转到**管理** \> **分发点**。

2.  选择分发点服务器，将提供 Skype 会议室系统 v2 部署中，然后选择**属性**。

3.  选择**PXE**选项卡，并确保启用了以下设置：
    -   启用 PXE 支持的客户端
    -   允许对传入 PXE 请求做出响应此分发点
    -   启用未知的计算机支持

4.  *可选：* 若要启用多播的支持，选择**多播**选项卡，并确保启用了以下设置：
    -   启用多播同时将数据发送到多个客户端
    -   配置根据您的网络团队建议的 UDP 端口范围

### <a name="configure-the-network-access-account"></a>配置网络访问帐户

1.  在 Configuration Manager 控制台中，转到**管理** \> **站点配置** \> **网站**，然后选择网站。

2.  在**设置**组中，选择**配置网站组件** \> **软件分发**。

3.  选择**网络访问帐户**选项卡设置备份一个或多个帐户和然后选择**确定**。

> [!NOTE]
> 帐户无需任何特殊权限，**从网络访问此计算机**右在分发点服务器除外。 通用域用户帐户将适用。 有关详细信息，请参阅[管理帐户以访问 System Center Configuration Manager 中的内容](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

### <a name="configure-a-boot-image"></a>配置启动映像

1.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **启动映像**。

2.  选择**启动映像 (x64)**，，，然后选择**属性**。

3.  选择**数据源**选项卡，并启用**部署从 PXE 启用分发点此启动映像**。

4.  选择**可选组件**选项卡安装所需的组件：

    1.  选择星形图标，然后搜索为**HTML (WinPE HTA)**

    2.  选择**确定**将 HTML 中的应用程序支持添加到启动映像。

5.  *可选：* 若要自定义部署体验，请选择**自定义**选项卡。
    -   如果您想要在部署过程中有权访问命令提示符下的，启用**命令支持 （仅测试）** 。 启用后，您可以通过在部署期间随时选择**F8**启动命令提示符。
    -   您还可以指定在部署过程中显示自定义背景图像。 若要设置图像，启用**指定自定义背景图像文件 (UNC 路径**，然后选择您的背景。

6.  当出现提示，请选择**是**和分发到分发点更新的启动映像。

有关详细信息，请参阅[管理启动映像使用 System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)。

> [!NOTE]
> 您可以创建可引导 USB 介质启动配置管理器没有 PXE 支持的环境的任务序列基于部署。 可引导介质只包含启动映像、 可选 prestart 命令和其所需的文件和配置管理器二进制文件以支持到 Windows PE 启动，连接到配置管理器中的部署过程的其余部分。 有关详细信息，请参阅[如何创建可引导介质](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。

## <a name="create-configuration-manager-packages"></a>创建配置管理器包

配置管理器需要大量的包来部署和配置的 Skype 会议室系统 v2 单位。

您需要创建并配置了下列程序包，然后将它们分发到配置管理器网站系统已分配了分发点服务器角色。

| **程序包名称**                     | **类型**               | **说明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SR v2-SR 应用程序包     | 软件包       | 包 Skype 会议室系统 v2 部署工具包                                      |
| SR v2-Sysprep 包             | 软件包       | 自定义 Unattended.xml 配置 Skype 会议室系统 v2 单位包            |
| SR v2-设置 SRSComputerName 包 | 软件包       | 要在部署过程中指定计算机名称的 HTML 应用程序 (HTA) 包    |
| SR v2-配置 SR 安装程序         | 软件包       | 要配置的 Skype 会议室系统 v2 应用程序部署包                          |
| SR v2-操作系统更新包          | 软件包       | 包来部署必需的操作系统更新                                      |
| SR v2-根证书包    | 软件包       | 可选-包来部署 （不需要加入域的单位） 的根证书  |
| SR v2-Microsoft OMS 代理包 | 软件包       | 可选-包来部署和配置 Microsoft 操作管理套件代理|
| SR v2-WinPE 背景包    | 软件包       | 自定义背景图像用于启动映像包                           |
| Windows 10 Enterprise                | 操作系统映像 | 操作系统安装文件 (install.wim) 包                          |
| Surface Pro                          | 驱动程序包         | 设备驱动程序和用于 Microsoft Surface Pro 固件软件包                     |
| Surface Pro 4                        | 驱动程序包         | 设备驱动程序和 Microsoft Surface Pro 4 的固件软件包                   |

有关详细信息，请参阅[包和程序 System Center Configuration Manager 中](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)。

### <a name="create-folders-for-the-package-source-files"></a>创建源文件的程序包的文件夹

配置管理器需要程序包源文件，它们首次创建时，它们更新的时间来组织特定的文件夹结构中。

或到主机包源文件正在使用的服务器共享的 System Center Configuration Manager 管理中心网站或主站点上创建以下文件夹结构：

-   SR v2-Microsoft OMS 代理包
-   SR v2-操作系统更新包
-   SR v2-根证书包
-   SR v2-设置 SRSComputerName 包
-   SR v2-SR 应用程序包
-   SR v2-配置 SR 安装程序
-   SR v2-Sysprep 包
-   驱动程序
    -   Surface Pro
    -   Surface Pro 4
-   操作系统
    -   Windows 10 Enterprise

> [!TIP]
> 您还可以[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)和使用包括包，您需要使用，这些脚本和任务序列模板，您需要导入的文件夹结构的 zip 文件。

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a>创建 Microsoft 操作管理套件代理包

1. 下载操作管理套件 X-64 代理从<https://go.microsoft.com/fwlink/?LinkId=828603>。

2. 通过打开命令提示符窗口并在命令提示符处输入**MMASetup AMD64.exe 无**程序包解压缩到**SR v2-Microsoft OMS 代理包**文件夹中。

3. 在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

4. 输入以下信息以创建包：

   - 名称<strong>: SR v2-Microsoft OMS 代理包</strong>

   - 制造商<strong>: Microsoft Corporation</strong>

   - 版本<strong>: 8.1.11081.0</strong> （输入下载的安装文件的版本）

   - 选择**此程序包包含源文件**复选框、 **SR v2-Microsoft OMS 代理包**文件夹中，输入的路径，然后选择**下一步**。

5. 选择**不创建程序**，然后选择**下一步**。

6. 查看**确认的设置**页，然后选择**下一步**。

7. 选择**关闭**。

### <a name="create-the-operating-system-updates-package"></a>创建操作系统更新包

1. 在**SR v2-操作系统更新程序包**文件夹中，创建名为**安装 SRSv2 OS Updates.ps1**新的 PowerShell 脚本。

2. 将以下脚本复制到**安装 SRSv2 OS Updates.ps1**脚本。 或者，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载该安装 SRSv2 OS Updates.ps1 脚本。
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
3. 下载到同一文件夹的必需的 Windows 更新程序包。
   > [!NOTE]
   > 在发布本文时，仅[KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)是必需的。 检查[配置 Skype 会议室系统 v2 控制台](console.md)，请参阅是否需要其他任何更新。

4. 在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

5. 输入以下信息以创建包：
   -   名称： **SR v2 – 操作系统更新包**
   -   制造商： **Microsoft Corporation**
   -   版本： **1.0.0**
   -   选择**此程序包包含源文件**复选框、 **SR v2-操作系统更新程序包**文件夹中，输入的路径，然后选择**下一步**。

6. 选择**不创建程序**，然后选择**下一步**。

7. 查看**确认的设置**页，然后选择**下一步**。

8. 选择**关闭**。

### <a name="create-the-root-certificate-package-optional"></a>创建根证书包 （可选）

创建此程序包分发不会加入 Active Directory 域的设备的根证书。 创建此包，仅当以下条件适用：
-   您的部署包括本地 Lync 或 Skype 业务服务器。
-   Skype 会议室系统 v2 单位配置为用于在工作组中而不是域成员。

1.  将根证书复制到**SR v2 – 根证书程序包**文件夹。

2.  在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

3.  输入以下信息以创建包：
    -   名称： **SR v2 – 根证书包**
    -   制造商：*贵组织的名称*
    -   版本： **1.0.0**
    -   选择**此程序包包含源文件**复选框、 **SR v2 – 根证书程序包**文件夹中，输入的路径，然后选择**下一步**。

4.  选择**不创建程序**，然后选择**下一步**。

5.  查看**确认的设置**页，然后选择**下一步**。

6.  选择**关闭**。

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a>创建 Skype 会议室系统 v2 部署套件包

1.  下载最新版本的**Skype 会议室系统 v2 部署工具包**从<https://go.microsoft.com/fwlink/?linkid=851168>，并将其安装到工作站。

2.  复制从内容**c:\\Program Files (x86)\\Skype 会议室系统部署工具包** **SR v2-SR 应用程序包**文件夹。

3.  在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

4.  输入以下信息以创建包：
    -   名称： **SR v2 – SR 应用程序包**
    -   制造商： **Microsoft Corporation**
    -   版本： **3.1.104.0** （输入下载的安装文件的版本）
    -   选择**此程序包包含源文件**复选框、 **SR v2 – SR 应用程序包**文件夹中，输入的路径，然后选择**下一步**。
5.  选择**不创建程序**，然后选择**下一步**。

6.  查看**确认的设置**页，然后选择**下一步**。

7.  选择**关闭**。

### <a name="create-the-computer-name-assignment-package"></a>创建计算机名称分配包

1.  在**SR v2-设置 SRSComputerName 程序包**文件夹中，创建名为**集 SRSComputerName.hta**新 HTML 应用程序。

2.  将以下脚本复制到**集 SRSComputerName.hta**文件。 此外，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载设置 SRSComputerName.hta 文件。
    ```
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
3.  在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

4.  输入以下信息以创建包：

    -   名称： **SR v2-设置 SRSComputerName 包**

    -   制造商： **Microsoft Corporation**

    -   版本： **1.0.0**

    -   选择**此程序包包含源文件**复选框、 **SR v2-设置 SRSComputerName 程序包**文件夹中，输入的路径，然后选择**下一步**。

5.  选择**不创建程序**，然后选择**下一步**。

6.  查看**确认的设置**页，然后选择**下一步**。

7.  选择**关闭**。

### <a name="create-the-sysprep-package"></a>创建 Sysprep 包

1. 在**SR v2 – Sysprep 程序包**文件夹中，创建名为**Unattend.xml**的新 XML 文件。

2. 将以下文本复制到**Unattend.xml**文件。 此外，您可以从[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下载 Unattend.xml 文件。
   ```
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
3. 在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

4. 输入以下信息以创建包：
   -   名称： **SR v2-Sysprep 包**
   -   制造商： **Microsoft Corporation**
   -   版本： **1.0.0**
   -   选择**此程序包包含源文件**复选框、 **SR v2 – Sysprep 程序包**文件夹中，输入的路径，然后选择**下一步**。
5. 选择**不创建程序**，然后选择**下一步**。

6. 查看**确认的设置**页，然后选择**下一步**。

7. 选择**关闭**。

### <a name="create-the-windows-10-enterprise-package"></a>创建 Windows 10 Enterprise 包

1.  获取 Windows 10 Enterprise x64 媒体，并复制到**install.wim**文件**操作系统\\Windows 10 Enterprise**文件夹。

2.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **操作系统映像**和然后选择**添加操作系统映像**。

3.  指定您刚复制的**install.wim**文件的路径，然后选择**下一步**。

4.  更新**版本**字段匹配的 Windows 10 Enterprise 图像，内部版本号，然后选择**下一步**。

5.  查看**详细信息**页上，然后选择**下一步**。

6.  选择**关闭**。

有关详细信息，请参阅[管理操作系统映像使用 System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)。

### <a name="create-surface-pro-device-driver-packages"></a>创建 Surface Pro 设备驱动程序包

Skype 会议室系统 v2 支持 Surface Pro 和 Surface Pro 4。 您需要创建已在您的环境中每个 Surface Pro 模型驱动程序包。

> [!IMPORTANT]
> 驱动程序必须与 Windows 10 Enterprise 生成和 Skype 会议室系统 v2 部署套件版本兼容。 有关详细信息，请参阅[下载最新的固件和呈现设备的驱动程序](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)和[Configure 控制台](console.md)。

1.  下载最新驱动程序和固件。
    -   为 Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   为 Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  提取下载的驱动程序和固件。 打开命令提示符窗口并在命令提示符处，输入以下命令之一：
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **驱动程序**，然后选择**导入驱动程序**。

4.  选择**导入以下网络路径 (UNC) 中的所有驱动程序**中，选择源文件夹 (例如，c:\\_Sources\\驱动程序\\Surface Pro)，然后选择**下一步**。

5.  在**指定的导入的驱动程序的详细信息**页上，选择所有列出驱动程序，，然后选择**启用这些驱动程序并允许进行安装的计算机**。

6.  选择**类别**，创建新类别相匹配的表面模型，选择**确定**，，然后选择**下一步**。

7.  选择**新程序包**。

8.  指定与 Surface Pro 模型匹配的软件包名称，请输入文件夹路径以存储驱动程序包文件中的，选择**确定**，然后选择**下一步**。

9.  在**启动映像**页上，确保没有启动映像选择，然后选中**下一步**。

10. 选择**关闭**。

11. 转到**软件库** \> **操作系统** \> **驱动程序**，选择**文件夹\>创建文件夹**，并输入一个文件夹名称相匹配的 Surface Pro 模型的您刚才导入的驱动程序。

12. 将所有已导入的驱动程序移动到新创建的文件夹，以便于导航和操作。

> [!NOTE]
> 对其他 Surface Pro 模型，您可能必须重复相同的步骤。 有关详细信息，请参阅[管理驱动因素 System Center Configuration Manager 中](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)。

### <a name="create-skype-room-system-configuration-package"></a>创建 Skype 会议室系统配置包

1.  在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**以及然后选择**创建新程序包**。

2.  输入以下信息以创建包：

    -   名称： **SR v2-配置 SR 安装程序包**

    -   制造商： **Microsoft Corporation**

    -   版本： **1.0.0**

    -   选择**此程序包包含源文件**复选框、 **SR v2-配置 SR 安装程序**文件夹中，输入的路径，然后选择**下一步**。

3.  选择**不创建程序**，然后选择**下一步**。

4.  查看**确认的设置**页，然后选择**下一步**。

5.  选择**关闭**。



## <a name="distribute-configuration-manager-packages"></a>分发配置管理器包

必须将所有程序包都分发给已分配了分发点角色配置管理器层次结构中的服务器。 按照以下说明启动软件包分发。

1.  分发软件包。

    1.  在 Configuration Manager 控制台中，转到**软件库** \> **应用程序管理** \> **包**。 选择您想要分配的所有软件程序包，然后都选择**分发内容**。

    2.  查看包的列表，然后选择**下一步**。

    3.  向列表中，添加所有分发点服务器 （或分发点组，具体取决于您的配置管理器层次结构），然后选择**下一步**。

    4.  选择**下一步**，，，然后选择**关闭**。

2.  分发驱动程序包。

    1.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **驱动程序包**。 选择您想要分配的所有驱动程序包，然后都选择**分发内容**。

    2.  查看包的列表，然后选择**下一步**。

    3.  向列表中，添加所有分发点服务器 （或分发点组，具体取决于您的配置管理器层次结构），然后选择**下一步**。

    4.  选择**下一步**，，，然后选择**关闭**。

3.  分发操作系统包。

    1.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **操作系统映像**。 选择您想要分配的所有操作系统映像，然后都选择**分发内容**。

    2.  查看包的列表，然后选择**下一步**。

    3.  向列表中，添加所有分发点服务器 （或分发点组，具体取决于您的配置管理器层次结构），然后选择**下一步**。

    4.  选择**下一步**，，，然后选择**关闭**。

> [!NOTE]
> 软件包分发可能需要一些时间，具体取决于程序包大小、 配置管理器层次结构、 分发点服务器的数量和网络中可以使用的带宽。
> 
> 在开始部署 Skype 会议室系统 v2 单位之前，必须将分发所有程序包。
> 
> 您可以查看您程序包分发 Configuration Manager 控制台中的状态，转到**监控** \> **分发状态** \> **内容状态**。

## <a name="configuration-manager-task-sequences"></a>配置管理器任务序列

使用任务序列使用 System Center Configuration Manager 中自动部署到目标计算机的操作系统映像的步骤。 若要部署中自动方式的 Skype 会议室系统 v2 单元，您创建引用用于启动目标 Skype 会议室系统 v2 计算机、 Windows 10 Enterprise 操作系统映像的要进行安装，以及任何启动映像任务序列其他其他内容，例如其他应用程序或软件更新。

### <a name="import-the-sample-task-sequence"></a>导入示例任务序列

您可以下载轻松导入示例任务序列并自定义以符合您的需求。

1.  [**下载**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)示例任务序列，并将下载的压缩文件复制到共享位置。
2.  在 Configuration Manager 控制台中，转到**软件库** \> **操作系统** \> **任务序列**和然后选择**导入任务序列**。

3.  选择**浏览**，转到您在步骤 1 中使用的共享的文件夹位置，选择**Skype 会议室系统 v2 部署 (EN-US).zip**文件中，，然后选择**下一步**。

4.  将**操作**设置为**新建**，然后选择**下一步**。

5.  确认设置，，然后选择**下一步**。

6.  选择**关闭**。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>验证引用包正确链接到任务序列的每个步骤。

1. 选择导入的任务序列，，，然后选择**编辑**。

    任务序列编辑器打开并显示每个连续的步骤，您需要部署和配置 Skype 会议室系统 v2 单位。

2. 演练每个步骤并完成建议的更新：

   1. **在 Windows PE 重新启动**： 此步骤重新启动，然后启动到 Windows PXE 的计算机。 没有更改所需的此步骤。

   2. **分区磁盘 0 – UEFI**： 此步骤擦除磁盘配置并创建基于已配置的设置的分区。 我们建议对此步骤不进行任何更改。

   3. **设置 SR 计算机名称**： 本步骤包括 HTML 应用程序提供 UI 在部署过程中设置的 Skype 会议室系统 v2 单位的计算机名称。
      -  这是一个可选步骤，但它可以仅禁用如果您想要管理计算机命名通过备用的过程。
      -  确认已选中**SR v2-设置 SRSComputerName**包。 如果没有，则浏览到包，并选择它。

   4. **应用的操作系统**： 此步骤指定要部署操作系统映像和要使用的无人参与的 Sysprep 应答文件。
      -  验证已选择正确的 Windows 10 Enterprise 操作系统图像文件。
      -  验证启用了**使用无人参与或为自定义安装 Sysprep 应答文件**，并选择**SR v2-Sysprep 包**。 此外还应确保**文件名称**设置为**unattend.xml**。

   5. **应用 Windows 设置**： 此步骤收集关于 Windows 安装的信息。
      -  提供许可和注册信息包括本地管理员帐户密码，产品密钥和时区 （具体取决于您的需求）。

   6. **应用网络设置**： 此步骤，可以指定工作组或 Active Directory 域名和组织单位。
      > [!NOTE]
      > 建议的操作需要部署 Skype 会议室系统 v2 单位为 Actve Directory 域的成员，请参阅[Skype 会议室系统域加入注意事项](domain-joining-considerations.md)。
   7. **应用驱动程序：** 使用此步骤和及其子步骤部署适用的设备驱动程序和基于 Surface Pro 模型必须的固件。 更新每个步骤，以指定与此部署关联的相关的驱动程序包。
      -   每个驱动因素包配置为利用 Windows Management Instrumentation (WMI) 筛选器部署相关的驱动程序的固件基于 Surface Pro 使和模型。
      -   我们强烈建议您不更改这些驱动程序的配置，否则部署可能会失败。

   8. **设置 Windows 和配置管理器**： 此步骤部署和配置 Configuration Manager 客户端。 更新指定的内置的配置管理器客户端包此步骤。

   9. **安装根证书**： 此步骤分发非加入域的设备的根证书，因此是可选的默认为禁用。
      -   如果您需要部署到的 Skype 会议室系统 v2 单位的根证书，则启用此步骤。
      -   如果需要执行此步骤，请验证选中的**SR v2 – 根证书包**和**禁用 64-bit 文件系统重定向**。

   10. **安装和配置 OMS 代理**： 此步骤安装 Microsoft 操作管理套件代理的 64 位版本和配置要连接到您的日志分析工作区的代理。
       -   默认情况下禁用此步骤。 仅当您要使用 OMS to monitor the health 的您 Skype 会议室系统 v2 单位，则启用此步骤。
       -   编辑此步骤和更新的命令行参数指定您的**工作区 ID**和**工作区键**。
       -   有关获取操作管理套件工作区 ID 和主关键字的详细信息，请参阅[到 Azure 中的日志分析服务的连接的 Windows 计算机](with-oms.md#configure-test-devices-for-operations-management-suite-setup)。
       -   验证选中的**SR v2 – Microsoft OMS 代理包**和**禁用 64-bit 文件系统重定向**。
       -   有关监控的 Skype 会议室系统 v2 部署运行状况的详细信息，请参阅[使用 OMS 的规划 Skype 会议室系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)和[使用 OMS 的部署 Skype 会议室系统 v2 管理](with-oms.md#configure-test-devices-for-operations-management-suite-setup)。

   11. **复制 SR v2 配置文件**： 此步骤将从 Skype 会议室系统 v2 部署工具包所需的安装和配置文件复制到本地硬盘。 无自定义，则需要此步骤。
       -   验证选中的**SR v2 – SR 应用程序包**和**禁用 64-bit 文件系统重定向**。

   12. **安装 SRSv2 操作系统更新**： 此步骤将部署与 Skype 会议室系统 v2 部署所需的任何必需的操作系统更新。 请执行下列操作：
       -   检查以查看哪些更新所需的[配置 Skype 会议室系统 v2 控制台](console.md)。
       -   确认您**SR v2 – 操作系统更新程序包**包含所有必需的更新。
       -   确认已选中**SR v2 – 操作系统更新包**。
       -   验证 PowerShell 执行策略设置为**绕过**。

   13. **重新启动计算机**： 在安装必需的操作系统更新后，此步骤重新启动计算机。 无自定义，则需要此步骤。

   14. **配置 Windows 组件**： 此步骤配置所需的 Windows 功能。 无自定义，则需要此步骤。

   15. **重新启动计算机**： 配置 Windows 功能后，此步骤重新启动计算机。 无自定义，则需要此步骤。

   16. **添加本地 Skype 用户**： 此步骤创建用于自动登录到 Windows 和启动 Skype 会议室系统 v2 应用程序的本地 Skype 帐户。 此步骤没有与其关联的任何软件程序包，它需要无自定义。

   17. **设置并配置 SR 应用程序**： 此步骤配置下次启动操作系统的 Skype 会议室系统 v2 应用程序安装。
       -   验证选中**SR v2 – 配置 SR 安装程序包**并**禁用 64-bit 文件系统重定向**。

> [!IMPORTANT]
> 它是非常重要的任务序列步骤必须在提供的顺序。 修改顺序的步骤，或配置其他步骤可能会中断部署。
>
> **设置并配置 SR 应用程序**步骤必须在任务序列中的最后一步，否则部署可能会失败。

### <a name="create-deployment-for-the-task-sequence"></a>创建部署任务序列

1. 选择任务序列，，，然后选择**部署**。

2. 选择**浏览**选择部署目标集合。

3. 选择**所有未知的计算机**，然后选择**确定**。

4. 选择**下一步**。

5. 选择**用途**下拉列表上的**有空**。

6. 在**使可用于以下**列表中，选择**仅媒体和 PXE** ，然后选择**下一步**。
   > [!WARNING]
   > 它是非常重要的**目的**设置为**可用**。 确保**用途**是**** 设置为**所需**。 另外，请确保您选择中**对以下公开****仅媒体和 PXE** 。
   >
   > 为其他设置这些值可能会导致获取 Skype 会议室系统部署映像时启动的所有计算机。
7. 不指定任何计划，并选择**下一步**。

8. 不更改**用户体验**部分中的任何内容，并选择**下一步**。

9. 不更改**通知**部分中的任何内容，并选择**下一步**。

10. 不更改该**分发点**内容中的任何内容，并选择**下一步**。

11. 确认设置，然后选择**下一步**。

12. 选择**关闭**。

<a name="validate-and-troubleshoot-the-solution"></a>验证并排查解决方案
--------------------------------------

在您完成 System Center Configuration Manager 任务序列后，您需要执行测试运行以验证任务序列可以部署和配置 Skype 会议室系统 v2 单位。

1.  通过使用受支持的以太网适配器之一或使用曲面停靠到有线网络连接的测试设备。 如果尚未为您的环境配置 PXE 启动功能，您可用于启动映像上 USB 闪存驱动器[您先前创建](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)从 USB 启动并连接到配置管理器。

2.  访问固件并启动 PXE 启动：

    1.  确保曲面设备处于关闭状态。

    2.  按住**批量向上**按钮。

    3.  按下并释放**高级**按钮。

    4.  设备后开始启动，释放**卷 Up**按钮。

    5.  选择**启动配置**。

    6.  请执行下列操作之一：

        -   选择**PXE 启动**，并将其拖动至列表顶部。 此外，您可以扫过网络适配器立即启动到设备上的左侧。 这不会影响启动顺序。
        -   选择包含启动媒体的 USB 闪存驱动器。

3.  选择**退出**，，，然后选择**立即重新启动**。

4.  出现提示时，选择网络启动服务**Enter** 。

5.  Windows PE 将加载到内存中，并将启动任务序列向导。 选择**下一步**以继续。

6.  选择之前，导入任务序列，然后选择**下一步**。

7.  应用磁盘配置后，将提示您指定设备的计算机名称。 用户界面会显示基于 Surface Pro 设备序列号的推荐的计算机名称。 您可以接受建议的名称，或指定一个新。 按照计算机名称分配屏幕上的说明。 当选择**接受**时，在开始部署。

8.  部署过程的其余部分是自动并不要求输入任何多个用户。

9.  部署任务序列完成配置设备后，您将看到要求您配置 Skype 会议室系统 v2 应用程序设置下配置屏幕。

    ![Skype 会议室系统 v2 应用程序的初始安装屏幕](../../media/room-systems-scale-image2.png)

10.  Surface Pro 插入 Skype 会议室系统 v2 控制台中，并配置的应用程序设置。

11.  验证已部署的设备上的[Skype 会议室系统 v2 帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能都正常工作。


要解决安装失败，请检查日志在 Configuration Manager 任务序列中执行的所有步骤的**SMSTS.log**文件。

SMSTS.log 文件存储在多个路径，具体取决于生成过程的阶段之一。 检查下表标识 SMSTS.log 文件的路径。


| **部署阶段**                                                            | **任务序列日志路径**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE 之前 HDD 格式                                                        | X:\\Windows\\Temp\\smstslog\\smsts.log             |
| WinPE 之后 HDD 格式                                                         | C:\\_SMSTaskSequence\\日志\\Smstslog\\smsts.log    |
| 部署之前的 Configuration Manager 代理已安装, 的操作系统 | c:\\_SMSTaskSequence\\日志\\Smstslog\\smsts.log    |
| 操作系统和部署 Configuration Manager 代理                   | %windir%\\System32\\ccm\\日志\\Smstslog\\smsts.log |
| 完成执行任务序列                                                | %windir%\\System32\\ccm\\日志\\smsts.log           |

> [!TIP]
> 可以随时期间任务序列以打开命令控制台中，选择**F8** ，然后获取对 SMSTS.log 文件的访问。

要解决 PXE 启动问题，请检查两个日志文件的配置管理器服务器上的特定于 PXE 操作：

-   **Pxecontrol.log**，位于配置管理器安装日志目录

-   **Smspxe.log**，位于配置管理器管理点 (MP) 日志目录中

您可以使用进一步解决配置管理器安装的日志文件的完整列表，请参阅[System Center Configuration Manager 中的日志文件](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)。
