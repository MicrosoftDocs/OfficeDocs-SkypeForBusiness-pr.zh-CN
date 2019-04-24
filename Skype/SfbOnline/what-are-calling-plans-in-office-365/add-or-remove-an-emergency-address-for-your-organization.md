---
title: 为你的组织添加、更改或删除紧急地址
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: f954c67c-b73c-4473-b6cd-a0fbcd0fd4c9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '了解如何将紧急地址添加到 Skype for Business 帐户。 '
ms.openlocfilehash: b3fab8d41c1b6f59961feee09f5eae888d32b362
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32170912"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>为你的组织添加、更改或删除紧急地址

紧急地址必须与一个电话号码，但当发生这种情况之间国家/地区可能各不相同。 例如在美国，向用户分配电话号码时需要关联紧急地址。 在英国，从 Office 365 获取的电话号码或将电话号码从当前的服务提供商转移时号码时需要将紧急地址关联到电话号码。
  
No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address. Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices. See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.
  
若要了解如何获取通话套餐及其价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
## <a name="add-an-emergency-address"></a>添加紧急地址

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧门户**。
    
3. 在左侧导航中，转到**语音** > **紧急位置**，然后单击 **添加新地址**按钮。
    
    > [!Important]
    > 要查看的左侧导航中的业务管理中心 Skype 中的**语音**选项，您必须先购买一个**电话系统**加载项许可证或一个**音频会议**加载项许可证至少一个**企业 E5 许可证**。
    
4. 在操作窗格中，在**新地址**下输入框中所需的信息。
    
5. 您输入的所有地址信息后，单击**验证**。
    
    > [!IMPORTANT]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center. 
    
    > 注意： 比利时，法国、 德国、 爱尔兰、 荷兰和西班牙务必要了解的才能成功激活 Office 365 中将用于获取数，紧急位置的地址设置中的电话号码必须匹配电话号码的区域代码。
  
    如果地址无法验证，如果你验证的是美国地址，可以通过单击**发送验证请求**来发送手动验证请求，或者，如果在美国以外，可单击**打开服务请求以获取地址验证帮助**。
    
6. 在验证地址之后，请单击" **保存**"。
    
## <a name="change-an-emergency-address"></a>更改紧急地址

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧门户**。
    
3. 在左侧导航窗格中，转到**语音** > **紧急位置**，选择您想要更改的地址和操作窗格中单击**编辑**。
    
    > [!IMPORTANT]
    > 要查看的左侧导航中的业务管理中心 Skype 中的**语音**选项，您必须先购买一个**电话系统**加载项许可证或一个**音频会议**加载项许可证至少一个**企业 E5 许可证**。

4. 进行更改，，然后单击**验证**。

5. 单击“**保存**”。

## <a name="remove-an-emergency-address"></a>删除紧急地址

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧门户**。
    
3. 在左侧导航窗格中，转到**语音** > **紧急位置**，选择您想要删除的地址和操作窗格中单击**删除**。
    
    > [!IMPORTANT]
    > 要查看的左侧导航中的业务管理中心 Skype 中的**语音**选项，您必须先购买一个**电话系统**加载项许可证或一个**音频会议**加载项许可证至少一个**企业 E5 许可证**。

## <a name="troubleshooting"></a>疑难解答

**处于"失败"状态的数目。**

获取后从 Office 365 门户的号码，状态更改 **"设置"** 中为 **"失败"**。

通常，数字添加从门户，使用指向某个位置这不匹配的电话的区号紧急地址时，将出现此问题。

若要获取有关拨未正确激活的详细信息，请运行以下 Powershell:
 
> [!语法] Get CsOnlineTelephoneNumber |Where-object {$_。ActivationState cnotcontains"激活"} |fl *

结果，如区域、 id 和 ActivationState，留出其他信息还应包含 CityCode。

**示例**中，对于马德里数，返回 CityCode 将为"EMEA-ES-所有-M_MA"。

如果确实已使用错误的紧急地址，请确保已创建新的紧急地址对应于号码的区域代码并将其分配到的号码。

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧门户**。
    
3. 在左侧导航窗格中，转到**语音** > **电话号码**和数处于 **"失败"** 状态和从右侧网站菜单中，然后双击选择**新紧急地址**。


请注意，更改紧急地址，数字的状态将更改为 **"待处理工作分配"** ，并可能需要 24 小时的成功激活之后。

## <a name="related-topics"></a>相关主题
[什么是紧急位置、地址和呼叫路由？](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
