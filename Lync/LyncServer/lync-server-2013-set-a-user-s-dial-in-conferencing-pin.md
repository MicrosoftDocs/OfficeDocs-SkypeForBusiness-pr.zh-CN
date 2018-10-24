---
title: Lync Server 2013：设置用户的电话拨入式会议 PIN
TOCTitle: 设置用户的电话拨入式会议 PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520985(v=OCS.15)
ms:contentKeyID: 49312666
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置用户的电话拨入式会议 PIN

 

_**上一次修改主题：** 2014-06-10_

要以经过身份验证的用户身份加入电话拨入式会议，具有 Active Directory 域服务 (AD DS) 凭据的 Lync Server 2013 用户需要个人标识号 (PIN)。如果用户忘记了电话拨入式会议的 PIN 或尚未通过 Lync Server 设置 PIN，则可以在 Lync Server 控制面板中设置用户的 PIN。可以自动生成 PIN，或手动创建 PIN。

> [!NOTE]  
> 可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。除了全局策略，您还可以为各个站点或用户配置 PIN 策略。有关配置 PIN 策略的详细信息，请参阅 <a href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">在 Lync Server 2013 中配置电话拨入式会议个人标识号 (PIN) 规则</a>。



## 设置用户的 PIN

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”。

4.  使用下列方法之一查找用户：
    
      - 在“搜索用户”框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
      - 如果具有保存的查询，请单击“打开查询”图标，使用“打开”对话框来检索该查询（.usf 文件），然后单击“查找”。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
    3.  在“等于”下拉列表中，单击运算符（例如“等于”或“不等于”）。
    
    4.  根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
        
        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”。
    
    5.  单击“查找”。
    
    > [!NOTE]  
	> 如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”，然后单击“解锁 PIN”。
    


6.  在搜索结果中单击某个用户，再单击“操作”，然后单击“设置 PIN”。

7.  在“设置 PIN”对话框中，执行下列操作之一：
    
      - 要允许 Lync Server 2013 生成用户的 PIN，请选择“自动生成有效 PIN”（默认值）。
    
      - 要创建您自己的 PIN，请单击“手动输入特定 PIN”，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。

8.  单击“确定”。

9.  在“设置 PIN”中，执行下列操作之一：
    
      - 选中“显示 PIN”复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。
    
      - 单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”复选框以查看 PIN，然后将其复制到电子邮件。

10. 单击“关闭”。

## 使用 Windows PowerShell cmdlet 分配用户 PIN

还可以使用 Set-CsClientPin cmdlet 分配 PIN 号码。您可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 自动为用户分配 PIN 号码

  - 以下命令可将 PIN 号码分配给用户 Ken Myer。由于未包括 Pin 参数，因此 Lync Server 将自动生成并分配 PIN 号码。
    
        Set-CsClientPin -Identity "Ken Myer" 

## 为用户分配特定 PIN 号码

  - 此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

有关详细信息，请参阅 [Set-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPin) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[拨入访问号码](https://technet.microsoft.com/zh-cn/library/gg133674\(v=ocs.15\))  

#### 其他资源

[在 Lync Server 2013 中配置电话拨入式会议个人标识号 (PIN) 规则](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)

