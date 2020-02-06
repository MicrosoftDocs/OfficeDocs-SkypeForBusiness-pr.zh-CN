---
title: 呼叫允许控制设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: 呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。
ms.openlocfilehash: cde55ba3cf6edb61e8a37f581341b7e5f6c11f45
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797253"
---
# <a name="call-admission-control-settings-expander"></a>呼叫允许控制设置扩展器
 
呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。 
  
> [!NOTE]
> 也可以使用控制面板或命令行管理程序 cmdlet 来启用 CAC。 
  
在站点的“**编辑属性**”对话框的“**呼叫允许控制设置**”部分中，可以更改以下设置：
  
- **启用呼叫许可控制**选择此设置以启用 CAC。 清除此设置以禁用整个网络的 CAC。 若要启用 CAC，您必须已将网络配置为 CAC。 有关详细信息，请参阅部署文档中的[Skype For Business 服务器中的 "部署呼叫许可控制](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)"。
    
- **用于运行呼叫许可控制的前端池**如果启用了 CAC，则可以更改运行它的池。 从下拉列表中选择 "池"。
    

