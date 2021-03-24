---
title: '在 Skype for Business Server 中管理电话拨入式会议访问号码 '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 摘要：了解如何在 Skype for Business Server 中管理电话拨入式会议访问号码。
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099148"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>在 Skype for Business Server 中管理电话拨入式会议访问号码
 
**摘要：** 了解如何在 Skype for Business Server 中管理电话拨入式会议访问号码。
  
部署电话拨入式会议时，需要设置用户可从公用电话交换网 (PSTN) 拨打的电话号码，以加入会议的音频部分。 这些拨入访问号码显示在会议邀请和"电话拨入式会议设置"网页中。 
  
本主题介绍如何查看、修改或删除现有的电话拨入式会议访问号码。 若要详细了解如何创建初始拨入访问号码，请参阅在 Skype [for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md)中配置电话拨入式会议。
  
## <a name="view-dial-in-conferencing-access-numbers"></a>查看电话拨入式会议访问号码

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看电话拨入式会议访问号码。
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板查看拨入访问号码

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。
    
4. 在“拨入访问号码”页上，单击要查看的访问号码。
    
5. 在 **"编辑**"中， **选中"显示详细信息** "复选框。
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序查看拨入访问号码

若要查看有关拨入访问号码的信息，请使用 **Get-CsDialInConferencingAccessNumber** cmdlet。
  
以下命令返回配置为在组织使用的所有电话拨入式会议访问号码的集合： 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

以下是返回的信息类型的示例：
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

有关详细信息，请参阅 [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>修改电话拨入式会议访问号码

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序修改拨入访问号码。
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板修改拨入访问号码

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。
    
4. 在"**拨入访问号码**"页上，单击列表中的某个拨入访问号码，再单击"编辑"，然后单击"显示 **详细信息"。**
    
    > [!NOTE]
    > 使用搜索字段搜索拨入访问号码列表中列的内容可能不会获得预期的结果。 相反，按关注列对列表进行排序，以标识要查看或更改的拨入访问号码。 
  
5. 在 **"显示** 号码"中，键入公用电话交换网 (PSTN) 电话用户为加入会议而拨打的电话号码。 
    
    此号码显示在会议邀请和电话拨入式会议设置网页中。
    
6. 在 **"显示** 名称"中，键入拨入访问号码的说明。 这是与 Skype for Business 搜索结果中的拨入访问号码相关联的名称。
    
    当用户呼叫访问号码时，此名称将显示在客户端中。 
    
7. 在 **"线路 URI"** 中，以 TEL URI 格式键入拨入访问号码的 E.164 号码，包括号码前的 + 符号和不包括空格。 例如，tel：+14255550200。
    
    > [!NOTE]
    > 同一线路 URI 不能由另一个电话拨入式会议访问号码重复使用。 
  
8. 在 **SIP URI** 中，执行以下操作：
    
   在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。 此 SIP URI 显示在各种位置，包括但不限于呼叫通知消息和早期版本的 Lync 客户端。
    
    > [!NOTE]
    > 同一 SIP URI 不能由另一个电话拨入式会议访问号码重复使用。 创建访问号码后，不能修改 SIP URI。 更改 SIP URI 的唯一方法就是删除并重新创建访问号码。 
  
   在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序的域。
    
9. 在 **"** 池"中，单击运行支持此拨入访问号码的会议助理实例的池。
    
    > [!NOTE]
    > 如果在创建访问号码后需要更改池，则必须使用 **Move-CsApplicationEndpoint** cmdlet 或删除并重新创建访问号码。
  
10. 在 **"主要** 语言"中，单击为此拨入访问号码播放提示的语言。 
    
    主要语言是会议助理用于应答呼叫的语言。 支持的语言显示在"电话拨入式会议设置"网页上的每个访问电话号码旁边。
    
11.  (可选) 在辅助语言 (最多四) 中，单击"添加 **"，** 选择要为此拨入访问号码的呼叫者支持的一种或多种语言，然后单击"确定 **"。** 
    
    对于每个拨入访问号码，你最多可以选择四种辅助语言。 用户在拨入会议时，可以在输入会议 ID 之前选择辅助语言。
    
12. 若要为拨入访问号码添加区域，请在"关联区域"下，单击"添加"，单击与此拨入访问号码的拨号计划关联的一个或多个区域，然后单击"确定 **"。**
    
13. 若要从拨入访问号码中删除某个区域，请在"关联区域"下，单击要删除的区域，然后单击"删除 **"。**
    
14. 单击“提交”。
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序修改拨入访问号码

要修改拨入访问号码，请使用 **Set-CsDialInConferencingAccessNumber** cmdlet。
  
以下命令修改 Identity 为 sip:RedmondDialIn@litwareinc.com 电话拨入式会议访问号码的 DisplayName sip:RedmondDialIn@litwareinc.com。 本示例中，显示名称设置为"Redmond 拨入访问号码"：
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

下一个示例将 Identity 为 sip:RedmondDialIn@litwareinc.com 电话拨入式会议访问号码修改为包括两个区域：Redmond 和 Seattle。 为执行此操作，命令调用了 Regions 参数，后跟这两个地区（以逗号分隔的两个字符串值）。 注意，除非已在拨号计划中定义了 Redmond 和 Seattle 这两个地区，否则此命令将失败。
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

有关详细信息，请参阅 [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>删除电话拨入式会议访问号码

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除电话拨入式会议访问号码。
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板删除电话拨入式会议访问号码

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。
    
4. 在页面上，单击列表中要删除的电话拨入式号码，再单击“编辑”，然后单击“删除”。
    
5. 单击“确定”。
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除电话拨入式会议访问号码

若要删除电话拨入式会议访问号码，请使用 **Remove-CsDialInConferencingAccessNumber**。
  
以下命令删除 Identity 为 sip:RedmondDialInAccess@litwareinc.com：
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

下一个命令删除与 Northwest 区域关联的所有电话拨入式会议访问号码：
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

下一个命令删除意大利语是主要语言的所有电话拨入式会议访问号码：
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

有关详细信息，请参阅 [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。
