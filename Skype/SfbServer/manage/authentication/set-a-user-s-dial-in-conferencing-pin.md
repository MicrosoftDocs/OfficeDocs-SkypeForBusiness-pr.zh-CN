---
title: 在 Skype for Business Server 中设置用户的电话拨入式会议 PIN
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 摘要：为 Skype for Business Server 设置用户的电话拨入式会议 PIN。
ms.openlocfilehash: cd7375519fa9fc161c6414dcf1b9d0fbf6de6ef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828293"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>在 Skype for Business Server 中设置用户的电话拨入式会议 PIN
 
**摘要：** 为 Skype for Business Server 设置用户的电话拨入式会议 PIN。
  
要以经过身份验证的用户身份加入电话拨入式会议，具有 Active Directory 域服务 (AD DS) 凭据的 Skype for Business Server 用户需要个人标识号 (PIN) 。 如果用户忘记了电话拨入式会议 PIN 或者没有使用 Skype for Business Server 设置 PIN，可以从 Skype for Business Server 控制面板设置用户的 PIN。 可以自动生成 PIN，或手动创建 PIN。
  
> [!NOTE]
> 可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。 除了全局策略，您还可以为各个站点或用户配置 PIN 策略。 
  
### <a name="to-set-a-users-pin"></a>设置用户的 PIN

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
  
6. 在搜索结果中单击某个用户，再单击“操作”，然后单击“设置 PIN”。
    
7. 在“设置 PIN”对话框中，执行下列操作之一：
    
   - 若要允许 Skype for Business Server 生成用户的 PIN，请选择"自动生成有效的 **PIN** (默认) 。
    
   - 要创建您自己的 PIN，请单击“手动输入特定 PIN”，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。
    
8. 单击“确定”。
    
9. 在“设置 PIN”中，执行下列操作之一： 
    
   - 选中“显示 PIN”复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。
    
   - 单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”复选框以查看 PIN，然后将其复制到电子邮件。
    
10. 单击“关闭”。
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 分配Windows PowerShell PIN

您还可以使用 Set-CsClientPin cmdlet 分配 PIN 号码。 可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。 有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中相同。 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>自动为用户分配 PIN 号码

以下命令可将 PIN 号码分配给用户 Ken Myer。 由于不包括 Pin 参数，因此 Skype for Business Server 将自动生成和分配 PIN 号。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>将特定 PIN 号码分配给用户

此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

有关详细信息，请参阅 [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet 的帮助主题。
  

