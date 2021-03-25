---
title: CMS 设置扩展器
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
- ms.lync.tb.CmsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4b882923-ed6f-44f3-ad9c-aabad5a3bc00
description: 可以将中央管理服务器从一个定义的前端池更改为另一个定义的前端池。 要更改中央管理服务器的位置，请从“要在其上安装中央管理服务器的前端服务器”下的下拉列表中选择前端池。 前端服务器可以是 Enterprise Edition 前端池或 Standard Edition 前端服务器。
ms.openlocfilehash: 42b4d4856e32929a9b56e69edfcf48d13f8ab66d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122456"
---
# <a name="cms-settings-expander"></a><span data-ttu-id="62557-105">CMS 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="62557-105">CMS Settings Expander</span></span>
 
<span data-ttu-id="62557-p102">可以将中央管理服务器从一个定义的前端池更改为另一个定义的前端池。要更改中央管理服务器的位置，请从“要安装中央管理服务器的前端服务器位置”下的下拉列表中选择前端池。前端服务器可以是 Enterprise Edition 前端池或 Standard Edition 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="62557-p102">The Central Management Server can be changed from one defined Front End pool to another defined Front End pool. To change the location of the Central Management Server, select the Front End pool from the drop-down list under **Front End server to install Central Management Server on**. A Front End Server can be an Enterprise Edition Front End pool or a Standard Edition Front End Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62557-109">如果已为基础结构定义、发布并部署中央管理存储，则在不通过外部进程将中央管理存储重新定位至其他前端的情况下，无法更改中央管理存储的位置。</span><span class="sxs-lookup"><span data-stu-id="62557-109">If you have defined, published, and deployed the Central Management store for the infrastructure, you cannot change the location of the Central Management store without relocating the Central Management store to another Front End by an external process.</span></span> 
  
<span data-ttu-id="62557-110">有关移动中央管理服务器存储的详细信息，请参阅 Windows PowerShell cmdlet 参考中的[Move-CsManagementServer。](/powershell/module/skype/move-csmanagementserver?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="62557-110">For details about moving the Central Management Server store, see [Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps) in the Windows PowerShell cmdlet reference.</span></span>
