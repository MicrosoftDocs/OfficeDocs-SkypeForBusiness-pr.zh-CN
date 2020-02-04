---
title: 呼叫允许控制设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: 呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。
ms.openlocfilehash: 345668c61697dfa90e9e511d98ac82e6468440cc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684855"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="c87a4-104">呼叫允许控制设置扩展器</span><span class="sxs-lookup"><span data-stu-id="c87a4-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="c87a4-p102">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="c87a4-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c87a4-107">也可以使用控制面板或命令行管理程序 cmdlet 来启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="c87a4-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="c87a4-108">在站点的“**编辑属性**”对话框的“**呼叫允许控制设置**”部分中，可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="c87a4-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="c87a4-109">**启用呼叫许可控制**选择此设置以启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="c87a4-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="c87a4-110">清除此设置以禁用整个网络的 CAC。</span><span class="sxs-lookup"><span data-stu-id="c87a4-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="c87a4-111">若要启用 CAC，您必须已将网络配置为 CAC。</span><span class="sxs-lookup"><span data-stu-id="c87a4-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="c87a4-112">有关详细信息，请参阅部署文档中[Skype For Business Server 2015 中的 "部署呼叫许可控制](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)"。</span><span class="sxs-lookup"><span data-stu-id="c87a4-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="c87a4-113">**用于运行呼叫许可控制的前端池**如果启用了 CAC，则可以更改运行它的池。</span><span class="sxs-lookup"><span data-stu-id="c87a4-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="c87a4-114">从下拉列表中选择 "池"。</span><span class="sxs-lookup"><span data-stu-id="c87a4-114">Select the pool from the drop-down list.</span></span>
    

