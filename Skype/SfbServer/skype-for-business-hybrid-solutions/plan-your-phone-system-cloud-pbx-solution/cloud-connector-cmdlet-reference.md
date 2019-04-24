---
title: 云连接器 cmdlet 参考
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 下表列出了 Skype for Business 云连接器版本 cmdlet，并带有简要说明和指向详细信息的链接。
ms.openlocfilehash: aa8b8ebe4ffd7d1cb2c405eae5fe6604c5f4c378
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234259"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
下表列出了 Skype for Business 云连接器版本 cmdlet，并带有简要说明和指向详细信息的链接。
  
> [!NOTE]
> 必须运行所有 cmdlet 的云连接器主机上，并且必须以管理员身份都运行 PowerShell 会话。 
  
|**Cmdlet 名称**|**说明**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 1.4.2 版及更高版本  <br/> |将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署云连接器的过程中使用。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |通过将其放在维护模式下，为更新过程准备云连接器主机服务器。 装置为"排空带";也就是说，所有现有呼叫将完成，但新呼叫被拒绝。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |退出更新云连接器主机服务器上的维护模式。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 用于将 Skype for Business 云连接器版本配置导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |将云连接器示例配置文件 (.ini) 导出到云连接器装置的装置目录。 你可以修改和重命名该文件以用于你的部署。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 1.4.2 版及更高版本   <br/> |将根 CA 证书导出到云连接器主机服务器上的本地文件。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |检索云连接器主机服务器上的工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |显示当前目录为云连接器 appliance 日志存储在何处正在  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 2.1 及更高版本  <br/> |提供云连接器装置的诊断信息。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |返回当前云连接器部署的凭据。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |返回云连接器部署外部证书文件路径。 用户准备此证书。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和云连接器安装文件。 应与云连接器网站的所有其他设备共享该文件夹。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |显示当前目录存储云连接器的网站级别日志。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> 2.0 版及更高版本  <br/> |返回云连接器实例上的版本。Get-CCVersion 只能用于云连接器的主机。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> 2.0 版及更高版本  <br/> |将业务云连接器 Edition 配置 Skype 从本地文件导入到云连接器主机服务器上。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |安装云连接器装置 — 包括 AD，中央管理存储、 中介服务器和边缘服务器的虚拟机 — 主机服务器上。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 获取从 online 租户配置高可用性的信息，并将其发布到云连接器装置主机服务器上。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 将设备信息注册到联机租户配置中的 PSTN 站点。 之前可以部署和管理云连接器管理服务，则必须注册 appliance。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 1.4.2 版及更高版本  <br/> |删除证书颁发机构服务备份文件"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"云连接器的网站共享目录的 CA 文件夹中。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 1.4.2 版及更高版本  <br/> |在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> 仅限于版本 1.4.2  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> 仅限于版本 1.4.2  <br/> |在云连接器的证书将要过期或已经过期时续订证书。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 1.4.2 版及更高版本  <br/> |重置证书颁发机构服务器，以安装新的证书颁发机构证书。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 2.1 及更高版本  <br/> |清理凭据，并提示您重新输入用于当前云连接器部署的所有凭据。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |搜索云连接器装置日志目录传入和传出的呼叫日志  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |云连接器主机服务器上设置的工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |设置当前云连接器部署的凭据。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |指定中介服务器或边缘服务器的证书的存储路径  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |设置用于存储云连接器的网站级别的配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |同步下载云连接器位和 msi 文件。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |生成云连接器装置的传入和传出的呼叫日志。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |停止生成传入和传出呼叫的云连接器装置日志。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |将正在运行的设备断开连接，并切换到新部署的设备或备份设备。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |卸载运行的云连接器 appliance 从主机服务器。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |注销当前云连接器设备从 PSTN 网站 online 租户配置中。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> 2.0 版及更高版本  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> 2.0 版及更高版本  <br/> |在云连接器的证书将要过期或已经过期时续订证书。  <br/> |
   

