---
title: 锁定或解锁用户 PIN Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要：锁定或解锁用户的电话拨入式会议 PIN Skype for Business Server。
ms.openlocfilehash: ccd575182bbac85b20879eaec8bb3e7a951fda1e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762510"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>锁定或解锁用户 PIN Skype for Business Server
 
**摘要：** 锁定或解锁用户的电话拨入式会议 PIN Skype for Business Server。
  
你可以从控制面板的"用户"部分锁定或解锁Skype for Business Server  PIN。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>在控制面板中锁定Skype for Business Server PIN

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
    
   f. 单击用户，再单击“操作”，然后单击“锁定 PIN”。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>在控制面板中解锁Skype for Business Server PIN

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
    
   f. 单击用户，再单击“操作”，然后单击“解锁 PIN”。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 锁定和解锁Windows PowerShell PIN

可以使用 Windows PowerShell cmdlet 和 Lock-CsClientPin cmdlet 锁定和解锁Unlock-CsClientPin PIN。 可以从命令行管理程序或 Skype for Business Server远程会话中运行这些 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft [Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 此过程在Skype for Business Server。
  
### <a name="to-lock-a-user-pin"></a>锁定用户 PIN

- 若要锁定用户的 PIN，请使用 Lock-CsClientPin cmdlet。 例如：
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>解锁用户 PIN

- 若要解锁用户的 PIN，请使用 Unlock-CsClientPin cmdlet。 例如：
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

有关详细信息，请参阅 [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) 和 [Unlock-CsClientPin](/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet 的帮助主题。