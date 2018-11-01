---
title: Lync Server 2013：为托管 Exchange UM 创建联系人对象
TOCTitle: 为托管 Exchange UM 创建联系人对象
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412765(v=OCS.15)
ms:contentKeyID: 49313817
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象

 

_**上一次修改主题：** 2012-09-24_

以下过程介绍如何为托管 Exchange 统一消息 (UM) 创建自动助理 (AA) 或订阅者访问 (SA) 联系人对象。

有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的托管 Exchange 联系人对象管理](lync-server-2013-hosted-exchange-contact-object-management.md)。

有关配置联系人对象的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)

> [!IMPORTANT]
> 必须先部署应用于 Lync Server 2013 联系人对象的托管语音邮件策略，然后才能为这些联系人对象启用托管 Exchange UM。有关详细信息，请参阅 <a href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</a>。


## 为托管 Exchange UM 创建 AA 或 SA 联系人对象

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsExUmContact cmdlet 创建部署所需的任何联系人对象。例如，运行以下命令创建 AA 和 SA 联系人对象：
    
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True

       &nbsp;
    
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
    
    这些示例设置了以下参数：
    
      - **SipAddress** 指定联系人对象的 SIP 地址。该地址必须是尚未在 Active Directory 域服务中用于配置用户或联系人对象的地址。该值必须使用“sip:\<*SIP 地址*\>”格式，如上面的示例中所示。
    
      - **RegistrarPool** 指定运行 Registrar 服务的池的完全限定域名 (FQDN)。
        
        > [!NOTE]  
		> 不能将 Exchange UM 联系人对象移动到 Lync Server 2013 之前的 Lync Server 2013 部署所包含的池中。
        
    
      - **OU** 指定此联系人对象将位于的 Active Directory 组织单位。
    
      - **DisplayNumber** 指定联系人对象的电话号码。每个联系人对象的电话号码必须是唯一的。
    
      - **AutoAttendant** 指定联系人对象是否为自动助理。自动助理提供了一组语音提示，允许呼叫者导航电话系统并最终到达他们要联系的一方。为此参数指定 **False** 值（默认值）指示对象为订阅者访问联系人对象。

