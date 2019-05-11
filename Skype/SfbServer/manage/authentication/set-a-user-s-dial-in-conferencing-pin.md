---
title: 为业务服务器 Skype 中设置用户的电话拨入式会议 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 摘要： 为业务服务器 Skype 设置用户的电话拨入式会议 PIN。
ms.openlocfilehash: 4dc60d10d063e367a7fd696d7625c6a5ad5540b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919358"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>为业务服务器 Skype 中设置用户的电话拨入式会议 PIN
 
**摘要：** 为业务服务器的 Skype 设置用户的电话拨入式会议 PIN。
  
若要加入电话拨入式会议作为经过身份验证的用户，具有 Active Directory 域服务 (AD DS) 凭据的企业服务器用户 Skype 需要的个人标识号 (PIN)。 如果用户忘记了电话拨入式会议 PIN 或通过使用 Business Server Skype 未设置 PIN，您可以为业务 Server Control Panel 从 Skype 设置用户的 PIN。 可以自动生成 PIN，或手动创建 PIN。
  
> [!NOTE]
> 可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。除了全局策略，您还可以为各个站点或用户配置 PIN 策略。 
  
### <a name="to-set-a-users-pin"></a>若要设置用户的 PIN

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
    
    > [!NOTE]
    > 如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”****，然后单击“解锁 PIN”****。 
  
6. 在搜索结果中单击某个用户，再单击“操作”****，然后单击“设置 PIN”****。
    
7. 在“设置 PIN”**** 对话框中，执行下列操作之一：
    
   - 若要允许 Skype 业务服务器生成用户的 PIN，请选中**自动生成有效 PIN** （默认）。
    
   - 要创建您自己的 PIN，请单击“手动输入特定 PIN”****，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。
    
8. 单击“**确定**”。
    
9. 在“设置 PIN”**** 中，执行下列操作之一： 
    
   - 选中“显示 PIN”**** 复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。
    
   - 单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”**** 以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”**** 复选框以查看 PIN，然后将其复制到电子邮件。
    
10. 单击“关闭”****。
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配用户 PIN

还可以使用 Set-CsClientPin cmdlet 分配 PIN 号码。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>自动为用户分配 PIN 号码

以下命令可将 PIN 号码分配给用户 Ken Myer。 Pin 参数不包含，因为 Skype 业务服务器将自动生成并分配 PIN 号码。
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>为用户分配特定 PIN 号码

此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

有关详细信息，请参阅[Set-csclientpin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet 的帮助主题。
  

