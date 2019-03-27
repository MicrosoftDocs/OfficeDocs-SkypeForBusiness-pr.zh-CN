---
title: Skype 业务服务器中的定义规范化规则
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 为 Business Server 规范化规则的 Skype 使用.NET Framework 正则表达式转换为 E.164 格式; 拨打的电话号码换句话说，规范化规则执行由用户拨打的电话号码，并将该号码转换为使用内部 Skype 业务服务器的格式。 必须将每个拨号计划分配给一个或多个规范化规则。
ms.openlocfilehash: 8e32ac485763c626d7d4347bb194fb4c4f3dba44
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882472"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Skype 业务服务器中的定义规范化规则

为 Business Server 规范化规则的 Skype 使用.NET Framework 正则表达式转换为 E.164 格式; 拨打的电话号码换句话说，规范化规则执行由用户拨打的电话号码，并将该号码转换为使用内部 Skype 业务服务器的格式。 必须将每个拨号计划分配给一个或多个规范化规则。

有关规范化规则的详细信息，请参阅[拨号计划和规范化规则](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)。

有关如何编写正则表达式的详细信息，请参阅[.NET Framework 正则表达式](http://go.microsoft.com/fwlink/p/?linkId=140927)。

您可以使用下列方法之一以定义或编辑规范化规则：
- [使用**建立规范化规则**工具](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)指定的起始数字、 长度、 要删除的数字和要添加，并让业务 Server 控制面板的 Skype 生成相应的匹配模式和转换规则的数字值给你的。
- [手动编写正则表达式](#create-or-modify-a-normalization-rule-manually)以定义匹配模式和转换规则。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>创建或修改规范化规则使用建立规范化规则

如果您想要创建或修改业务 Server Control Panel 中 Skype 的规范化规则，请完成以下步骤。 

**使用建立规范化规则定义规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于业务控制面板的启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. （可选）请按照[创建拨号计划](GET LINK AFTER MIGRATION)通过步骤 11 或[修改拨号计划](GET LINK AFTER MIGRATION)前 10 个步骤。 
4. 在“新建规范化规则”**** 或“编辑规范化规则”**** 的“名称”**** 中，键入描述要进行规范化的号码模式的名称（例如，**5DigitExtension**）。
5. （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。
6. 在“建立规范化规则”**** 的以下字段中输入值：
    - **起始数字**: （可选） 指定的拨打的号码您想要匹配的模式中的前导零的数字。 例如，如果要使模式与以 425 开头的拨打号码匹配，则键入 **425**。
    - **长度**： 指定的数字位数中匹配模式，选择您想要完全匹配此长度的模式、 匹配的拨打号码的至少此长度，还是匹配的拨打号码的任何长度。
    - **要删除的数字**: （可选） 指定数量的起始数字要从已拨号码中删除您想要匹配的模式。
    - **要添加的数字**: （可选） 指定数字要添加要拨打号码您想要匹配的模式。
    
    这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 中。 例如，如果保留**起始数字**为空，到**长度**字段类型**7** **完全**，选择，然后在**要删除的数字**指定**0** ，在**要匹配模式**中生成的正则表达式:

    **^(\d{7})$**

7. 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式，如下所示：
    - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式 **^(\d{7})$**，然后在转换规则 $1 代表 7 位数字表示已拨的号码。
    - （可选）在“要添加的数字”**** 字段中键入值，指定要附加到转换后的号码前面的数字（例如  **+1425**）。
    
    例如，如果**模式与之匹配**包含 **^(\d{7})$** 因为已拨的号码和**转换规则**的图案包含 **+ 1425年$ 1**该规则会为 + 14255550100 将 5550100 规范化为 E.164 电话号码的模式。

8. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。
9. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。
    > [!Note] 
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)。 

10. 单击“确定”**** 保存规范化规则。
11. 单击“确定”**** 保存拨号计划。
12. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。 
    > [!Note]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅[发布待处理的语音路由配置更改](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手动创建或修改规范化规则

如果您想要手动创建或修改规范化规则，请完成以下步骤。

**手动定义规范化规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于业务控制面板的启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. （可选）请按照[创建拨号计划](GET LINK AFTER MIGRATION)通过步骤 11 或[修改拨号计划](GET LINK AFTER MIGRATION)前 10 个步骤。  
4. 在“新建规范化规则”**** 或“编辑规范化规则”**** 的“名称”**** 中，键入描述要进行规范化的号码模式的名称（例如，将规范化规则命名为 **5DigitExtension**）。
5. （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。
6. 在“建立规范化规则”**** 中，单击“编辑”****。
7. 在“键入正则表达式”中输入以下内容：
    - 在“匹配此模式”**** 中，指定要用于匹配拨打的电话号码的模式。
    - 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式。

    例如，如果输入 **^(\d{7})$** **匹配此模式**中和 **+ 1425年$ 1** **转换规则**，该规则会规范化为 + 14255550100 将 5550100。

8. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。
9. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。

    > [!Note]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)。 

10. 单击“确定”**** 保存规范化规则。
11. 单击“确定”**** 保存拨号计划。
12. 在**拨号计划**页上，单击**Commi**t，然后单击**全部提交**。 
