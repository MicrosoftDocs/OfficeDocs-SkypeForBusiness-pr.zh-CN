---
title: 使用 Microsoft 终结点配置管理器部署 Microsoft Teams 会议室
author: dstrome
ms.author: dstrome
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
description: 了解如何使用 Microsoft 终结点配置管理器大规模部署 Microsoft Teams 会议室。
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
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410108"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft 终结点配置管理器部署 Microsoft Teams 会议室

本文提供使用 Microsoft 终结点配置管理器创建 Microsoft Teams 会议室部署所需的全部信息。

使用 Configuration Manager 提供的易用方法，可以将操作系统和其他应用程序部署到多个目标设备。

使用下面演示的方法指导完成配置管理器配置，并根据需要自定义本指南中提供的示例包和脚本。

![使用 Configuration Manager 的 Microsoft Teams 会议室部署过程](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 此解决方案仅通过基于 Surface Pro 的部署进行测试。 对于不基于 Surface Pro 的配置，请遵循制造商指南。

## <a name="validate-prerequisites"></a>验证先决条件

若要使用 Configuration Manager 部署 Microsoft Teams 会议室，请确保满足以下先决条件和要求。

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft 终结点配置管理器要求

-   Microsoft Endpoint Configuration Manager 版本必须至少为 1706 或更旧版本。 建议使用 1710 或更高版本。 请查看配置 [管理器中对 Windows 10](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) 的支持，了解配置管理器支持的 Windows 10 版本。

-   必须安装适用于 Windows 10 (ADK) 支持的 Windows 评估和部署工具包版本。 请参阅 Windows [10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) 版本，这些版本可用于不同版本的 Configuration Manager，并确保部署包含正确的版本。

-   必须为站点系统服务器分配分发点角色，并且应该为预启动执行环境启用启动映像 [ (PXE](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)) 启用网络发起的部署。 如果未启用 PXE 支持，可以使用 [可启动](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 媒体进行部署。

-   必须将网络访问帐户配置为支持新计算机 (裸机) 方案。 若要详细了解网络访问帐户的配置，请参阅配置管理器 [中使用的帐户](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

-   如果同时将 [同](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)一 Microsoft Teams 会议室映像部署到多个单元，建议启用多播支持。

### <a name="networking-requirements"></a>网络要求

-   网络应具有一个动态主机配置协议 (DHCP) 服务器，该服务器配置为自动将 IP 地址分发到将部署 Microsoft Teams 会议室单元的子网。

    > [!NOTE]
    > DHCP 租约持续时间必须设置为大于映像部署持续时间的值。 否则，部署可能会失败。

-   网络（包括交换机和虚拟 (VLAN) ）应配置为支持 PXE。 有关 IP 帮助程序与 PXE 配置的信息，请参阅网络供应商。 或者，如果 [PXE](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 支持未启用，可以使用可启动媒体进行部署。

    > [!NOTE]
    > 对于 Surface Pro 设备， (PXE) ，只有使用 Microsoft 的以太网适配器或扩展坞时，才支持从网络启动。 第三方以太网适配器不支持使用 Surface Pro 启动 PXE。 有关详细信息 [，请参阅以太网适配器和 Surface](/surface/ethernet-adapters-and-surface-device-deployment) 部署。

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>为操作系统部署配置 Microsoft 终结点配置管理器

本文假定你已拥有正常的 Configuration Manager 部署，并且未详细说明从头开始部署和配置配置管理器所需的所有步骤。 有关 Microsoft [终结点配置管理器](/configmgr/) 的文档和配置指南是一个很好的资源;如果尚未部署配置管理器，建议从这些资源着手。

使用以下说明验证 OSD (配置) 操作系统部署。

### <a name="validate-and-upgrade-configuration-manager"></a>验证和升级配置管理器

1.  在配置管理器控制台中，转到 **"管理更新** \> **"和"服务"。**

2.  检查已安装的生成和尚未安装的适用更新。

3.  在 [配置管理器中查看对 Windows 10 的支持](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client);如果需要升级部署，请选择要安装的更新，然后选择"下载 **"。**

4.  下载完成后，选择更新，然后选择"**安装更新包"。**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>配置分发点以支持 PXE 和多播

1.  在配置管理器控制台中，转到 **"管理** \> **分发点"。**

2.  选择用于 Microsoft Teams 会议室部署的分发点服务器，然后选择"属性 **"。**

3.  选择 **"PXE"** 选项卡，并确保已启用以下设置：
    -   为客户端启用 PXE 支持
    -   允许此分发点响应传入的 PXE 请求
    -   启用未知的计算机支持

4.  *可选：* 若要启用多播支持，请选择" **多** 播"选项卡，并确保启用以下设置：
    -   启用多播以同时将数据发送到多个客户端
    -   根据网络团队的建议配置 UDP 端口范围

### <a name="configure-the-network-access-account"></a>配置网络访问帐户

1.  在配置管理器控制台中，转到" **管理** \> **站点配置** \> **站点**"，然后选择站点。

2.  在"设置 **"组中**，选择 **"配置站点组件** \> **软件分发"。**

3.  选择"**网络访问帐户"** 选项卡。设置一个或多个帐户，然后选择"确定 **"。**

> [!NOTE]
> 帐户不需要任何特殊权限，但从分发点服务器上网络访问此计算机除外。 通用域用户帐户将适用。 有关详细信息，请参阅 [配置管理器 中使用的帐户](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

### <a name="configure-a-boot-image"></a>配置启动映像

1.  在配置管理器控制台中，转到 **"软件库** \> **操作系统** \> **启动映像"。**

2.  选择 **"启动映像 (x64) "，** 然后选择"属性 **"。**

3.  选择"**数据源"** 选项卡，然后从已启用 PXE 的分发点启用"部署 **此启动映像"。**

4.  选择" **可选组件"** 选项卡以安装所需的组件：

    1.  选择星形图标，然后搜索 **WINPE-HTA (HTML)**

    2.  选择 **"** 确定"，将 HTML 应用程序支持添加到启动映像。

5.  *可选：* 若要自定义部署体验，请选择"自定义 **"** 选项卡。
    -   若要 **在 (访问命令) ，** 才启用命令支持以测试。 启用此功能后，可以在部署过程中随时通过选择 **F8** 来启动命令提示符。
    -   还可以指定在部署期间显示的自定义背景映像。 若要设置图像，请启用 **"在 UNC 路径 (自定义背景图像文件并选择** 背景。

6.  当系统询问时 **，选择** "是"，并将更新的启动映像分发到分发点。

有关详细信息，请参阅使用 [Configuration Manager 管理启动映像](/configmgr/osd/get-started/manage-boot-images)。

> [!NOTE]
> 可以创建可启动的 USB 媒体，为没有 PXE 支持的环境启动基于配置管理器任务序列的部署。 可启动媒体仅包含启动映像、可选 prestart 命令及其所需的文件，以及 Configuration Manager 二进制文件，用于支持启动到 Windows PE 并连接到 Configuration Manager，供部署过程的其余部分使用。 有关详细信息，请参阅 [创建可启动媒体](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。

## <a name="create-configuration-manager-packages"></a>创建配置管理器包

> [!IMPORTANT]
> 每个 SRS 安装程序版本所需的操作系统版本随每个 MSI 版本而更改。 若要确定给定 MSI 的最佳操作系统版本，请运行控制台设置脚本一次。 有关详细信息，请参阅使用 [Microsoft 终结点配置管理器](rooms-scale.md)部署 Microsoft Teams 会议室。

配置管理器需要多个包来部署和配置 Microsoft Teams 会议室单元。

需要创建并配置以下包，并将其分发到已分配有分发点服务器角色的 Configuration Manager 站点系统。

| **包名称**                     | **类型**               | **说明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - SRS 应用程序包     | 软件包       | Microsoft Teams 会议室部署工具包包                                      |
| SRS v2 - Sysprep 包             | 软件包       | 用于配置 Microsoft Teams Unattended.xml单元的自定义程序包            |
| SRS v2 - Set-SRSComputerName 包 | 软件包       | HTML 应用程序的包 (HTA) ，以在部署期间分配计算机名称    |
| SRS v2 - 配置 SRS 设置         | 软件包       | 用于配置 Microsoft Teams 会议室应用的部署的包                          |
| SRS v2 - OS 更新包          | 软件包       | 部署强制操作系统更新的包                                      |
| SRS v2 - 根证书包    | 软件包       | 可选 - 用于部署根证书的包 (已加入域的单元不需要)   |
| SRS v2 - Microsoft Monitoring Agent 包 | 软件包       | 可选 - 用于部署和配置 Microsoft Operations Management Suite 代理的包|
| SRS v2 - WinPE 后台包    | 软件包       | 要用于启动映像的自定义背景映像的包                           |
| Windows 10 企业版                | 操作系统映像 | install.wim (操作系统安装文件的)                           |
| Surface Pro                          | 驱动程序包         | 适用于 Microsoft Surface Pro 的设备驱动程序和固件包                     |
| Surface Pro 4                        | 驱动程序包         | 适用于 Microsoft Surface Pro 4 的设备驱动程序和固件包                   |

有关详细信息，请参阅 Configuration [Manager 中的包和程序](/configmgr/apps/deploy-use/packages-and-programs)。

### <a name="create-folders-for-the-package-source-files"></a>为包源文件创建文件夹

配置管理器要求包源文件在首次创建和更新时按特定文件夹结构进行组织。

在 Microsoft Endpoint Configuration Manager 管理中心站点或主站点或用于托管包源文件的服务器共享上创建以下文件夹结构：

-   SRS v2 - Microsoft Monitoring Agent 包
-   SRS v2 - OS 更新包
-   SRS v2 - 根证书包
-   SRS v2 - Set-SRSComputerName 包
-   SRS v2 - SRS 应用程序包
-   SRS v2 - 配置 SRS 设置
-   SRS v2 - Sysprep 包
-   驱动程序
    -   Surface Pro
    -   Surface Pro 4
-   操作系统
    -   Windows 10 企业版

> [!TIP]
> 还可以下载 [并使用](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) zip 文件，其中包含包的文件夹结构、需要使用的脚本以及需要导入的任务序列模板。

### <a name="create-the-monitoring-agent-package"></a>创建监视代理包

1. 从 下载监视代理 <https://go.microsoft.com/fwlink/?LinkId=828603> 。

2. 打开命令提示符窗口，在命令提示符下输入MMASetup-AMD64.exe **/C：** ，将包提取到 **SRS v2 - Microsoft Monitoring Agent Package** 文件夹中。

3. 在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

4. 输入以下信息以创建包：

   - 名称<strong>：SRS v2 - Microsoft Monitoring Agent 包</strong>

   - 制造商<strong>：Microsoft Corporation</strong>

   - 版本<strong>：8.1.11081.0</strong> (输入下载的安装文件版本) 

   - 选中"**此包包含源文件"复选框**，输入 **SRS v2 - Microsoft Monitoring Agent Package** 文件夹的路径，然后选择"下一步 **"。**

5. 选择 **"不创建程序"，** 然后选择"下一 **步"。**

6. 查看"**确认设置"页**，然后选择"下一 **步"。**

7. 选择"**关闭"。**

### <a name="create-the-operating-system-updates-package"></a>创建操作系统更新包

1. 在 **"SRS v2 - OS 更新包** "文件夹中，创建名为Install-SRSv2-OS-Updates.ps1 **的新 PowerShell 脚本**。

2. 将以下脚本复制到 **Install-SRSv2-OS-Updates.ps1** 脚本。 或者，可以从此处下载[Install-SRSv2-OS-Updates.ps1脚本。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3. 将必需的 Windows 更新包下载到同一文件夹中。
   > [!NOTE]
   > 在本文发布时，只需要[KB4056892。](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 选中 ["配置 Microsoft Teams 会议室"控制台](console.md)，查看是否需要任何其他更新。

4. 在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

5. 输入以下信息以创建包：
   -   名称 **：SRS v2 – OS 更新包**
   -   制造商 **：Microsoft Corporation**
   -   版本 **：1.0.0**
   -   选中"**此包包含源文件"复选框**，输入 **SRS v2 - OS 更新包** 文件夹的路径，然后选择"下一步 **"。**

6. 选择 **"不创建程序"，** 然后选择"下一 **步"。**

7. 查看"**确认设置"页**，然后选择"下一 **步"。**

8. 选择"**关闭"。**

### <a name="create-the-root-certificate-package-optional"></a>创建根证书包 (可选) 

创建此包，为不会加入 Active Directory 域的设备分发根证书。 仅在以下两个条件都适用时创建此包：
-   部署包括本地 Lync 或 Skype for Business Server。
-   Microsoft Teams 会议室单元配置为在工作组中工作，而不是域成员。

1.  将根证书复制到 **"SRS v2 – 根证书包"** 文件夹。

2.  在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

3.  输入以下信息以创建包：
    -   名称 **：SRS v2 – 根证书包**
    -   制造商 *：组织的名称*
    -   版本 **：1.0.0**
    -   选中"**此包包含源文件"复选框**，输入 **SRS v2 –** 根证书包文件夹的路径，然后选择"下一步 **"。**

4.  选择 **"不创建程序"，** 然后选择"下一 **步"。**

5.  查看"**确认设置"页**，然后选择"下一 **步"。**

6.  选择"**关闭"。**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>创建 Microsoft Teams 会议室部署工具包包

1.  从 下载最新版本的 **Microsoft Teams 会议室部署工具包** <https://go.microsoft.com/fwlink/?linkid=851168> ，并安装到工作站。

2.  将内容从 **C： \\ Program Files (x86) \\ Skype Room System Deployment Kit** 复制到 **SRS v2 - SRS 应用程序包** 文件夹。

3.  在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

4.  输入以下信息以创建包：
    -   名称 **：SRS v2 – SRS 应用程序包**
    -   制造商 **：Microsoft Corporation**
    -   版本 **：3.1.104.0** (输入下载的安装文件版本) 
    -   选中"**此包包含源文件"复选框**，输入 **SRS v2 – SRS** 应用程序包文件夹的路径，然后选择"下一步 **"。**
5.  选择 **"不创建程序"，** 然后选择"下一 **步"。**

6.  查看"**确认设置"页**，然后选择"下一 **步"。**

7.  选择"**关闭"。**

### <a name="create-the-computer-name-assignment-package"></a>创建计算机名称分配包

1.  在 **"SRS v2 - Set-SRSComputerName 包** "文件夹中，创建名为 **Set-SRSComputerName.hta 的新** HTML 应用程序。

2.  将以下脚本复制到 **Set-SRSComputerName.hta** 文件中。 或者，可以从此处下载 Set-SRSComputerName.hta [文件](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)。
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
3.  在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

4.  输入以下信息以创建包：

    -   名称 **：SRS v2 - Set-SRSComputerName包**

    -   制造商 **：Microsoft Corporation**

    -   版本 **：1.0.0**

    -   选中"**此包包含源文件"复选框**，输入 **SRS v2 - Set-SRSComputerName包文件夹** 的路径，然后选择"下一步 **"。**

5.  选择 **"不创建程序"，** 然后选择"下一 **步"。**

6.  查看"**确认设置"页**，然后选择"下一 **步"。**

7.  选择"**关闭"。**

### <a name="create-the-sysprep-package"></a>创建 Sysprep 包

1. 在 **"SRS v2 – Sysprep 包** "文件夹中，创建名为Unattend.xml **的新 XML 文件** 。

2. 将以下文本复制到 **Unattend.xml** 文件中。 或者，可以从此处下载[Unattend.xml文件。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3. 在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

4. 输入以下信息以创建包：
   -   名称 **：SRS v2 - Sysprep 包**
   -   制造商 **：Microsoft Corporation**
   -   版本 **：1.0.0**
   -   选中"**此包包含源文件"复选框**，输入 **SRS v2 – Sysprep 包** 文件夹的路径，然后选择"下一步 **"。**
5. 选择 **"不创建程序"，** 然后选择"下一 **步"。**

6. 查看"**确认设置"页**，然后选择"下一 **步"。**

7. 选择"**关闭"。**

### <a name="create-the-windows-10-enterprise-package"></a>创建 Windows 10 企业版包

1.  获取 Windows 10 企业版 x64 媒体，将 **install.wim** 文件复制到 **操作系统 Windows \\ 10 企业** 版文件夹。

2.  在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统** \> **映像**"，然后选择"**添加操作系统映像"。**

3.  指定刚复制的 **install.wim** 文件的路径，然后选择"下一步 **"。**

4.  更新"**版本"** 字段以匹配 Windows 10 企业映像的版本号，然后选择"下一步 **"。**

5.  查看"**详细信息"** 页，然后选择"下一 **步"。**

6.  选择"**关闭"。**

有关详细信息，请参阅使用 [Configuration Manager 管理 OS 映像](/configmgr/osd/get-started/manage-operating-system-images)。

### <a name="create-surface-pro-device-driver-packages"></a>创建 Surface Pro 设备驱动程序包

Surface Pro 和 Surface Pro 4 都支持 Microsoft Teams 会议室。 你需要为环境中每个 Surface Pro 模型创建驱动程序包。

> [!IMPORTANT]
> 驱动程序必须与 Windows 10 企业版和 Microsoft Teams 会议室部署工具包版本兼容。 有关详细信息，请参阅下载 [Surface 设备](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 的最新固件和驱动程序和 [配置主机](console.md)。

1.  下载最新的驱动程序和固件。
    -   对于 Surface Pro： <https://www.microsoft.com/download/details.aspx?id=55484>
    -   对于 Surface Pro 4： <https://www.microsoft.com/download/details.aspx?id=49498>

2.  提取下载的驱动程序和固件。 打开命令提示符窗口，在命令提示符下输入以下命令之一：
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统** \> **驱动程序**"，然后选择"**导入驱动程序"。**

4.  选择 **"导入** 以下网络路径 (UNC) 的所有驱动程序"，选择源文件夹 (例如 C： _Sources Drivers Surface Pro) ，然后选择"下一 \\ \\ \\ 步"。 

5.  在 **"指定导入的驱动程序** 的详细信息"页上，选择列出的所有驱动程序，然后选择"启用这些驱动程序并允许计算机 **安装它们"。**

6.  选择 **"** 类别"，创建与 Surface 模型匹配的新类别，选择"**确定**"，然后选择"下一步 **"。**

7.  选择 **"新建包"。**

8.  指定与 Surface Pro 模型匹配的包名称，输入用于存储驱动程序包文件的文件夹路径，选择"确定 **"，然后选择**"下一步 **"。**

9.  在"**启动映像"** 页上，确保未选择任何启动映像，然后选择"下一步 **"。**

10. 选择"**关闭"。**

11. 转到"**软件库** 操作系统驱动程序"，选择"文件夹创建文件夹"，然后输入与刚刚导入驱动程序的 Surface Pro 模型 \>  \> 相匹配的文件夹名称。 **\>**

12. 将导入的所有驱动程序移到新创建的文件夹，以便更轻松地导航和操作。

> [!NOTE]
> 对可能拥有的其他 Surface Pro 模型重复相同的步骤。 有关详细信息，请参阅在 [Configuration Manager 中管理驱动程序](/configmgr/osd/get-started/manage-drivers)。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>创建 Microsoft Teams 会议室配置包

1.  在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"，** 然后选择"**创建包"。**

2.  输入以下信息以创建包：

    -   名称 **：SRS v2 - 配置 SRS 安装包**

    -   制造商 **：Microsoft Corporation**

    -   版本 **：1.0.0**

    -   选中"**此包包含源文件"复选框**，输入 **SRS v2 - 配置 SRS 安装程序** 文件夹的路径，然后选择"下一步 **"。**

3.  选择 **"不创建程序"，** 然后选择"下一 **步"。**

4.  查看"**确认设置"页**，然后选择"下一 **步"。**

5.  选择"**关闭"。**



## <a name="distribute-configuration-manager-packages"></a>分发配置管理器包

所有包必须分发到在配置管理器层次结构中分配了分发点角色的服务器。 按照以下说明启动包分发。

1.  分发软件包。

    1.  在配置管理器控制台中，转到 **"软件库** \> **应用程序管理** \> **包"。** 选择要分发的所有软件包，然后选择"分发 **内容"。**

    2.  查看程序包列表，然后选择"下一 **步"。**

    3.  根据配置管理器层次结构， (组或分发点组添加所有分发点) 服务器，然后选择"下一步 **"。**

    4.  选择 **"下一** 步"，然后选择"关闭 **"。**

2.  分发驱动程序包。

    1.  在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统驱动程序** \> **包"。** 选择要分发的所有驱动程序包，然后选择"分发 **内容"。**

    2.  查看程序包列表，然后选择"下一 **步"。**

    3.  根据配置管理器层次结构， (组或分发点组添加所有分发点) 服务器，然后选择"下一步 **"。**

    4.  选择 **"下一** 步"，然后选择"关闭 **"。**

3.  分发操作系统包。

    1.  在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统** \> **映像"。** 选择要分发的所有操作系统映像，然后选择"分发 **内容"。**

    2.  查看程序包列表，然后选择"下一 **步"。**

    3.  根据配置管理器层次结构， (组或分发点组添加所有分发点) 服务器，然后选择"下一步 **"。**

    4.  选择 **"下一** 步"，然后选择"关闭 **"。**

> [!NOTE]
> 包分发可能需要一些时间，具体取决于包大小、配置管理器层次结构、分发点服务器数以及网络中可用的带宽。
> 
> 必须先分发所有程序包，然后才能开始部署 Microsoft Teams 会议室单元。
> 
> 可以通过访问"监视分发状态内容状态"，在配置管理器控制台中 \> **查看包** \> **分发的状态**。

## <a name="configuration-manager-task-sequences"></a>Configuration Manager 任务序列

将任务序列与 Configuration Manager 一起用于自动执行将操作系统映像部署到目标计算机的步骤。 若要以自动化方式部署 Microsoft Teams 会议室单元，请创建一个任务序列，该序列引用用于启动目标 Microsoft Teams 会议室计算机的启动映像、要安装的 Windows 10 企业版操作系统映像，以及任何其他内容，例如其他应用程序或软件更新。

### <a name="import-the-sample-task-sequence"></a>导入示例任务序列

可以下载并轻松导入示例任务序列，并对其进行自定义以满足需求。

1.  [**下载**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 示例任务序列，将下载的 zip 文件复制到共享位置。
2.  在 Configuration Manager 控制台中，转到 **"软件库** \> **操作系统任务** \> **序列"，** 然后选择"**导入任务序列"。**

3.  选择 **"浏览**"，转到步骤 1 中使用的共享文件夹位置，选择 **Microsoft Teams 会议室部署 (EN-US) .zip** 文件，然后选择"下一步 **"。**

4.  将 **"操作**"**设置为"新建**"，然后选择"下一 **步"。**

5.  确认设置，然后选择"下一 **步"。**

6.  选择"**关闭"。**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>验证引用包是否正确链接到每个任务序列步骤。

1. 选择导入的任务序列，然后选择"编辑 **"。**

    任务序列编辑器将打开并显示部署和配置 Microsoft Teams 会议室单元所需的每个有序步骤。

2. 完成每个步骤并完成建议的更新：

   1. **在 Windows PE 中** 重新启动：此步骤将重启，然后将计算机启动到 Windows PXE 中。 此步骤不需要任何更改。

   2. **分区磁盘 0 – UEFI：** 此步骤将擦除磁盘配置，并基于配置的设置创建分区。 建议不要对此步骤做出任何更改。

   3. **设置 SRS 计算机名称**：此步骤包括一个 HTML 应用程序，用于提供一个 UI，用于设置部署期间 Microsoft Teams 会议室单元的计算机名称。
      -  这是一个可选步骤，但只有当你想要通过备用进程管理计算机命名时，才能禁用此步骤。
      -  验证是否 **选择了"SRS v2 - Set-SRSComputerName"** 包。 如果不是，请浏览到程序包并选择它。

   4. **应用操作系统**：此步骤指定要部署的操作系统映像和要使用无人参与的 Sysprep 应答文件。
      -  验证是否选择了正确的 Windows 10 企业版操作系统映像文件。
      -  验证是否已启用对自定义安装使用无人参与或 **Sysprep** 应答文件，并选择了 **"SRS v2 - Sysprep 包** "。 另请确保 **将"文件名**"设置为 **unattend.xml。**

   5. **应用 Windows 设置**：此步骤收集有关 Windows 安装的信息。
      -  提供许可和注册信息，包括产品密钥、本地管理员帐户密码和时区 (，具体取决于) 。

   6. **应用网络设置**：此步骤允许指定工作组或 Active Directory 域名和组织单位。
      > [!NOTE]
      > 请参阅 [Skype 会议室系统域](domain-joining-considerations.md) 加入注意事项，了解在将 Microsoft Teams 会议室单元部署为 Actve Directory 域的成员时需要采取的建议操作。
   7. **应用驱动程序：** 此步骤及其子步骤用于根据你的 Surface Pro 模型部署适用的设备驱动程序和固件。 更新每个步骤，指定与此部署关联的相关驱动程序包。
      -   每个驱动程序包都配置为利用 Windows Management Instrumentation (WMI) 筛选器来部署基于 Surface Pro 制造和模型的相关驱动程序和固件。
      -   强烈建议不要更改这些驱动程序的配置，否则部署可能会失败。

   8. **设置 Windows 和配置管理器**：此步骤部署并配置 Configuration Manager 客户端。 更新此步骤以指定内置的 Configuration Manager 客户端包。

   9. **安装根证书**：此步骤为未加入域的设备分发根证书，因此是可选的，默认情况下处于禁用状态。
      -   如果需要将根证书部署到 Microsoft Teams 会议室单元，可启用此步骤。
      -   如果需要执行此步骤，请验证是否选择了 **"SRS v2 –** 根证书包"和"禁用 **64** 位文件系统重定向"。

   10. **安装和配置监视代理**：此步骤安装 64 位版本的 Microsoft Azure Monitor 代理，并配置代理以连接到 Log Analytics 工作区。
       -   默认情况下，此步骤处于禁用状态。 只有在要使用监视代理监视 Microsoft Teams 会议室单元的运行状况时，才启用此步骤。
       -   编辑此步骤并更新命令行参数，以指定 **工作区 ID** 和 **工作区密钥**。
       -   有关 [获取](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) Operations Management Suite 工作区 ID 和主密钥的信息，请参阅为 Azure 监视配置测试设备。
       -   验证是否 **选择了"SRS v2 – Microsoft Monitoring Agent 包** "和"禁用 **64 位文件系统重定向** "。
       -   有关监视 Microsoft Teams 会议室部署运行状况的信息，请参阅使用 [Azure Monitor](azure-monitor-plan.md)规划 Microsoft Teams 会议室管理、使用 Azure Monitor 部署 [Microsoft Teams](azure-monitor-deploy.md) 会议室管理以及使用 Azure Monitor 管理 Microsoft Teams [会议室设备](azure-monitor-manage.md)。

   11. **复制 SRS v2 配置文件**：此步骤将所需的安装和配置文件从 Microsoft Teams 会议室部署工具包复制到本地硬盘驱动器。 此步骤不需要自定义。
       -   验证是否 **选择了"SRS v2 – SRS** 应用程序包"和"禁用 **64 位文件系统重定向** "。

   12. **Install-SRSv2-OS-Updates：** 此步骤部署 Microsoft Teams 会议室部署所需的任何必需的操作系统更新。 执行以下操作：
       -   选中 ["配置 Microsoft Teams 会议室"控制台](console.md) ，查看需要哪些更新。
       -   验证 **SRS v2 – OS 更新包** 是否包含所有必需的更新。
       -   验证是否选择了 **"SRS v2 – OS 更新包** "。
       -   验证 PowerShell 执行策略是否设置为"绕过 **"。**

   13. **重新启动计算机**：此步骤在安装必需的操作系统更新后重新启动计算机。 此步骤不需要自定义。

   14. **配置 Windows 组件**：此步骤配置所需的 Windows 功能。 此步骤不需要自定义。

   15. **重新启动计算机**：此步骤在配置 Windows 功能后重新启动计算机。 此步骤不需要自定义。

   16. **添加本地 Skype 用户**：此步骤创建用于自动登录到 Windows 的本地 Skype 帐户，并启动 Microsoft Teams 会议室应用程序。 此步骤没有任何关联的软件包，并且不需要任何自定义。

   17. **设置和配置 SRS 应用程序**：此步骤为下次启动操作系统配置 Microsoft Teams 会议室应用程序安装。
       -   验证是否 **选择了"SRS v2 – 配置 SRS** 安装包"和"禁用 **64 位文件系统** 重定向"。

> [!IMPORTANT]
> 任务序列步骤必须按提供的顺序进行，这一点非常重要。 修改步骤顺序或配置其他步骤可能会中断部署。
>
> **设置和配置 SRS 应用程序** 步骤必须是任务序列中的最后一步，否则部署可能会失败。

### <a name="create-deployment-for-the-task-sequence"></a>为任务序列创建部署

1. 选择任务序列，然后选择"部署 **"。**

2. 选择 **"浏览** "以选择要部署的目标集合。

3. 选择 **"所有未知计算机**"，然后选择"确定 **"。**

4. 选择"下 **一步"。**

5. 在 **"用途** " **下拉列表** 中选择"可用"。

6. 在 **"使以下列表可用**"**中选择"仅** 媒体和 PXE"，然后选择"下一 **步"。**
   > [!WARNING]
   > 将" **用途"设置为** "可用 **"非常重要**。 确保"用途 **"****未设置为**"必需 **"。** 另请确保在"使以下项可用"中选择"**仅媒体和** **PXE"。**
   >
   > 将这些值设置为其他值可能会导致所有计算机在启动时获取 Microsoft Teams 会议室部署映像。
7. 不要指定任何计划，然后选择"下一 **步"。**

8. 请勿更改"用户体验"部分 **内的内容**，然后选择"下一 **步"。**

9. 请勿更改"警报"部分 **内** 的内容，然后选择"下一 **步"。**

10. 请勿更改"分发点"部分 **内的内容，** 然后选择"下一 **步"。**

11. 确认设置，然后选择"下一 **步"。**

12. 选择"**关闭"。**

<a name="validate-and-troubleshoot-the-solution"></a>验证和排查解决方案问题
--------------------------------------

完成 Microsoft 终结点配置管理器任务序列后，需要执行测试运行来验证任务序列是否可部署和配置 Microsoft Teams 会议室单位。

1.  使用支持的以太网适配器之一或 Surface 扩展坞将测试设备连接到有线网络。 如果尚未为环境配置 PXE 启动功能，可以使用之前创建的 U 盘上的启动映像从 USB 启动[](/configmgr/osd/deploy-use/create-bootable-media)并连接到 Configuration Manager。

2.  访问固件并启动 PXE 启动：

    1.  确保 Surface 设备已关闭电源。

    2.  长按" **调高音量"** 按钮。

    3.  按下并松开 **"电源"** 按钮。

    4.  设备开始启动后，释放 **"调高音量"** 按钮。

    5.  选择 **"启动配置"。**

    6.  执行下列操作之一：

        -   选择 **"PXE 启动**"，并将其拖动到列表顶部。 或者，可以在网络适配器上向左轻扫以立即启动到设备。 这不会影响启动顺序。
        -   选择保存启动媒体的 U 盘。

3.  选择 **"退出**"，然后选择"**立即重启"。**

4.  系统提示时，为 **网络启动** 服务选择 Enter。

5.  Windows PE 将加载到内存中，任务序列向导将启动。 选择 **"下一** 步"继续。

6.  选择之前导入的任务序列，然后选择"下一步 **"。**

7.  应用磁盘配置后，系统会提示你指定设备的计算机名称。 用户界面将基于 Surface Pro 设备的序列号显示推荐的计算机名称。 可以接受建议的名称或指定新名称。 按照计算机名称分配屏幕上的说明操作。 选择" **接受"** 时，部署将开始。

8.  部署过程的其余部分是自动的，不需要任何其他用户输入。

9.  部署任务序列完成设备配置后，会看到以下配置屏幕，要求配置 Microsoft Teams 会议室应用程序设置。

    ![Microsoft Teams 会议室应用程序的初始设置屏幕](../media/room-systems-scale-image2.png)

10.  将 Surface Pro 插入 Microsoft Teams 会议室控制台，并配置应用程序设置。

11.  验证 Microsoft Teams 会议室中所列的 [功能在](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 已部署设备上是否正常工作。


若要排查安装失败的问题，请检查 **SMSTS.log** 文件，该文件记录在 Configuration Manager 任务序列中执行的所有步骤。

SMSTS.日志文件存储在多个路径之一上，具体取决于生成过程的阶段。 查看下表，确定 SMSTS.日志文件。


| **部署阶段**                                                            | **任务序列日志路径**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE，HDD 格式之前                                                        | \\X：Windows \\ Temp \\ smstslog \\ smsts.log             |
| WinPE，HDD 格式之后                                                         | \\C：_SMSTaskSequence Logs \\ \\ Smstslog \\ smsts.log    |
| 在安装 Configuration Manager 代理之前部署的操作系统 | \\c：_SMSTaskSequence Logs \\ \\ Smstslog \\ smsts.log    |
| 已部署操作系统和 Configuration Manager 代理                   | %windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log |
| 任务序列执行完成                                                | %windir% \\ System32 \\ ccm \\ 日志 \\ smsts.log           |

> [!TIP]
> 在任务序列中，你随时可以选择 **F8** 以打开命令控制台，然后访问 SMSTS.日志文件。

若要排查 PXE 启动问题，请检查 Configuration Manager 服务器上特定于 PXE 操作的两个日志文件：

-   **Pxecontrol.log，** 位于 Configuration Manager 安装日志目录中

-   **Smspxe.log，** 位于配置管理器管理点 (MP) 目录中

有关可用于进一步排查配置管理器安装问题的完整日志文件列表，请参阅 Microsoft Endpoint Configuration Manager [日志文件参考](/configmgr/core/plan-design/hierarchy/log-files)。
