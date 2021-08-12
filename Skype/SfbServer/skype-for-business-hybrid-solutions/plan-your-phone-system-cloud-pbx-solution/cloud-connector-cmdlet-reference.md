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
description: 下表列出了这些Skype for Business 云连接器版本 cmdlet，并提供了简要说明和指向详细信息的链接。
ms.openlocfilehash: a5a29003db50f79440b6bd0393bce63b8597d90df35cded4b7b6c0114b165b97
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341487"
---
# <a name="cloud-connector-cmdlet-reference"></a>云连接器 cmdlet 参考
 
> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

下表列出了这些Skype for Business 云连接器版本 cmdlet，并提供了简要说明和指向详细信息的链接。
  
> [!NOTE]
> 必须在云连接器主机上运行所有 cmdlet，并且必须以管理员角色运行 PowerShell 会话。 
  
|**Cmdlet 名称**|**说明**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 版本 1.4.2 及更高版本  <br/> |将证书颁发机构服务备份到文件，并保存到网站共享目录下的 CA 文件夹。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |使用客户提供的 R2 ISO (VHDX) 基本虚拟Windows Server 2012硬盘文件。 VHDX 文件将在部署云连接器期间使用。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |通过将云连接器主机服务器置于维护模式，为更新过程做好准备。 设备"排出";即，所有现有呼叫都将完成，但新呼叫将被拒绝。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |在云连接器主机服务器上退出更新维护模式。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 将Skype for Business 云连接器版本配置导出到主机服务器上Skype for Business 云连接器版本文件。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |将云连接器示例配置文件 (.ini) 导出到云连接器设备的设备目录。 可以修改和重命名文件以用于部署。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 版本 1.4.2 及更高版本  <br/> |将根 CA 证书导出到云连接器主机服务器上本地文件。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |检索云连接器主机服务器上的工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |显示存储云连接器设备的日志的当前目录。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 版本 2.1 及更高版本  <br/> |提供云连接器设备的诊断信息。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |返回当前云连接器部署的凭据。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |返回云连接器部署的外部证书文件路径。 用户准备此证书。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和云连接器安装文件。 此文件夹应该与云连接器站点的所有其他设备共享。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |显示存储云连接器的站点级别日志的当前目录。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> 版本 2.0 及更高版本  <br/> |返回云连接器实例上的版本。 Get-CCVersion只能在云连接器的主机中使用。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> 版本 2.0 及更高版本  <br/> |将Skype for Business 云连接器版本配置从本地文件导入到云连接器主机服务器。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |在主机服务器上安装云连接器设备（包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机）。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 从联机租户配置获取高可用性信息，并发布到主机服务器上云连接器设备。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 在联机租户配置中将设备信息注册到 PSTN 站点。 必须先注册设备，然后才能由云连接器管理服务部署和管理该设备。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 版本 1.4.2 及更高版本  <br/> |删除云连接器的站点共享目录下的 CA 文件夹中的证书颁发机构服务备份文件 \<SiteRootDirectory\> "\CA\SfB CCE Root.p12"。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 版本 1.4.2 及更高版本  <br/> |执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，删除中央管理存储、中介服务器和边缘服务器上旧版服务器证书。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> 仅版本 1.4.2  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> 仅版本 1.4.2  <br/> |在云连接器即将过期或已过期时续订这些证书。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 版本 1.4.2 及更高版本  <br/> |重置证书颁发机构服务器以安装新的证书颁发机构证书。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 版本 2.1 及更高版本  <br/> |清理凭据并提示你重新输入用于当前云连接器部署的所有凭据。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |在云连接器设备日志目录中搜索传入和传出呼叫日志  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |设置云连接器主机服务器上的工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |设置当前云连接器部署的凭据。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |指定中介服务器或边缘服务器的证书存储路径  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |设置将存储云连接器的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |同步下载云连接器 bits 和 msi 文件。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |为云连接器设备生成传入和传出呼叫日志。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |停止为云连接器设备生成传入和传出呼叫日志。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |断开正在运行的设备，并切换到新部署的或备份的设备。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |从主机服务器卸载正在运行的云连接器设备。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |从联机租户配置中的 PSTN 站点注销当前云连接器设备。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> 版本 2.0 及更高版本  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> 版本 2.0 及更高版本  <br/> |在云连接器即将过期或已过期时续订这些证书。  <br/> |
