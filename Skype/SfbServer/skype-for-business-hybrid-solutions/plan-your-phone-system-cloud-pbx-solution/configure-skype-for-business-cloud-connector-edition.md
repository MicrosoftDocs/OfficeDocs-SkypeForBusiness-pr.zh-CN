---
title: 配置和管理 Skype for Business 云连接器版本
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 了解如何配置 Skype for Business 云连接器版本，这是一种最低本地拓扑，支持将本地语音基础结构与 Skype for Business Online 中的电话系统 (云 PBX) 语音服务集成。
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094870"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>配置和管理 Skype for Business 云连接器版本
 
> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

了解如何配置 Skype for Business 云连接器版本，这是一种最低本地拓扑，支持将本地语音基础结构与 Skype for Business Online 中的电话系统 (云 PBX) 语音服务集成。 
  
在启动之前，应查看 Plan for [Skype for Business Cloud Connector Edition 中的先决条件](plan-skype-for-business-cloud-connector-edition.md)。
  
> [!IMPORTANT]
> 本主题中的步骤仅适用于云连接器版本 1.4.1 及更高版本。 如果尚未升级到云连接器版本 2.1，请参阅升级到云连接器 [的新版本](upgrade-to-a-new-version-of-cloud-connector.md)。 可以从 下载安装文件 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>配置 Skype for Business 云连接器版本的步骤

下表列出了安装和配置云连接器版本所需的步骤：
  
|**步骤**|**说明**|
|:-----|:-----|
|[准备云连接器设备](prepare-your-cloud-connector-appliance.md) <br/> |下载安装文件、准备证书、配置Hyper-V，并准备好部署云连接器的环境。  <br/> |
|[在云连接器中部署单个站点](deploy-a-single-site-in-cloud-connector.md) <br/> |在云连接器部署中创建站点。  <br/> |
|[在云连接器中部署多个站点](deploy-multiple-sites-in-cloud-connector.md) <br/> |将网站添加到部署，并了解单站点部署和多站点部署之间的差异。  <br/> |
|[配置云连接器与 Microsoft 365 或 Office 365 组织的集成](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |添加 DNS 记录、配置混合、设置 PSTN 网关以及为用户启用电话系统语音邮件。  <br/> |
|[验证云连接器部署](validate-your-cloud-connector-deployment.md) <br/> |确保部署正常运行。  <br/> |
|[升级至新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |将现有的云连接器部署升级到版本 2.1。  <br/> |
|[修改现有云连接器部署的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |部署云连接器后更改其设置。  <br/> |
|[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md) <br/> |了解如何在云连接器中部署媒体旁路。  <br/> |
|[云连接器 cmdlet 参考](cloud-connector-cmdlet-reference.md) <br/> |了解云连接器中使用的 PowerShell cmdlet。  <br/> |
|[对云连接器部署进行故障排除](troubleshoot-your-cloud-connector-deployment.md) <br/> |云连接器部署遇到的常见问题的解决方案。  <br/> |
