---
title: 使用 PowerShell 控制对团队的来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: 使用 PowerShell 在 Microsoft Teams 中允许或阻止对团队的来宾访问
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3bcf91bc6f78951439b051f3cc2d3e827210a9f
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706248"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>使用 PowerShell 控制对团队的来宾访问
================================================

除了使用 Office 365 管理中心和 Azure Active Directory 门户外，你还可以使用 Windows PowerShell 控制来宾访问。 使用 PowerShell 可以执行以下操作：
  
- 允许或阻止来宾访问所有团队和 Office 365 组
    
- 允许将来宾添加到所有团队和 Office 365 组
      
- 在特定团队或 Office 365 组中允许或阻止来宾用户
    
有关详细信息，请参阅[来宾访问 Office 365 组中](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)的管理选项卡上的"使用 PowerShell 来控制来宾访问"一节。
  
你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。 例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。 你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。 有关更多详细信息，请参阅[“允许/阻止对 Office 365 组的来宾访问”](https://go.microsoft.com/fwlink/?linkid=854001)。
  
如果你要在团队中阻止来宾，但仍允许来宾访问 SharePoint 网站，你可以使用 Azure Active Directory Powershell cmdlet 对 Company 对象禁用 AllowGuestAccessToGroups 参数，从而实现对 SharePoint 网站开启外部共享。   

## <a name="guest-access-vs-external-access"></a>与外部访问的来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]