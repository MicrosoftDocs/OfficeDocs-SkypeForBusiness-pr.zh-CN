---
title: 在 Skype for Business 服务器中分配每用户 PIN 策略
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
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：暂存 Skype for business 服务器的 AV 和 OAuth 证书。
ms.openlocfilehash: b7c353090f9eef3d2d2fbd0e6f8884121458f2f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818864"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>在 Skype for Business 服务器中分配每用户 PIN 策略

**摘要：** 暂存 Skype for business 服务器的 AV 和 OAuth 证书。
  
电话拨入式会议个人识别号（PIN）策略是可在 Skype for Business Server 控制面板中配置的用户帐户的个人设置之一。
  
部署一个或多个每用户 PIN 策略是可选的。还可以只部署一个全局级别的 PIN 策略或站点级别的 PIN 策略。如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。未分配特定的站点级别或每用户策略时，用户在电话拨入式会议中使用 PIN 的权限将自动默认为全局级别的 PIN 策略中定义的用户权限。
  
创建至少一个每用户 PIN 策略之后，请使用本主题中的过程分配策略，该策略指定您希望服务器对特定用户创建和使用的 PIN 施加的约束。
  
### <a name="to-assign-a-per-user-pin-policy"></a>分配每用户 PIN 策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
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
  
   e.i. 单击“查找”****。
    
6. 在搜索结果中单击某个用户，再单击“操作”****，然后单击“分配策略”****。
    
    > [!TIP]
    > 如果您希望将相同的每用户 PIN 策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”****，然后单击“分配策略”****。 
  
7. 在“分配策略”**** 中的“PIN 策略”**** 下，执行下列操作之一：
    
    > [!NOTE]
    > 由于有多个策略可以使用 "**分配策略**" 对话框进行配置，因此默认情况下为对话框中的每个策略选中 " ** \<保持\> **原样"。 如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。
  
   - 允许 Skype for business 服务器自动选择全局级别策略或网站级策略（如果已定义）。
    
   - 单击之前在“PIN 策略”**** 页中定义的每用户 PIN 策略的名称。
    
     > [!TIP]
     > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”**** 以查看策略中定义的用户权限。
  
8. 完成后，单击“确定”****。
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户 PIN 策略

你可以使用 Windows PowerShell 和**CsPinPolicy** cmdlet 分配每用户 PIN 策略。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中，此过程是相同的。
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>为单个用户分配每用户 PIN 策略

- 以下命令为用户 Ken Myer 分配每用户 PIN 策略 RedmondPinPolicy。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>为多个用户分配每用户 PIN 策略

- 以下命令为工作于 Redmond 市的所有用户分配每用户 PIN 策略 RedmondUsersPinPolicy。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>取消分配每用户 PIN 策略

- 以下命令取消分配之前分配给 Ken Myer 的任何每用户 PIN 策略。取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。站点策略优先于全局策略。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

有关详细信息，请参阅[授权-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中创建新的 PIN 策略](create-a-new-pin-policy.md)
