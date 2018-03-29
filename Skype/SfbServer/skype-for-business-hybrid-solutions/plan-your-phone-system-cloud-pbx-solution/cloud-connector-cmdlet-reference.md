---
title: 云连接器 cmdlet 参考
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
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>云连接器 cmdlet 参考
 
下表列出了 Skype for Business 云连接器版本 cmdlet，并带有简要说明和指向详细信息的链接。
  
> [!NOTE]
> 必须在云连接器主机上运行所有 cmdlet，并且必须以管理员身份运行 PowerShell 会话。 
  
|**Cmdlet 名称**|**说明**|
|:-----|:-----|
|[备份-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 1.4.2 版及更高版本  <br/> |将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。     <br/> |
|[转换-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署云连接器的过程中使用。  <br/> |
|[输入 CcUpdate](enter-ccupdate.md) <br/> |通过将云连接器主机服务器置于维护模式来为更新过程做准备。 该装置是"排放;"也就是说，所有现有呼叫将完成，但新的呼叫都将被拒绝。  <br/> |
|[退出-CcUpdate](exit-ccupdate.md) <br/> |在云连接器主机服务器上退出更新维护模式。  <br/> |
|[导出 CcConfiguration](export-ccconfiguration.md) <br/> | 用于将 Skype for Business 云连接器版本配置导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 <br/> |
|[导出 CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |将一个云连接器示例配置文件 (.ini) 导出到云接口装置的设备目录。 你可以修改和重命名该文件以用于你的部署。  <br/> |
|[导出 CcRootCertificate](export-ccrootcertificate.md) <br/> 1.4.2 版及更高版本  <br/> |将根 CA 证书导出到云连接器主机服务器上的一个本地文件。  <br/> |
|[获得 CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |检索云连接器主机服务器上的工作目录。所有部署文件都存储在此目录中。  <br/> |
|[获得 CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |显示当前目录存储日志的云接头装置.  <br/> |
|[获得 CcApplianceStatus](get-ccappliancestatus.md) <br/> 版本 2.1 或更高版本  <br/> |提供云接口装置的诊断信息。  <br/> |
|[获得 CcCredential](get-cccredential.md) <br/> |返回当前云连接器部署的凭据。  <br/> |
|[获得 CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |返回云连接器部署的外部证书文件路径。用户准备此证书。  <br/> |
|[获得 CcSiteDirectory](get-ccsitedirectory.md) <br/> |显示存储站点级别配置文件的当前目录。 该文件夹包含基 VHD 和云接头安装文件。 应与云连接器站点的所有其他设备共享此文件夹。  <br/> |
|[获得 CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |显示当前目录云连接器站点级别记录的存储位置。  <br/> |
|[获得 CcVersion](get-ccversion.md) <br/> 2.0 版及更高版本  <br/> |返回云连接器实例上的版本。Get-CCVersion 只能用于云连接器的主机。  <br/> |
|[导入 CcConfiguration](import-ccconfiguration.md) <br/> 2.0 版及更高版本  <br/> |将 Skype 商务云连接器版配置从本地文件导入到云连接器宿主服务器上。  <br/> |
|[安装 CcAppliance](install-ccappliance.md) <br/> |安装云接头装置 — — 包括广告、 中央管理存储、 中介服务器和边缘服务器虚拟机 — — 在主机服务器上。  <br/> |
|[将发布 CcAppliance](publish-ccappliance.md) <br/> | 获取从联机租户配置高可用性的信息，并将其发布到主机服务器上云接头装置。 <br/> |
|[注册 CcAppliance](register-ccappliance.md) <br/> | 将设备信息注册到联机租户配置中的 PSTN 站点。 部署和管理的云连接器管理服务之前，必须注册装置。 <br/> |
|[删除 CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 1.4.2 版及更高版本  <br/> |删除证书颁发机构服务备份文件"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"云连接器的站点共享目录下的 CA 中。  <br/> |
|[删除 CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 1.4.2 版及更高版本  <br/> |在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。  <br/> |
|[续订 CcCACertificate](renew-cccacertificate.md) <br/> 仅限于版本 1.4.2  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[续订 CcServerCertificate](renew-ccservercertificate.md) <br/> 仅限于版本 1.4.2  <br/> |在云连接器的证书将要过期或已经过期时续订证书。  <br/> |
|[重置-CcCACertificate](reset-cccacertificate.md) <br/> 1.4.2 版及更高版本  <br/> |将安装新的证书颁发机构证书的证书颁发机构服务器重置。  <br/> |
|[还原-CcCredentials](restore-cccredentials.md) <br/> 版本 2.1 或更高版本  <br/> |清理的凭据，并提示您重新输入用于云连接器当前部署的所有凭据。  <br/> |
|[搜索-CcLog](search-cclog.md) <br/> |在云连接器设备日志目录中搜索传入和传出呼叫日志  <br/> |
|[一组 CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |在云连接器宿主服务器上设置的工作目录。 所有部署文件都存储在此目录中。  <br/> |
|[一组 CcCredential](set-cccredential.md) <br/> |设置当前云连接器部署的凭据。  <br/> |
|[一组 CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |指定中介服务器或边缘服务器的证书的存储路径  <br/> |
|[一组 CcSiteDirectory](set-ccsitedirectory.md) <br/> |设置将存储云连接器的站点级别配置文件的目录。该文件夹将包含基本 VHD 和云连接器配置文件。  <br/> |
|[开始-CcDownload](start-ccdownload.md) <br/> |同步下载云连接器位和 msi 文件。  <br/> |
|[开始-CcLogging](start-cclogging.md) <br/> |生成云接头装置传入和传出的呼叫的日志。  <br/> |
|[Stop CcLogging](stop-cclogging.md) <br/> |停止生成传入和传出的云接头装置电话记录。  <br/> |
|[开关 CcVersion](switch-ccversion.md) <br/> |将正在运行的设备断开连接，并切换到新部署的设备或备份设备。  <br/> |
|[卸载-CcAppliance](uninstall-ccappliance.md) <br/> |从主机服务器中卸载正在运行的云接头装置。  <br/> |
|[取消注册 CcAppliance](unregister-ccappliance.md) <br/> |注销当前云接头装置通过 PSTN 网站在线租户配置中。  <br/> |
|[更新 CcCACertificate](update-cccacertificate.md) <br/> 2.0 版及更高版本  <br/> |重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。  <br/> |
|[更新 CcServerCertificate](update-ccservercertificate.md) <br/> 2.0 版及更高版本  <br/> |在云连接器的证书将要过期或已经过期时续订证书。  <br/> |
   

