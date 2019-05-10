---
title: 使用 PowerShell 控制对团队的来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 使用 PowerShell 在 Microsoft Teams 中允许或阻止对团队的来宾访问
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ca05e48d28986a944debe150d5dbf25129ca73c
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827666"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>使用 PowerShell 控制对团队的来宾访问
================================================

除了使用 Office 365 管理中心和 Azure Active Directory 门户外，你还可以使用 Windows PowerShell 控制来宾访问。 使用 PowerShell 可以执行以下操作：
  
- 允许或阻止来宾访问所有团队和 Office 365 组
    
- 允许将来宾添加到所有团队和 Office 365 组
      
- 在特定团队或 Office 365 组中允许或阻止来宾用户
    
有关详细信息，请参阅[来宾访问 Office 365 组中](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)的管理选项卡上的"使用 PowerShell 来控制来宾访问"一节。
  
你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。 例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。 你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。 有关更多详细信息，请参阅[“允许/阻止对 Office 365 组的来宾访问”](https://go.microsoft.com/fwlink/?linkid=854001)。
  
如果您想要阻止在团队中的来宾并且仍要允许其访问 SharePoint 网站，您可以使用 Azure Active Directory Powershell cmdlet 禁用对公司的对象的 AllowGuestsToAccessGroups 参数假定外部共享为打开SharePoint 网站。   

## <a name="guest-access-vs-external-access"></a>与外部访问的来宾访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
