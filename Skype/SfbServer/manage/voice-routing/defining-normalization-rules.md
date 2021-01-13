---
title: 在 Skype for Business Server 中定义规范化规则
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为 E.164 格式;换句话说，规范化规则采用用户拨打的电话号码，并将该号码转换为 Skype for Business Server 内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823372"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>在 Skype for Business Server 中定义规范化规则

Skype for Business Server 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为 E.164 格式;换句话说，规范化规则采用用户拨打的电话号码，并将该号码转换为 Skype for Business Server 内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。

有关规范化规则的详细信息，请参阅 [拨号计划和规范化规则](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)。

若要详细了解如何编写正则表达式，请参阅 [.NET Framework 正则表达式](https://go.microsoft.com/fwlink/p/?linkId=140927)。

可以使用以下任一方法定义或编辑规范化规则：
- 使用 [**"**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)建立规范化规则"工具指定起始数字、长度、要删除的数字和要添加的数字的值，然后让 Skype for Business Server 控制面板生成相应的匹配模式和转换规则。
- [手动编写正则表达式以](#create-or-modify-a-normalization-rule-manually) 定义匹配模式和转换规则。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用"建立规范化规则"创建或修改规范化规则

如果要在 Skype for Business Server 控制面板中创建或修改规范化规则，请完成以下步骤。 

**使用“建立规范化规则”定义规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅委派 [安装权限](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。
2. 打开浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3.  (可选) 按照步骤 11 中的步骤创建[](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan)拨号计划或通过步骤 10[](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan)修改拨号计划。 
4. 在“新建规范化规则”或“编辑规范化规则”的“名称”中，键入描述要进行规范化的号码模式的名称（例如，**5DigitExtension**）。
5. （可选）在“描述”中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。
6. 在“建立规范化规则”的以下字段中输入值：
    - **起始数字**： (可选) 指定希望模式匹配的已拨号码的前导数字。 例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425**。
    - **Length**： Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly， match dialed numbers that are least that are least this length， or match dialed numbers of any length.
    - **要删除** 的数字： (可选) 指定要从希望模式匹配的已拨号码中删除的起始位数。
    - **要添加的数字： (** 可选) 指定要添加到希望模式匹配的拨打号码的数字。
    
    这些字段中输入的值将反映在“要匹配的模式”和“转换规则”中。 例如，如果将起始数字留空，请在"长度"字段中键入 **7，** 选择 **"** 完全"，并指定要删除的 **Digits** 中的 **0，** 则 Pattern 中要匹配的生成的 **正则表达式为：** 

    **^ (\d {7}) $**

7. 在“转换规则”中，指定转换后的 E.164 电话号码格式的模式，如下所示：
    - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式 **为 ^ (\d) {7} $**，则转换规则中的 $1 表示 7 位拨打的号码。
    - （可选）在“要添加的数字”字段中键入值，指定要附加到转换后的号码前面的数字（例如 **+1425**）。
    
    例如，如果要匹配的 **Pattern** 包含 **^ (\d {7}) $** 作为拨打号码的模式，而 **转换** 规则包含 **+1425$1** 作为 E.164 电话号码的模式，则规则将 5550100 规范化为 +14255550100。

8. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”。
9. （可选）输入一个号码以测试规范化规则，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。
    > [!Note] 
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅["测试语音路由"。](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. 单击“确定”保存规范化规则。
11. 单击“确定”保存拨号计划。
12. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。 
    > [!Note]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅["发布对语音路由配置挂起的更改"。](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手动创建或修改规范化规则

如果要手动创建或修改规范化规则，请执行以下步骤。

**手动定义规范化规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅委派 [安装权限](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。
2. 打开浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3.  (可选) 按照步骤 11 中的步骤创建[](GET LINK AFTER MIGRATION)拨号计划或通过步骤 10[](GET LINK AFTER MIGRATION)修改拨号计划。  
4. 在“新建规范化规则”或“编辑规范化规则”的“名称”中，键入描述要进行规范化的号码模式的名称（例如，将规范化规则命名为 **5DigitExtension**）。
5. （可选）在“描述”中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。
6. 在“建立规范化规则”中，单击“编辑”。
7. 在“键入正则表达式”中输入以下内容：
    - 在“匹配此模式”中，指定要用于匹配拨打的电话号码的模式。
    - 在“转换规则”中，指定转换后的 E.164 电话号码格式的模式。

    例如，如果在"匹配"模式中输入 **^ {7} (\d) $** ，在 **转换** 规则中输入 **+1425$1，** 则规则将 5550100 规范化为 +14255550100。 

8. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”。
9. （可选）输入一个号码以测试规范化规则，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。

    > [!Note]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅["测试语音路由"。](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. 单击“确定”保存规范化规则。
11. 单击“确定”保存拨号计划。
12. 在"**拨号计划"** 页上，单击 **"Commi** t"，然后单击"**全部提交"。** 
