---
title: 在 Skype for Business Server 2015 中锁定或解锁用户 PIN
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要： 锁定或解锁的 Skype 的用户拨入会议针，对于业务服务器 2015年。
ms.openlocfilehash: 5bd4a334f9c0b543d9b4cade8631f992a920dfb1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中锁定或解锁用户 PIN
 
**摘要：**锁定或解锁的 Skype 的用户拨入会议针，对于业务服务器 2015年。
  
您可以锁定或解锁业务服务器控制面板的**用户**部分的 Skype 用户的 PIN。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype 用户的 PIN 锁定的业务服务器的控制面板

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 使用下列方法之一查找用户：
    
    - 在“搜索用户”****框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
    - 如果具有保存的查询，请单击“打开查询”****图标，使用“打开”****对话框来检索该查询（.usf 文件），然后单击“查找”****。
    
5. （可选）指定附加搜索条件以缩小结果的范围：
    
   a. 单击“添加筛选器”****。
    
   b. 通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
   c. 在“等于”****下拉列表中，单击运算符（例如“等于”****或“不等于”****）。
    
   d. 根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
    
    > [!TIP]
    > 要向查询中添加附加搜索子句，请单击“添加筛选器”****。 
  
   电子。 单击“查找”****。
    
   f。 单击用户，再单击“操作”****，然后单击“锁定 PIN”****。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>解锁用户的 PIN，在 Skype 业务服务器的控制面板

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
3. 在左导航栏中，单击“用户”****。
    
4. 使用下列方法之一查找用户：
    
   - 在“搜索用户”****框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
   - 如果具有保存的查询，请单击“打开查询”****图标，使用“打开”****对话框来检索该查询（.usf 文件），然后单击“查找”****。
    
5. （可选）指定附加搜索条件以缩小结果的范围：
    
   a. 单击“添加筛选器”****。
    
   b. 通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
   c. 在“等于”****下拉列表中，单击运算符（例如“等于”****或“不等于”****）。
    
   d. 根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
    
    > [!TIP]
    > 要向查询中添加附加搜索子句，请单击“添加筛选器”****。 
  
   电子。 单击“查找”****。
    
   f。 单击用户，再单击“操作”****，然后单击“解锁 PIN”****。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell Cmdlet 的锁定和解锁用户针脚

可以锁定和解锁用户针使用 Windows PowerShell 和锁 CsClientPin 和解锁 CsClientPin cmdlet。 可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行这些 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-lock-a-user-pin"></a>锁定用户 PIN

- 若要锁定用户的 PIN，请使用锁定 CsClientPin cmdlet。 例如：
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>解锁用户 PIN

- 若要解除锁定用户的 PIN，请使用解锁 CsClientPin cmdlet。 例如：
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

有关详细信息，请参阅有关[锁定 CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)和[解锁 CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlet 的帮助主题。