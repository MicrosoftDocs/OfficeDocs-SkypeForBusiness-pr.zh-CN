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
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="81880-104">呼叫允许控制设置扩展器</span><span class="sxs-lookup"><span data-stu-id="81880-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="81880-p102">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。为 CAC 配置网络后，必须启用 CAC 以强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="81880-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="81880-107">也可以使用控制面板或命令行管理程序 cmdlet 来启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="81880-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="81880-108">在站点的“**编辑属性**”对话框的“**呼叫允许控制设置**”部分中，可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="81880-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="81880-109">**启用呼叫许可控制**选择此设置可启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="81880-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="81880-110">清除此设置为您的整个网络禁用 CAC。</span><span class="sxs-lookup"><span data-stu-id="81880-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="81880-111">若要启用 CAC，必须已配置您的网络的 CAC。</span><span class="sxs-lookup"><span data-stu-id="81880-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="81880-112">有关详细信息，请参阅部署文档中的[调用中业务服务器 2015年的 Skype 的许可控制的部署](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="81880-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="81880-113">**前端池运行调用许可控制**如果您启用了 CAC，您可以更改运行它们的池。</span><span class="sxs-lookup"><span data-stu-id="81880-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="81880-114">从下拉列表中选择池。</span><span class="sxs-lookup"><span data-stu-id="81880-114">Select the pool from the drop-down list.</span></span>
    

