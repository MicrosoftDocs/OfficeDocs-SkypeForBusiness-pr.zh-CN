---
title: 锁定或解锁用户 PIN Skype 中的业务服务器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要： 锁定或解锁的 Skype 业务服务器的用户的电话拨入式会议 PIN。
ms.openlocfilehash: 89e971ac8c935c7998c206ce365c8899e0617cc4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986321"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>锁定或解锁用户 PIN Skype 中的业务服务器
 
**摘要：** 锁定或解锁的 Skype 业务服务器的用户的电话拨入式会议 PIN。
  
可以锁定或解锁用户 PIN，从**用户**部分的 Skype 的业务 Server Control Panel。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>为业务 Server Control Panel Skype 中锁定用户 PIN

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 使用下列方法之一查找用户：
    
    - 在“搜索用户”**** 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
    - 如果具有保存的查询，请单击“打开查询”**** 图标，使用“打开”**** 对话框来检索该查询（.usf 文件），然后单击“查找”****。
    
5. （可选）指定附加搜索条件以缩小结果的范围：
    
   a. 单击“添加筛选器”****。
    
   b. 通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
   c. 在“等于”**** 下拉列表中，单击运算符（例如“等于”**** 或“不等于”****）。
    
   d. 根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
    
    > [!TIP]
    > 要向查询中添加附加搜索子句，请单击“添加筛选器”****。 
  
   e。 单击“查找”****。
    
   f。 单击用户，再单击“操作”****，然后单击“锁定 PIN”****。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype 中的用户的 PIN 解锁的业务 Server Control Panel

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 使用下列方法之一查找用户：
    
   - 在“搜索用户”**** 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
   - 如果具有保存的查询，请单击“打开查询”**** 图标，使用“打开”**** 对话框来检索该查询（.usf 文件），然后单击“查找”****。
    
5. （可选）指定附加搜索条件以缩小结果的范围：
    
   a. 单击“添加筛选器”****。
    
   b. 通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
   c. 在“等于”**** 下拉列表中，单击运算符（例如“等于”**** 或“不等于”****）。
    
   d. 根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
    
    > [!TIP]
    > 要向查询中添加附加搜索子句，请单击“添加筛选器”****。 
  
   e。 单击“查找”****。
    
   f。 单击用户，再单击“操作”****，然后单击“解锁 PIN”****。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 锁定和解锁用户 Pin

您可以锁定和解锁用户 Pin by using Windows PowerShell 和 Lock-csclientpin 和 Unlock-csclientpin cmdlet。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行这些 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-lock-a-user-pin"></a>锁定用户 PIN

- 若要锁定用户 PIN，请使用 Lock-csclientpin cmdlet。 例如：
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>解锁用户 PIN

- 若要解除锁定用户 PIN，请使用 Unlock-csclientpin cmdlet。 例如：
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

有关详细信息，请参阅[Lock-csclientpin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)和[Unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet 的帮助主题。