---
title: Skype 业务服务器中的定义转换规则
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 业务 Server 企业语音的 Skype 将基于电话号码规范化为 E.164 格式的呼叫路由。 这意味着，将所拨打的所有字符串必须都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会，以便他们可以转换为其匹配的 SIP URI。 Skype 业务服务器提供操作呼叫的 ID 和呼叫者 ID 演示文稿的功能。
ms.openlocfilehash: b85241cfa7fc8f14732c92994660cdeb2088c874
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214650"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Skype 业务服务器中的定义转换规则

业务 Server 企业语音的 Skype 将基于电话号码规范化为 E.164 格式的呼叫路由。 这意味着，将所拨打的所有字符串必须都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会，以便他们可以转换为其匹配的 SIP URI。 Skype 业务服务器提供操作呼叫的 ID 和呼叫者 ID 演示文稿的功能。

与 Skype 的企业服务器，调用的方的电话号码 （即，调用的电话号码） 可以由 E.164 格式转换为本地拨号格式所需的中继对等方 （即，关联的网关、 专用交换机 (PBX) 或 SIP中继）。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

## <a name="caller-id-presentation"></a>呼叫者 ID 演示文稿

Skype 业务服务器为本地拨号格式所需的中继对等方从 E.164 格式提供还平移呼叫方的电话号码 （即，呼叫者呼叫的电话号码） 的选项。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

**使用适用于业务 Server Control Panel Skype 配置呼叫者 ID**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于业务控制面板的启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。
4. 在 Trunk 配置页上，双击某个现有的中继 （例如，**全局**中继） 以显示**编辑 Trunk 配置**对话框。
5. 配置呼叫者 ID 显示：
    - 若要从企业语音部署中可用的所有转换规则的列表中选择一个或多个规则，请单击**选择**。 在“主叫号码转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 
    - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。
    - 若要复制现有的转换规则要作为起点，用于定义一个新规则，单击规则名称，单击**复制**，然后单击**粘贴**。
    - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。

> [!Warning] 
> 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。 

## <a name="called-id-presentation"></a>呼叫的 ID 演示文稿

> [!Important]
> 将一个或多个转换规则与企业语音中继配置相关联的功能旨在用作*替代*中继对等方上配置转换规则。 不关联转换规则与企业语音中继配置如果已在中继对等方上配置转换规则，因为这两种规则可能会发生冲突。 

您可以使用下列方法之一可创建或修改转换规则：

- [使用生成的转换规则工具](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool)指定的起始数字、 长度、 要删除的数字和要添加，并让业务 Server 控制面板的 Skype 为您生成相应的匹配模式和转换规则的数字值。
- [手动编写正则表达式](#create-or-modify-a-translation-rule-manually)以定义匹配模式和转换规则。

> [!Note]
> 有关如何编写正则表达式的信息，请参阅[.NET Framework 正则表达式](http://go.microsoft.com/fwlink/p/?linkId=140927)。 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>创建或修改转换规则使用建立转换规则工具

如果您想要在生成的转换规则工具中输入的一组值和启用业务 Server 控制面板为您生成的相应匹配模式和转换规则的 Skype 定义转换规则，请按照以下步骤。 

**使用“构建转换规则”工具定义规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于业务控制面板的启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 要开始定义转换规则，请按照中的步骤[配置与媒体中继绕过](GET LINK AFTER MIGRATION)通过 10 个步骤或[配置无媒体中继绕过](GET LINK AFTER MIGRATION)前 9 个步骤。
4. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 下，键入描述要转换的号码模式的名称。
5. （可选）在**说明**，键入转换规则-例如，**美国国际长途拨号**的说明。
6. 在对话框的“构建转换规则”**** 部分的以下字段中输入值：
    - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。 例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。
    - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。例如，输入 **11** 并在下拉列表中选择**At least**可匹配长度至少为 11 位的号码。
    - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如，输入 **1** 将去掉号码开头的 +。
    - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 **011**。
    
    在这些字段中输入的值都反映在**要匹配模式**和**转换**规则字段中。 例如，如果指定上述示例中的值时，生成的正则表达式**模式 matc**h 字段中是：
    
    **^\+(\d{9}\d+)$** 

    “转换规则”**** 字段指定转换号码格式的模式。该模式由两部分组成：
    - 代表匹配模式中数字位数的值（例如，**$1**）
    - （可选）可以通过在“要添加的数字”**** 字段中输入来附加的值

    如果使用前面示例中的值，“转换规则”**** 字段中将显示 **011$1**。
    
    应用此转换规则后，+441235551010 将变为 011441235551010。
7. 单击“确定”**** 保存转换规则。
8. 单击“确定”**** 保存中继配置。
9. 在**中继配置**n 页上，单击**提交**，，然后单击**全部提交**。 

> [!Note]
> 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅[发布待处理的语音路由配置更改](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 

### <a name="create-or-modify-a-translation-rule-manually"></a>手动创建或修改转换规则

如果您想要定义转换规则，通过编写正则表达式的匹配模式和转换规则，请按照以下步骤。 

**手动定义转换规则**

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[委派安装权限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于业务控制面板的启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 要开始定义转换规则，请按照中的步骤[配置与媒体中继绕过](GET LINK AFTER MIGRATION)通过 10 个步骤或[配置无媒体中继绕过](GET LINK AFTER MIGRATION)前 9 个步骤。
4. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 字段中，键入描述要转换的号码模式的名称。
5. （可选）在**说明**框中，键入转换规则; 的说明例如，**美国国际长途拨号**。
6. 单击“构建转换规则”**** 部分底部的“编辑”****。
7. 在键入**正则表达式**输入以下内容：
    - 在“匹配此模式”**** 中，指定将用于匹配要转换的号码的模式。
    - 在“转换规则”**** 中，指定转换号码格式的模式。

    例如，如果输入**^ \+(\d{9}\d+)$** **匹配此模式**中和**011$ 1**中**转换规则**，该规则会将 + 441235551010 转换为 011441235551010。
8. 单击“确定”**** 保存转换规则。
9. 单击“确定”**** 保存中继配置。
10. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。 

> [!Note] 
> 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅[发布待处理的语音路由配置更改](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 
