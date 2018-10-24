---
title: 在 Lync Server 2013 中分配每用户承载的语音邮件策略
TOCTitle: 在 Lync Server 2013 中分配每用户承载的语音邮件策略
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398919(v=OCS.15)
ms:contentKeyID: 49314349
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中分配每用户承载的语音邮件策略

 

_**上一次修改主题：** 2010-11-07_

部署一个或多个每用户托管语音邮件策略是可选的。如果要部署每用户策略，则必须将其显式分配给用户、组或联系人对象。

有关分配或删除每用户托管语音邮件策略分配的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## 分配每用户托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 Grant-CsHostedVoicemailPolicy cmdlet 将每用户托管语音邮件策略分配给各个用户、组和联系人对象。例如，运行：
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    此示例将 ExRedmond 托管语音邮件策略分配给用户 Ken Myer。
    
    **Identity** 指定要修改的用户帐户。可以使用以下任意格式指定 Identity 值：
    
      - 用户的 SIP 地址
    
      - 用户的 Active Directory 用户主体名称
    
      - 用户的域\\登录名（例如，contoso\\kenmyer）
    
      - 用户的 Active Directory 域服务显示名称（例如，Ken Myer）。如果将显示名称用作 Identity 值，可以使用星号 (\*) 通配符。例如，Identity "\* Smith" 将返回显示名称以字符串值“Smith”结尾的所有用户。
    
    > [!NOTE]  
    > 用户的 Active Directory SAM 帐户名不能用作 Identity 值，因为 SAM 帐户名在林中不一定是唯一的。
    

