---
title: '管理 Skype for Business 服务器中的电话拨入式会议访问号码 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '摘要: 了解如何在 Skype for Business Server 中管理电话拨入式会议访问号码。'
ms.openlocfilehash: e41011c4ba06da7f05d8cb1a52717e707cd2f8bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289032"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的电话拨入式会议访问号码
 
**摘要:** 了解如何在 Skype for Business Server 中管理电话拨入式会议访问号码。
  
部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打以加入会议的音频部分的电话号码。 这些拨入访问号码显示在会议邀请和“电话拨入式会议设置”网页上。 
  
本主题描述如何查看、修改或删除现有的电话拨入式会议访问号码。 有关如何创建初始拨入访问号码的详细信息, 请参阅[在 Skype For Business 服务器中配置电话拨入式会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
## <a name="view-dial-in-conferencing-access-numbers"></a>查看拨入会议访问号码

您可以使用 Skype for Business 服务器控制面板或使用 Skype for business Server 命令行管理器查看电话拨入式会议访问号码。
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板查看拨入访问号码

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**拨入访问号码**”。
    
4. 在“**拨入访问号码**”页上，单击要查看的访问号码。
    
5. 在“**编辑**”中，选中“**显示详细信息**”复选框。
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序查看拨入访问号码

若要查看有关拨入访问号码的信息，请使用 **Get-CsDialInConferencingAccessNumber** cmdlet。
  
以下命令返回已配置为在组织中使用的所有电话拨入式会议访问号码的集合: 
  
```
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

有关详细信息, 请参阅[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>修改电话拨入式会议访问号码

您可以使用 Skype for Business 服务器控制面板或使用 Skype for business Server 命令行管理器修改拨入访问号码。
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板修改拨入访问号码

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**拨入访问号码**”。
    
4. 在“**拨入访问号码**”页上，单击列表中的某个拨入访问号码，单击“**编辑**”，然后单击“**显示详细信息**”。
    
    > [!NOTE]
    > 使用搜索字段搜索拨入访问号码列表中某一列的内容时，可能得不到预期结果。此时，可以按照列的关注度对列表进行排序，以识别要查看或更改的拨入访问号码。 
  
5. 在“**显示号码**”中，键入相应的电话号码，以便公用电话交换网 (PSTN) 电话用户可拨打此号码加入会议。 
    
    该号码会显示在会议邀请和电话拨入式会议设置网页中。
    
6. 在“显示名称”**** 中，键入拨入访问号码的说明。 这是与 Skype for Business 搜索结果中的拨入访问号码相关联的名称。
    
    用户呼叫访问号码时，此名称会显示在客户端上。 
    
7. 在“线路 URI”**** 中，使用 TEL URI 格式键入拨入访问号码的 E.164 号码，请在此号码前添加 + 符号，不要添加空格。例如：tel:+14255550200。
    
    > [!NOTE]
    > 同一线路 URI 不能由其他电话拨入式会议访问号码重复使用。 
  
8. 在“SIP URI”**** 中，执行下列操作：
    
   在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。 SIP URI 显示在不同的位置, 其中包括但不限于呼叫通知消息和早期版本的 Lync 客户端。
    
    > [!NOTE]
    > 同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。创建访问号码之后，将不能修改 SIP URI。更改 SIP URI 的唯一方法是删除并重新创建访问号码。 
  
   在下拉列表框中, 单击支持此拨入访问号码的会议助理应用程序所在的域。
    
9. 在“池”**** 中，单击运行支持此拨入访问号码的会议助理实例的池。
    
    > [!NOTE]
    > 创建访问号码后，如果需要更改池，必须使用  **Move-CsApplicationEndpoint** cmdlet 或删除并重新创建访问号码。
  
10. 在“主要语言”**** 中，单击针对此拨入访问号码播放提示时使用的语言。 
    
    主要语言是会议助理应答呼叫时使用的语言。支持的语言显示在电话拨入式会议设置网页上的每个访问电话号码旁边。
    
11. （可选）在“辅助语言（最多 4 个）”**** 中，单击“添加”****，选择一个或多个要为此拨入访问号码的呼叫者提供支持的其他语言，然后单击“确定”****。 
    
    最多可以为每个拨入访问号码选择四种辅助语言。用户通过电话拨入加入会议时，在输入会议 ID 之前可以选择一种辅助语言。
    
12. 若要为拨入访问号码添加区域, 请在 "**关联区域**" 下, 单击 "**添加**", 单击与此拨入访问号码的拨号计划相关联的一个或多个区域, 然后单击 **"确定"**。
    
13. 要从拨入访问号码中删除某个区域，请在“关联区域”**** 下，单击要删除的区域，然后单击“删除”****。
    
14. 单击“**提交**”。
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序修改拨入访问号码

若要修改拨入访问号码，请使用 **Set-CsDialInConferencingAccessNumber** cmdlet。
  
下面的命令修改了 Identity 为 sip:RedmondDialIn@litwareinc.com 的电话拨入式会议接入号码的 DisplayName 属性。在此示例中，显示名称设置为"Redmond Dial-In Access Number"：
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

在下一个示例中，Identity 为 sip:RedmondDialIn@litwareinc.com 的电话拨入式会议接入号码经修改后包含以下两个地区：Redmond 和 Seattle。为执行此操作，命令调用了 Regions 参数，后跟这两个地区（以逗号分隔的两个字符串值）。注意，除非已在拨号计划中定义了 Redmond 和 Seattle 这两个地区，否则此命令将失败。
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

有关详细信息, 请参阅[设置 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>删除电话拨入式会议访问号码

您可以使用 Skype for Business 服务器控制面板或使用 Skype for business Server 命令行管理程序删除电话拨入式会议访问号码。
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板删除电话拨入式会议接入号码

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**拨入访问号码**”。
    
4. 在页面上，单击列表中要删除的电话拨入式号码，再单击“**编辑**”，然后单击“**删除**”。
    
5. 单击“**确定**”。
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除电话拨入式会议接入号码

若要删除电话拨入式会议访问号码，请使用 **Remove-CsDialInConferencingAccessNumber**。
  
下面的命令可删除标识为 sip:RedmondDialInAccess@litwareinc.com 的电话拨入式会议访问号码：
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

下一个命令可删除与西北区域关联的所有电话拨入式会议访问号码：
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

下一个命令可删除意大利语为主要语言的所有电话拨入式会议访问号码：
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

有关详细信息, 请参阅[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。
  

