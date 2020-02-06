---
title: 在 Skype for Business 服务器中定义翻译规则
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
description: Skype for Business 服务器企业版语音路由基于规范化为164格式的电话号码进行呼叫。 这意味着，所有已拨打的字符串都必须规范化为 RNL 格式，以便执行反向数字查找（），以便可以将其转换为匹配的 SIP URI。 Skype for business 服务器提供操作被呼叫的 ID 和来电显示演示文稿的功能。
ms.openlocfilehash: cdcfe3a847e148461b97abed33df070057dcd00b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816982"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>在 Skype for Business 服务器中定义翻译规则

Skype for Business 服务器企业版语音路由基于规范化为164格式的电话号码进行呼叫。 这意味着，所有已拨打的字符串都必须规范化为 RNL 格式，以便执行反向数字查找（），以便可以将其转换为匹配的 SIP URI。 Skype for business 服务器提供操作被呼叫的 ID 和来电显示演示文稿的功能。

使用 Skype for Business 服务器，被呼叫方的电话号码（称为电话号码）可以从. 164 格式转换为中继对等（即关联网关、专用分支 exchange （PBX）或 SIP 所需的本地拨号格式）。干线）。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

## <a name="caller-id-presentation"></a>来电显示

Skype for Business 服务器提供的选项还可将呼叫方的电话号码（即呼叫方呼叫的电话号码）从 E-164 格式转换为中继对等所需的本地拨号格式。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

**使用 Skype for Business 服务器控制面板配置呼叫者 ID**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派设置权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。
4. 在 "中继配置" 页面上，双击现有主干（例如**全局**干线）以显示 "**编辑主干配置**" 对话框。
5. 配置呼叫者 ID 显示：
    - 若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则，请单击 "**选择**"。 在“主叫号码转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 
    - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。
    - 若要复制现有翻译规则以用作定义新规则的起始点，请单击规则名称，单击 "**复制**"，然后单击 "**粘贴**"。
    - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。

> [!Warning] 
> 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。 

## <a name="called-id-presentation"></a>名为 "ID 演示文稿"

> [!Important]
> 将一个或多个翻译规则与企业语音中继配置相关联的功能旨在用作在中继对等上配置翻译规则的*替代方法*。 如果你已在中继对等上配置了转换规则，请不要将翻译规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。 

你可以使用以下任一方法来创建或修改翻译规则：

- [使用 "生成翻译规则" 工具](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool)来指定起始数字、长度、要删除的数字和要添加的数字的值，然后让 Skype For Business 服务器控制面板为你生成相应的匹配模式和转换规则。
- [手动编写正则表达式](#create-or-modify-a-translation-rule-manually)以定义匹配的模式和转换规则。

> [!Note]
> 有关如何编写正则表达式的信息，请参阅[.Net Framework 正则表达式](http://go.microsoft.com/fwlink/p/?linkId=140927)。 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>使用 "生成翻译规则" 工具创建或修改翻译规则

如果要定义翻译规则，请执行以下步骤：在 "生成翻译规则" 工具中输入一组值，并启用 "Skype for Business 服务器" 控制面板为你生成相应的匹配模式和转换规则。 

**使用“构建转换规则”工具定义规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派设置权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 若要开始定义翻译规则，请按照通过第10步[配置具有媒体旁路的主干](GET LINK AFTER MIGRATION)中的步骤操作，或在步骤9中[配置不带媒体旁路的主干](GET LINK AFTER MIGRATION)。
4. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 下，键入描述要转换的号码模式的名称。
5. 可选在 "**说明**" 下，键入翻译规则的描述-例如，**美国国际长途拨号**。
6. 在对话框的“构建转换规则”**** 部分的以下字段中输入值：
    - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。 例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。
    - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。例如，输入 **11** 并在下拉列表中选择**At least**可匹配长度至少为 11 位的号码。
    - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如，输入 **1** 将去掉号码开头的 +。
    - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 **011**。
    
    在这些字段中输入的值将反映在 "**要匹配的模式**" 和 "**翻译**规则" 字段中。 例如，如果你指定前面的示例值，则 "**模式" 到 "matc**h" 字段中得到的正则表达式是：
    
    **^\+（\d{9}\d +） $** 

    “转换规则”**** 字段指定转换号码格式的模式。该模式由两部分组成：
    - 代表匹配模式中数字位数的值（例如，**$1**）
    - （可选）可以通过在“要添加的数字”**** 字段中输入来附加的值

    如果使用前面示例中的值，“转换规则”**** 字段中将显示 **011$1**。
    
    应用此转换规则后，+441235551010 将变为 011441235551010。
7. 单击“确定”**** 保存转换规则。
8. 单击“确定”**** 保存中继配置。
9. 在 "**中继 Configuratio**n" 页上，单击 "**提交**"，然后单击 "**全部提交**"。 

> [!Note]
> 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅[将挂起的更改发布到语音路由配置](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 

### <a name="create-or-modify-a-translation-rule-manually"></a>手动创建或修改翻译规则

如果要通过编写匹配模式和转换规则的正则表达式来定义翻译规则，请执行以下步骤。 

**手动定义转换规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派设置权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 若要开始定义翻译规则，请按照通过第10步[配置具有媒体旁路的主干](GET LINK AFTER MIGRATION)中的步骤操作，或在步骤9中[配置不带媒体旁路的主干](GET LINK AFTER MIGRATION)。
4. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 字段中，键入描述要转换的号码模式的名称。
5. 可选在 "**说明**" 中，键入翻译规则的描述;例如，**美国国际长途拨号**。
6. 单击“构建转换规则”**** 部分底部的“编辑”****。
7. 在 "键入**正则表达式**" 中输入以下内容：
    - 在“匹配此模式”**** 中，指定将用于匹配要转换的号码的模式。
    - 在“转换规则”**** 中，指定转换号码格式的模式。

    例如，如果在**转换规则**中输入** ^ \+"（{9}\d \d +） $** "**与此模式**和**011 $ 1**匹配，则规则将 + 441235551010 转换为011441235551010。
8. 单击“确定”**** 保存转换规则。
9. 单击“确定”**** 保存中继配置。
10. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。 

> [!Note] 
> 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅[将挂起的更改发布到语音路由配置](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 
