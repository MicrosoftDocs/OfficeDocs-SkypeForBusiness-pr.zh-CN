---
title: 在用户视图中查看用户 PIN Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：在用户视图中查看用户 PIN Skype for Business Server。
ms.openlocfilehash: a77dbc71a186ff20b0136b3391f5ce33dcda1134
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014186"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>在用户视图中查看用户 PIN Skype for Business Server
 
**摘要：** 在用户视图中查看Skype for Business Server。
  
若要以经过身份验证的用户身份加入电话拨入式会议，具有 Active Directory 域服务 (AD DS) 凭据的 Skype for Business Server 用户需要个人标识号 (PIN) 。 You can view a user's PIN information from Skype for Business Server Control Panel.
  
> [!NOTE]
> 您可以查看 PIN 状态信息（如是否已设置 PIN 或上次更改 PIN 的时间），但无法通过查看 PIN 状态来查看当前 PIN。 如果用户丢失了 PIN，可以按照"设置用户的电话拨入式会议[PIN"](set-a-user-s-dial-in-conferencing-pin.md)中的过程重置Skype for Business Server
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>在控制面板中查看Skype for Business Server PIN

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“用户”。
    
4. 使用下列方法之一查找用户：
    
   - 在“搜索用户”框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
   - 如果具有保存的查询，请单击“打开查询”图标，使用“打开”对话框来检索该查询（.usf 文件），然后单击“查找”。
    
5. （可选）指定附加搜索条件以缩小结果的范围：
    
   a. 单击“添加筛选器”。
    
   b. 通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
   c. 在“等于”下拉列表中，单击运算符（例如“等于”或“不等于”）。
    
   d. 根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
    
    > [!TIP]
    > 要向查询中添加附加搜索子句，请单击“添加筛选器”。 
  
   e. 单击“查找”。
    
    > [!NOTE]
    > 如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”，然后单击“解锁 PIN”。 
  
6. 在搜索结果中单击某个用户，再单击“操作”，然后单击“查看 PIN 状态”。
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看Windows PowerShell PIN 信息

您可以使用 Get-CsClientPinInfo cmdlet 查看用户 PIN 信息。 可以从命令行管理程序或 Skype for Business Server远程会话运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在Skype for Business Server。
  
### <a name="to-view-user-pin-information"></a>查看用户 PIN 信息

若要查看用户的 PIN 信息，请在命令行管理程序中键入与Skype for Business Server类似的命令，然后按 Enter：
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

这将返回与以下类似的信息：

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

有关详细信息，请参阅 [Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[设置用户电话拨入式会议 PIN Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[锁定或解锁用户 PIN Skype for Business Server](lock-or-unlock-a-user-pin.md)