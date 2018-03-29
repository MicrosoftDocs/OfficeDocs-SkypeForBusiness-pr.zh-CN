---
title: 呼叫允许控制设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。
ms.openlocfilehash: 9c3645b259949e208bd8bf6d0bc9d240ec5fe2e2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-settings-expander"></a>呼叫允许控制设置扩展器
 
呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。 
  
> [!NOTE]
> 也可以使用控制面板或命令行管理程序 cmdlet 来启用 CAC。 
  
在站点的“**编辑属性**”对话框的“**呼叫允许控制设置**”部分中，可以更改以下设置：
  
- **启用呼叫许可控制**选择此设置可启用 CAC。 清除此设置为您的整个网络禁用 CAC。 若要启用 CAC，必须已配置您的网络的 CAC。 有关详细信息，请参阅部署文档中的[调用中业务服务器 2015年的 Skype 的许可控制的部署](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)。
    
- **前端池运行调用许可控制**如果您启用了 CAC，您可以更改运行它们的池。 从下拉列表中选择池。
    

