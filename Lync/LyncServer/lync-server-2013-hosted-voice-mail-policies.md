---
title: Lync Server 2013：托管语音邮件策略
TOCTitle: 托管语音邮件策略
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398932(v=OCS.15)
ms:contentKeyID: 49314382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的托管语音邮件策略

 

_**上一次修改主题：** 2012-10-01_

*托管语音邮件策略* 向 Lync Server 2013 ExUM 路由应用程序提供有关可在哪里为邮箱位于托管 Exchange 服务的用户路由呼叫的信息。

> [!NOTE]  
> 仅当 Lync Server 2013 与托管 Exchange UM 集成时才需要托管语音邮件策略。对于与内部 Exchange UM 的集成，则不需要这些策略。



## 托管语音邮件策略作用域

托管语音邮件策略作用域确定应用策略的层次级别。可以为托管语音邮件策略配置以下作用域级别：

  - *全局* 策略可能会影响 Lync Server 2013 部署中的所有用户。如果已为用户启用托管 Exchange UM 访问且未向用户分配每用户策略，并且如果未将站点策略分配给该用户的站点，则将应用全局策略。全局策略是随 Lync Server 2013 一起安装的。可以根据需要修改该策略，但不能重命名或删除它。

  - *站点* 策略会影响驻留在为其定义策略的站点上的所有用户。如果已为用户配置托管 Exchange UM 访问且未向用户分配每用户策略，则将应用站点策略。

  - *每用户* 策略只会影响各个用户或组。要强制实施每用户策略，必须将其显式分配给各个用户、组或联系人对象。

> [!NOTE]  
> 在大多数情况下，只需要一个托管语音邮件策略。可以经常修改全局策略以满足您的所有需要。如果部署多个托管语音邮件策略，则所有这些策略都具有每用户作用域。



## 托管语音邮件策略属性

语音邮件策略定义了两个属性， Lync Server 2013 ExUM 路由应用程序将这两个属性插入到发送至托管 Exchange UM 实现的 INVITE 消息的请求 URI 中：

  - **Destination ：** 托管 Exchange UM 服务的完全限定域名 (FQDN)。此值由内部 Lync Server 边缘服务器用于进行路由。
    
    > [!NOTE]  
    > Exchange Online 的 FQDN 为 exap.um.outlook.com。
    


  - **Organization ：** 托管 Lync Server 2013 用户的邮箱的托管 Exchange UM 服务上的租户 FQDN。语音邮件策略可以包含多个组织。如果策略中包含多个组织，则此属性必须是以逗号分隔的托管 Lync Server 2013 用户邮箱的 Exchange Server 租户列表。

> [!NOTE]  
> 托管 Exchange UM 服务的租户管理员将提供 Destination 和 Organization 属性设置的所需值。要配置策略，必须运行 New-CsHostedVoicemailPolicy cmdlet 或使用 Set-CsHostedVoicemailPolicy cmdlet 来修改一个存在的策略（例如，全局策略）。



有关管理托管语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

## 每用户语音邮件策略分配

如果托管语音邮件策略定义有每用户作用域，则必须显式分配该策略。可以运行 Grant-CsHostedVoicemailPolicy cmdlet 将该策略分配给各个用户或组。

有关分配或删除每用户托管语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

