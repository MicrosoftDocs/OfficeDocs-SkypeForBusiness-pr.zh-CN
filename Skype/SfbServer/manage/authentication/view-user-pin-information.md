---
title: 在 Skype for Business Server 中查看用户 PIN 信息
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
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：在 Skype for Business Server 中查看用户 PIN 信息。
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806502"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>在 Skype for Business Server 中查看用户 PIN 信息
 
**摘要：** 在 Skype for Business Server 中查看用户 PIN 信息。
  
要以经过身份验证的用户身份加入电话拨入式会议，具有 Active Directory 域服务 (AD DS) 凭据的 Skype for Business Server 用户需要个人标识号 (PIN) 。 可以从 Skype for Business Server 控制面板查看用户的 PIN 信息。
  
> [!NOTE]
> 您可以查看 PIN 状态信息（如是否已设置 PIN 或上次更改 PIN 的时间），但无法通过查看 PIN 状态来查看当前 PIN。 如果用户丢失了 PIN，可以按照"在 Skype for Business Server 中设置用户的电话拨入式会议 [PIN"中的过程重置 PIN](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>在 Skype for Business Server 控制面板中查看用户的 PIN

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。  
    
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

您可以使用 Get-CsClientPinInfo cmdlet 查看用户 PIN 信息。 此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。 有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中相同。
  
### <a name="to-view-user-pin-information"></a>查看用户 PIN 信息

若要查看用户的 PIN 信息，请在 Skype for Business Server 命令行管理程序 中键入类似如下的命令，然后按 Enter：
    
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

有关详细信息，请参阅 [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet 的帮助主题。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中设置用户的电话拨入式会议 PIN](set-a-user-s-dial-in-conferencing-pin.md)
  
[在 Skype for Business Server 中锁定或解锁用户 PIN](lock-or-unlock-a-user-pin.md)
