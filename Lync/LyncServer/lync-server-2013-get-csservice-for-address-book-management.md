---
title: 用于通讯簿管理的 Get-CsService
TOCTitle: 用于通讯簿管理的 Get-CsService
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429698(v=OCS.15)
ms:contentKeyID: 49312483
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于通讯簿管理的 Get-CsService

 

_**上一次修改主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Get-CsService cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-CsService 对检索并显示基础结构定义的 Web 服务的当前配置非常有价值。通过定义池的完全限定域名 (FQDN) 和参数 WebServer，该 cmdlet 可返回服务器提供的基于 Web 的服务，包括通讯簿处理程序和通讯组列表扩展 URI。

例如：

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

此 cmdlet 返回以下值：

Identity :WebServer:pool01.contoso.net

FileStore :FileStore:dc01.contoso.net

UserServer :UserServer:pool01.contoso.net

PrimaryHttpPort :80

PrimaryHttpsPort :443

ExternalHttpPort :8080

ExternalHttpsPort :4443

PublishedPrimaryHttpPort :80

PublishedPrimaryHttpsPort :443

PublishedExternalHttpPort :80

PublishedExternalHttpsPort :443

ReachPrimaryPsomServerPort :8060

ReachExternalPsomServerPort :8061

AppSharingPortStart :49152

AppSharingPortCount :16383

LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri :https://csweb.contoso.com/abs/handler

DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri :https://internalweb.contoso.net/CollabContent

CollabContentExternalUri :https://csweb.contoso.com/CollabContent

CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

DialinExternalUri :https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn :csweb.contoso.com

InternalFqdn :internalweb.contoso.net

DependentServiceList :{Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}

ServiceId :1-WebServices-1

SiteId :Site:Redmond

PoolFqdn :pool01.contoso.net

Version :5

Role :WebServer

有关完整命令的详细说明，请参阅主 Lync Server Windows PowerShell RTCCmdlets 参考中的以下内容。

## 另请参阅

#### 其他资源

[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

