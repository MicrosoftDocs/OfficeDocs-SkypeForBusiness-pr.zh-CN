---
title: 设置用户电话拨入式会议 PIN Skype for Business Server
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 摘要：设置用户的电话拨入式会议 PIN Skype for Business Server。
ms.openlocfilehash: 0532a5972a373bd92d9fb72d0883d6c40542a91e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012316"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>设置用户电话拨入式会议 PIN Skype for Business Server
 
**摘要：** 设置用户的电话拨入式会议 PIN Skype for Business Server。
  
若要以经过身份验证的用户身份加入电话拨入式会议，具有 Active Directory 域服务 (AD DS) 凭据的 Skype for Business Server 用户需要个人标识号 (PIN) 。 如果用户忘记了电话拨入式会议 PIN 或尚未使用 Skype for Business Server 设置 PIN，可以从"控制面板"中Skype for Business Server PIN。 可以自动生成 PIN，或手动创建 PIN。
  
> [!NOTE]
> 可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。 除了全局策略，您还可以为各个站点或用户配置 PIN 策略。 
  
### <a name="to-set-a-users-pin"></a>设置用户的 PIN

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
  
6. 在搜索结果中单击某个用户，再单击“操作”，然后单击“设置 PIN”。
    
7. 在“设置 PIN”对话框中，执行下列操作之一：
    
   - 若要Skype for Business Server生成用户的 PIN，请选择"自动生成有效的 **PIN** (默认) "。
    
   - 要创建您自己的 PIN，请单击“手动输入特定 PIN”，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。
    
8. 单击“确定”。
    
9. 在“设置 PIN”中，执行下列操作之一： 
    
   - 选中“显示 PIN”复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。
    
   - 单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”复选框以查看 PIN，然后将其复制到电子邮件。
    
10. 单击“关闭”。
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 分配Windows PowerShell PIN

您还可以使用 cmdlet 分配 PIN Set-CsClientPin号码。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>向用户自动分配 PIN 号码

以下命令可将 PIN 号码分配给用户 Ken Myer。 由于不包括 Pin 参数，Skype for Business Server自动生成和分配 PIN 号码。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>向用户分配特定 PIN 号码

此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

有关详细信息，请参阅 [Set-CsClientPin](/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet 的帮助主题。
