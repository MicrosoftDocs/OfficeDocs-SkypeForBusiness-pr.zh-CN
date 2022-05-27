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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 下表列出了Skype for Business 云连接器版本 cmdlet，其中包含简短的说明和指向详细信息的链接。
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676164"
---
# <a name="cloud-connector-cmdlet-reference"></a>云连接器 cmdlet 参考

> [!Important]
> Cloud Connector Edition 将于 2021 年 7 月 31 日停用，Skype for Business Online。 组织升级到Teams后，了解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到Teams。

下表列出了Skype for Business 云连接器版本 cmdlet，其中包含简短的说明和指向详细信息的链接。
  
> [!NOTE]
> 必须在云连接器主机上运行所有 cmdlet，并且必须以管理员身份运行 PowerShell 会话。 
  
|Cmdlet 名称**|描述|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> 版本 1.4.2 及更高版本|将证书颁发机构服务备份到文件，并将其保存到站点共享目录下的 CA 文件夹。|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|使用客户提供的 Windows Server 2012 R2 ISO 文件 (VHDX) 创建基本虚拟硬盘文件。 VHDX 文件将在部署Cloud 连接器期间使用。|
|[Enter-CcUpdate](enter-ccupdate.md)|将云连接器主机服务器置于维护模式，为更新过程做好准备。 设备已“排干”;也就是说，所有现有调用都将完成，但新调用将被拒绝。|
|[Exit-CcUpdate](exit-ccupdate.md)|退出云连接器主机服务器上的更新维护模式。|
|[Export-CcConfiguration](export-ccconfiguration.md)|将Skype for Business 云连接器版本配置导出到Skype for Business 云连接器版本主机服务器上的本地文件。|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|将云连接器示例配置文件 (.ini) 导出到云连接器设备的设备目录。 可以修改和重命名要用于部署的文件。|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> 版本 1.4.2 及更高版本|将根 CA 证书导出到云连接器主机服务器上的本地文件。|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|检索云连接器主机服务器上的工作目录。 所有部署文件都存储在此目录中。|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|显示存储云连接器设备日志的当前目录。|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> 版本 2.1 及更高版本|提供云连接器设备的诊断信息。|
|[Get-CcCredential](get-cccredential.md)|返回当前云连接器部署的凭据。|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|返回云连接器部署的外部证书文件路径。 用户准备此证书。|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和云连接器安装文件。 此文件夹应与云连接器站点的所有其他设备共享。|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|显示存储云连接器的站点级别日志的当前目录。|
|[Get-CcVersion](get-ccversion.md) <p> 版本 2.0 及更高版本|返回 Cloud Connector 实例上的版本。 Get-CCVersion只能在云连接器的主机中使用。|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> 版本 2.0 及更高版本|将Skype for Business 云连接器版本配置从本地文件导入到云连接器主机服务器。|
|[Install-CcAppliance](install-ccappliance.md)|在主机服务器上安装云连接器设备（包括 AD、中央管理Microsoft Store、中介服务器和 Edge Server 虚拟机）。|
|[Publish-CcAppliance](publish-ccappliance.md)|从联机租户配置获取高可用性信息，并将其发布到主机服务器上的云连接器设备。|
|[Register-CcAppliance](register-ccappliance.md)|在联机租户配置中将设备信息注册到 PSTN 站点。 必须先注册设备，然后才能由云连接器管理服务对其进行部署和管理。|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> 版本 1.4.2 及更高版本|在云连接器的站点共享目录下的 CA 文件夹中删除证书颁发机构服务备份文件“\<SiteRootDirectory\>\CA\SfB CCE Root.p12”。|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> 版本 1.4.2 及更高版本|执行 Renew-CcCACertificate 或续订 CcServerCertificate cmdlet 后，删除中央管理Microsoft Store、中介服务器和 Edge Server 上的旧服务器证书。|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> 仅限版本 1.4.2|重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> 仅限版本 1.4.2|在云连接器即将过期或已过期时续订证书。|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> 版本 1.4.2 及更高版本|重置证书颁发机构服务器以安装新的证书颁发机构证书。|
|[Restore-CcCredentials](restore-cccredentials.md) <p> 版本 2.1 及更高版本|清理凭据，并提示你重新输入用于当前云连接器部署的所有凭据。|
|[Search-CcLog](search-cclog.md)|在云连接器设备日志目录中搜索传入和传出呼叫日志|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|在云连接器主机服务器上设置工作目录。 所有部署文件都存储在此目录中。|
|[Set-CcCredential](set-cccredential.md)|设置当前云连接器部署的凭据。|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|指定存储中介服务器或边缘服务器证书的路径|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|设置存储云连接器的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。|
|[Start-CcDownload](start-ccdownload.md)|同步下载云连接器位和 msi 文件。|
|[Start-CcLogging](start-cclogging.md)|为云连接器设备生成传入和传出调用日志。|
|[Stop-CcLogging](stop-cclogging.md)|停止为云连接器设备生成传入和传出呼叫日志。|
|[Switch-CcVersion](switch-ccversion.md)|断开正在运行的设备的连接，并切换到新部署的或备份的设备。|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|从主机服务器卸载正在运行的云连接器设备。|
|[Unregister-CcAppliance](unregister-ccappliance.md)|在联机租户配置中从 PSTN 站点注销当前的云连接器设备。|
|[Update-CcCACertificate](update-cccacertificate.md) <p> 版本 2.0 及更高版本|重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> 版本 2.0 及更高版本|在云连接器即将过期或已过期时续订证书。|
