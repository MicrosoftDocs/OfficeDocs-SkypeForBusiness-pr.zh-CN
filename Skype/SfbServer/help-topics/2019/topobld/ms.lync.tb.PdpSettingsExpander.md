---
title: 呼叫允许控制设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: e05d4b480472289560c3d1f517e725fadf7288bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829912"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="f42dc-104">呼叫允许控制设置扩展器</span><span class="sxs-lookup"><span data-stu-id="f42dc-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="f42dc-p102">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f42dc-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f42dc-107">您还可以使用控制面板或命令行管理程序 cmdlet 启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="f42dc-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="f42dc-108">在站点的 **“编辑属性”** 对话框的 **“呼叫允许控制设置”** 部分中，可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="f42dc-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="f42dc-109">**启用呼叫允许控制** 选择此设置可启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="f42dc-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="f42dc-110">清除此设置以禁用整个网络的 CAC。</span><span class="sxs-lookup"><span data-stu-id="f42dc-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="f42dc-111">若要启用 CAC，必须为 CAC 配置网络。</span><span class="sxs-lookup"><span data-stu-id="f42dc-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="f42dc-112">有关详细信息，请参阅 [部署文档中的 Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 中的部署呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="f42dc-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="f42dc-113">**运行呼叫允许控制的前端池** 如果启用 CAC，可以更改运行 CAC 的池。</span><span class="sxs-lookup"><span data-stu-id="f42dc-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="f42dc-114">从下拉列表中选择池。</span><span class="sxs-lookup"><span data-stu-id="f42dc-114">Select the pool from the drop-down list.</span></span>
    

