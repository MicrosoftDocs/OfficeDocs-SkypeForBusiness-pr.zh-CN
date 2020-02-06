---
title: 云连接器 cmdlet 参考
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 下表列出了 Skype for Business 云连接器版本 cmdlet，并带有简要说明和指向详细信息的链接。
ms.openlocfilehash: c82d81fe19af7c0f305ce18e0bbce83f944b5d73
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803712"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
下表列出了 Skype for Business 云连接器版本 cmdlet，并带有简要说明和指向详细信息的链接。
  
> [!NOTE]
> 必须在云连接器主机计算机上运行所有 cmdlet，并且必须以管理员身份运行 PowerShell 会话。 
  
|**Cmdlet 名称**|**说明**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 1.4.2 版及更高版本  <br/> |将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署云连接器的过程中使用。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |通过将更新过程置于维护模式来为其准备云连接器主机服务器。 装置已 "排放";也就是说，所有现有通话都将完成，但新通话将被拒绝。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |退出云连接器主机服务器上的 "更新维护模式"。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 用于将 Skype for Business 云连接器版本配置导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |将云连接器示例配置文件（.ini）导出到云连接器装置的装置目录中。 你可以修改和重命名该文件以用于你的部署。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 1.4.2 版及更高版本   <br/> |将根 CA 证书导出到云连接器主机服务器上的本地文件。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |检索云连接器主机服务器上的工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |显示用于存储云连接器装置日志的当前目录。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 版本2.1 和更高版本  <br/> |提供云连接器设备的诊断信息。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |返回当前云连接器部署的凭据。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |返回云连接器部署的外部证书文件路径。 用户准备此证书。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和云连接器安装文件。 此文件夹应与云连接器网站的所有其他装置共享。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |显示存储云连接器的网站级日志的当前目录。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> 2.0 版及更高版本  <br/> |返回云连接器实例上的版本。Get-CCVersion 只能用于云连接器的主机。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> 2.0 版及更高版本  <br/> |将 Skype for Business Cloud Connector Edition 配置从本地文件导入到云连接器主机服务器。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |在主机服务器上安装云连接器设备（包括广告、中央管理存储、中介服务器和边缘服务器虚拟机）。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 从联机租户配置获取高可用性信息，并将其发布到主机服务器上的云连接器设备。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 将设备信息注册到联机租户配置中的 PSTN 站点。 必须先注册装置，然后才能通过云连接器管理服务部署和管理该装置。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 1.4.2 版及更高版本  <br/> |删除云连接器的网站共享目录下\<的\>CA 文件夹中的证书颁发机构服务备份文件 "SiteRootDirectory \CA\SfB CCE 根类"。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 1.4.2 版及更高版本  <br/> |在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> 仅限于版本 1.4.2  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> 仅限于版本 1.4.2  <br/> |在云连接器的证书将要过期或已经过期时续订证书。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 1.4.2 版及更高版本  <br/> |重置证书颁发机构服务器，以安装新的证书颁发机构证书。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 版本2.1 和更高版本  <br/> |清理凭据并提示您重新输入用于当前云连接器部署的所有凭据。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |在云连接器设备日志目录中搜索传入和传出呼叫日志  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |在云连接器主机服务器上设置工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |设置当前云连接器部署的凭据。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |指定中介服务器或边缘服务器的证书的存储路径  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |设置将存储云连接器的网站级配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |同步下载云连接器位和 msi 文件。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |为云连接器装置生成传入和传出呼叫日志。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |停止为云连接器装置生成传入和传出呼叫日志。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |将正在运行的设备断开连接，并切换到新部署的设备或备份设备。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |从主机服务器卸载正在运行的云连接器设备。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |从联机租户配置中的 PSTN 网站注销当前云连接器设备。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> 2.0 版及更高版本  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> 2.0 版及更高版本  <br/> |在云连接器的证书将要过期或已经过期时续订证书。  <br/> |
   

