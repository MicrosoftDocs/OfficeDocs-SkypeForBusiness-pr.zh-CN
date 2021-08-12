---
title: 呼叫允许控制设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。
ms.openlocfilehash: c4cf3fb84e8c7a4cb9fea9f6092054d37278c52a4e441d52dce72734b37906e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298292"
---
# <a name="call-admission-control-settings-expander"></a>呼叫允许控制设置扩展器
 
呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。 
  
> [!NOTE]
> 您还可以使用控制面板或命令行管理程序 cmdlet 启用 CAC。 
  
在站点的 **“编辑属性”** 对话框的 **“呼叫允许控制设置”** 部分中，可以更改以下设置：
  
- **启用呼叫允许控制** 选择此设置可启用 CAC。 清除此设置可禁用整个网络的 CAC。 若要启用 CAC，必须为 CAC 配置网络。 有关详细信息，请参阅部署[文档中的 Deploy call admission control in Skype for Business Server 2015。](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)
    
- **运行呼叫允许控制的前端池** 如果启用 CAC，可以更改运行它的池。 从下拉列表中选择池。
    

