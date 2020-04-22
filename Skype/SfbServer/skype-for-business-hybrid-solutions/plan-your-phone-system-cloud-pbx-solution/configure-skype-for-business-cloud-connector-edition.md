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
description: 了解如何配置 Skype for Business 云连接器版本，这是一种最少的本地拓扑，可在 Skype for business Online 的 Office 365 （云 PBX）语音服务中将本地语音基础结构与电话系统集成。
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779158"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>配置和管理 Skype for Business 云连接器版本
 
了解如何配置 Skype for Business 云连接器版本，这是一种最少的本地拓扑，可在 Skype for business Online 的 Office 365 （云 PBX）语音服务中将本地语音基础结构与电话系统集成。 
  
在开始之前，应查看[Plan For Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)中的先决条件。
  
> [!IMPORTANT]
> 本主题中的步骤仅适用于云连接器版本1.4.1 和更高版本。 如果尚未升级到云连接器版本2.1，请参阅[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。 您可以从[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)下载安装文件。 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>配置 Skype for Business 云连接器版本的步骤

下表列出了安装和配置云连接器版本所需的步骤：
  
|**步骤**|**说明**|
|:-----|:-----|
|[准备云连接器设备](prepare-your-cloud-connector-appliance.md) <br/> |下载安装文件、准备证书、配置 Hyper-v，并让你的环境为你的云连接器部署做好准备。  <br/> |
|[在云连接器中部署单个网站](deploy-a-single-site-in-cloud-connector.md) <br/> |在你的云连接器部署中创建网站。  <br/> |
|[在云连接器中部署多个网站](deploy-multiple-sites-in-cloud-connector.md) <br/> |将网站添加到部署，并了解单站点部署与多站点部署之间的差异。  <br/> |
|[配置与 Office 365 组织的云连接器集成](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |添加 DNS 记录，配置混合配置，设置 PSTN 网关，并为用户启用 Office 365 语音邮件中的电话系统。  <br/> |
|[验证你的云连接器部署](validate-your-cloud-connector-deployment.md) <br/> |请确保您的部署正常运行。  <br/> |
|[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |将现有云连接器部署升级到版本2.1。  <br/> |
|[修改现有云连接器部署的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |在云连接器中更改已部署的设置后对其进行更改。  <br/> |
|[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md) <br/> |了解如何在云连接器中部署媒体旁路。  <br/> |
|[云连接器 cmdlet 参考](cloud-connector-cmdlet-reference.md) <br/> |了解在云连接器中使用的 PowerShell cmdlet。  <br/> |
|[对云连接器部署进行故障排除](troubleshoot-your-cloud-connector-deployment.md) <br/> |部署云连接器时遇到的常见问题的解决方案。  <br/> |
   

