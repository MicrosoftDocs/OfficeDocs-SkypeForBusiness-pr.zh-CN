---
title: Create or modify a Call Park orbit range in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Create or modify a Call Park orbit range table in Skype for Business Server 企业语音.
ms.openlocfilehash: 8a283ee9fd63a9c034385821d397d54156da9ba9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581096"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Create or modify a Call Park orbit range in Skype for Business

Create or modify a Call Park orbit range table in Skype for Business Server 企业语音.

呼叫等待使用通道来接听呼叫。 用户必须先配置呼叫离开通道表，然后用户才能呼叫和取回呼叫。 您需要指定组织为 (保留的) 通道的分机号码范围，并指定哪个呼叫池处理每个范围，从而定义这些范围的路由。 定义通道范围时，目标是具有足够的通道，以便不会在短时间内重用任何一个通道，但又不能有太多通道，以致于不得不限制用户或其他服务可使用的分机数量。 您可以为部署了呼叫Skype for Business Server的每个呼叫池创建多个呼叫等待通道范围。 每个呼叫 Park 通道范围必须具有一个全局唯一的名称和一组唯一的分机。

> [!IMPORTANT]
> 每个通道范围包含的通道数通常不超过 100。范围可以更大一点，只要每个范围的通道数小于最大值 10,000 且每个池的通道数小于 50,000。如果范围太小，很快就会重用通道。

请使用虚拟分机（未向其分配用户或电话的分机）块作为通道范围。

> [!NOTE]
> 不支持将外线直拨 (DID) 作为呼叫轨道表中的通道号码进行分配。

使用下列过程之一可创建或修改呼叫寄存通道范围。

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用Skype for Business Server控制面板创建或修改用于呼叫等待的号码范围

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅 **Delegate Setup Permissions**。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左侧导航栏中，单击“语音功能”，然后单击“呼叫寄存”。

4. 在“呼叫寄存”页上，执行下列操作之一：

   - 若要创建新的通道范围，请单击“新建”。在“名称”中，键入此号码范围的标识名称。

     > [!NOTE]
     > 在将通道范围提交到数据库后，将无法更改该名称。

   - 若要修改现有通道范围，请在搜索字段中键入通道范围的全部或部分名称。在通道的结果列表中，单击所需的通道，再单击“编辑”，然后单击“显示详细信息”。

5. 在第一个“号码范围”字段中，键入此呼叫寄存通道的分机范围中的起始号码，在第二个“号码范围”字段中，键入该范围的结束号码。 请注意：

   - 该范围的起始号码必须小于或等于该范围的结束号码。

   - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

   - 通道范围必须是唯一的。该范围不能与其他任何范围重叠。

   - 如果通道范围以 字符或 #开头，则范围 \* 必须大于 100。

   - 有效值：必须与正则表达式字符串匹配 ([ \\ *|#]？[1-9]\d {0,7}) | ([1-9]\d {0,8}) 。 这意味着该值必须是以字符或 # 或数字 1 到 9 开头的字符串 (第一个字符不能为 \* 零) 。 如果第一个字符是 或 #，则下面的字符必须是 1 到 \* 9 (不能是零) 。 后续字符可以是 0 到 9 之间的任意数字，最多包含七个其他字符 (例如 \* ，"#6000"、"92000"、"95551212"和 \* "915551212") 。 如果第一个字符不是 或 #，则第一个字符必须是数字 1 到 9 (不能为零) 后跟最多八个字符，每个字符从 0 到 9 (例如 \* ，"915551212"、"41212"、"300") 。

   - 每个池不应包含 50,000 个以上的通道。每个通道范围包含的通道数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。

6. 在 **“目标服务器的 FQDN”** 中，单击托管呼叫寄存应用程序的应用程序服务的完全限定域名 (FQDN) 或服务 ID。寄存在由通道范围中的起始号码和结束号码指定的范围内的号码的所有呼叫都将路由到此服务器或池。

7. 单击 **“提交”**。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用 Skype for Business Server命令行管理程序创建或修改用于呼叫等待的号码范围

1. 以 RTCUniversalServerAdmins 组的成员或所需的用户权限（如D delegate **Setup Permissions** 中所述）登录到安装了命令行管理程序Skype for Business Server的计算机。

2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

3. 使用 **New-CsCallParkOrbit** 可创建通道号码的新范围。使用 **Set-CsCallParkOrbit** 可修改通道号码的现有范围。

    在命令行中运行：

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    例如：

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    以下示例说明如何修改现有通道范围中的号码。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>另请参阅

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[删除呼叫寄存通道范围](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)