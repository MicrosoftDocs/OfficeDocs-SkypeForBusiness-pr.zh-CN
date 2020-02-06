---
title: 在 Skype for Business 服务器中定义规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business 服务器规范化规则使用 .NET Framework 正则表达式将已拨打的电话号码转换为 E-164 格式;换句话说，规范化规则获取用户拨打的电话号码，并将该号码转换为 Skype for Business 服务器在内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。
ms.openlocfilehash: ed9db264dc637251c535f111e419aac9aa0f5e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816992"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>在 Skype for Business 服务器中定义规范化规则

Skype for Business 服务器规范化规则使用 .NET Framework 正则表达式将已拨打的电话号码转换为 E-164 格式;换句话说，规范化规则获取用户拨打的电话号码，并将该号码转换为 Skype for Business 服务器在内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。

有关规范化规则的详细信息，请参阅[拨号计划和规范化规则](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)。

有关如何编写正则表达式的详细信息，请参阅[.Net Framework 正则表达式](http://go.microsoft.com/fwlink/p/?linkId=140927)。

你可以使用以下任一方法来定义或编辑规范化规则：
- [使用 "**生成规范化规则**" 工具](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)来指定起始数字、长度、要删除的数字和要添加的数字的值，然后让 Skype for business 服务器控制面板为你生成相应的匹配模式和转换规则。
- [手动编写正则表达式](#create-or-modify-a-normalization-rule-manually)以定义匹配的模式和转换规则。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用构建规范化规则创建或修改规范化规则

如果要在 Skype for Business Server 控制面板中创建或修改规范化规则，请完成以下步骤。 

**使用构建规范化规则定义规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派设置权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 可选按照步骤 11[创建拨号计划](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan)或通过步骤 10[修改拨号计划](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan)中的步骤进行操作。 
4. 在“新建规范化规则”**** 或“编辑规范化规则”**** 的“名称”**** 中，键入描述要进行规范化的号码模式的名称（例如，**5DigitExtension**）。
5. （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。
6. 在“建立规范化规则”**** 的以下字段中输入值：
    - **开始数字**：（可选）指定你希望模式匹配的已拨号码的前导数字。 例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425**。
    - **长度**：指定匹配模式中的位数，并选择是希望模式完全匹配此长度、匹配至少具有此长度的电话号码，还是匹配任何长度的已拨打号码。
    - **要删除的数字**：（可选）指定要从所需模式匹配的已拨号码的起始位数。
    - **要添加的数字**：（可选）指定要为模式匹配的已拨号码的数字。
    
    这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 中。 例如，如果将开始的**数字**保留为空，请在 "**长度**" 字段中键入 " **7** **"，然后**指定 "要删除的数字"，若**要删除** **0** ，则**模式**中的结果正则表达式如下所示：

    **^ （\d{7}） $**

7. 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式，如下所示：
    - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式为 **^ （\d{7}） $**，则翻译规则中的 $1 表示7位拨入号码。
    - （可选）在“要添加的数字”**** 字段中键入值，指定要附加到转换后的号码前面的数字（例如  **+1425**）。
    
    例如，如果**要匹配的模式**包含 **^ （\d{7}） $** 作为拨号号码和**翻译规则**的模式，则将 **+ 1425 $ 1**用作 E. 164 电话号码的模式，规则将5550100标准化到 + 14255550100。

8. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。
9. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。
    > [!Note] 
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)。 

10. 单击“确定”**** 保存规范化规则。
11. 单击“确定”**** 保存拨号计划。
12. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。 
    > [!Note]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅[将挂起的更改发布到语音路由配置](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手动创建或修改规范化规则

如果要手动创建或修改规范化规则，请完成以下步骤。

**手动定义规范化规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派设置权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 可选按照步骤 11[创建拨号计划](GET LINK AFTER MIGRATION)或通过步骤 10[修改拨号计划](GET LINK AFTER MIGRATION)中的步骤进行操作。  
4. 在“新建规范化规则”**** 或“编辑规范化规则”**** 的“名称”**** 中，键入描述要进行规范化的号码模式的名称（例如，将规范化规则命名为 **5DigitExtension**）。
5. （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。
6. 在“建立规范化规则”**** 中，单击“编辑”****。
7. 在“键入正则表达式”中输入以下内容：
    - 在“匹配此模式”**** 中，指定要用于匹配拨打的电话号码的模式。
    - 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式。

    例如，如果你在**翻译规则**中输入 " **^ （\d{7}） $** " 与**此模式** **+ 1425 $ 1** ，则规则会将5550100规范化到 + 14255550100。

8. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。
9. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。

    > [!Note]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)。 

10. 单击“确定”**** 保存规范化规则。
11. 单击“确定”**** 保存拨号计划。
12. 在 "**拨号计划**" 页面上，单击 " **Commi**t"，然后单击 "**全部提交**"。 
