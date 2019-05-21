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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '了解如何将紧急地址添加到 Skype for Business 帐户。 '
ms.openlocfilehash: 5c22875873d2164c14d690523404481a514ef388
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293732"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>为你的组织添加、更改或删除紧急地址

紧急地址必须与电话号码相关联, 但是如果发生这种情况, 国家/地区之间可能会有所不同。 例如在美国，向用户分配电话号码时需要关联紧急地址。 在英国，从 Office 365 获取的电话号码或将电话号码从当前的服务提供商转移时号码时需要将紧急地址关联到电话号码。
  
No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address. Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices. See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.
  
若要了解如何获取通话套餐及其价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
## <a name="add-an-emergency-address"></a>添加紧急地址

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧版门户**。
    
3. 在左侧导航中，转到**语音** > **紧急位置**，然后单击 **添加新地址**按钮。
    
    > [!Important]
    > 要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。
    
4. 在操作窗格中，在**新地址**下输入框中所需的信息。
    
5. 输入地址的所有信息后, 单击 "**验证**"。
    
    > [!IMPORTANT]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center. 
    
    > 注意: 在比利时、法国、德国、爱尔兰、荷兰和西班牙, 请务必了解, 为了成功激活 Office 365 中的电话号码, 在紧急位置 (将用于获取号码) 中的地址设置必须与电话号码的区号。
  
    如果地址无法验证，如果你验证的是美国地址，可以通过单击**发送验证请求**来发送手动验证请求，或者，如果在美国以外，可单击**打开服务请求以获取地址验证帮助**。
    
6. 在验证地址之后，请单击" **保存**"。
    
## <a name="change-an-emergency-address"></a>更改紧急地址

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧版门户**。
    
3. 在左侧导航中, 转到 "**语音** > **紧急位置**", 选择要更改的地址, 然后在 "操作" 窗格中单击 "**编辑**"。
    
    > [!IMPORTANT]
    > 要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。

4. 进行更改, 然后单击 "**验证**"。

5. 单击“**保存**”。

## <a name="remove-an-emergency-address"></a>删除紧急地址

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧版门户**。
    
3. 在左侧导航中, 转到 "**语音** > **紧急位置**", 选择要删除的地址, 然后在 "操作" 窗格中单击 "**删除**"。
    
    > [!IMPORTANT]
    > 要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。

## <a name="troubleshooting"></a>疑难解答

**"失败" 状态中的数字。**

从 Office 365 门户获取数字后, 状态从 **"预配"** 更改为 **"失败"**。

当从门户添加数字时, 通常会出现此问题, 使用的紧急地址指向的位置与电话的区域代码不匹配。

若要获取有关未正确激活的号码的详细信息, 请运行以下 Powershell:
 
> [!语法] CsOnlineTelephoneNumber |其中-对象 {$ _。ActivationState-cnotcontains "已激活"} |市

结果, 除了区域、id 和 ActivationState 之类的其他信息之外, 还应包含 CityCode。

**例如**, 对于马德里号码, 返回的 CityCode 将为 "EMEA-ES-M_MA"。

如果确实使用了错误的紧急地址, 请确保您已创建了一个与号码区号对应的新紧急地址, 并将其分配给号码。

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 团队管理中心** > **旧版门户**。
    
3. 在左侧导航中, 转到 "**语音** > **电话号码**", 然后双击 **"失败"** 状态中的数字, 然后单击 "右手网站" 菜单, 选择新的**紧急地址**。


请注意, 更改紧急地址后, 号码的状态将更改为 **"作业挂起"** , 并且最多可能需要24小时才能成功激活。

## <a name="related-topics"></a>相关主题
[什么是紧急位置、地址和呼叫路由？](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
