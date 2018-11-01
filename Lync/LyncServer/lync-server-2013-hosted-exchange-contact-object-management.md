---
title: Lync Server 2013：托管 Exchange 联系人对象管理
TOCTitle: 托管 Exchange 联系人对象管理
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412978(v=OCS.15)
ms:contentKeyID: 49314672
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的托管 Exchange 联系人对象管理

 

_**上一次修改主题：** 2012-09-25_

您需要为交叉部署中的每个自动助理号码和订阅者访问号码配置联系人对象。

为了与托管 Exchange UM 集成，ocsumutil.exe 不能用于管理联系人对象，因为它取决于 Active Directory Exchange UM 设置。在交叉部署中， Lync Server 2013 和托管 Exchange UM 安装在单独的林中，彼此之间不存在信任关系。由于安全原因， Lync Server 2013 管理员无法直接访问 Exchange UM Active Directory 设置。因此， Lync Server 2013 还提供了另外一个模型，用于管理 Lync Server 2013 和托管 Exchange UM 服务可访问的 *共享 SIP 地址空间* 中的联系人对象。

## 托管的联系人对象工作流

以下是托管的 Exchange 租户管理员用于管理联系人对象的常规步骤：

1.  Exchange 管理员为 Exchange UM 订阅者访问和自动助理联系人对象请求电话号码。

2.  Lync Server 2013 管理员为每个电话号码创建一个联系人对象，并将托管的语音邮件策略分配给每个联系人对象。

3.  Lync Server 2013 管理员向 Exchange 管理员提供电话号码。

4.  Exchange 管理员将电话号码分配给自动助理和订阅者访问的相应 Exchange UM 拨号计划。

> [!NOTE]  
> 由于存在内部部署，因此不需要在联系人对象上配置任何 Lync Server 2013 拨号计划设置。



## 配置托管的联系人对象

> [!NOTE]  
> 必须先部署应用于 Lync Server 2013 联系人对象的托管语音邮件策略，然后才能为这些联系人对象启用托管 Exchange UM。策略可以是全局策略、站点级别策略或每用户策略，只要策略适用于要启用的联系人对象。有关详细信息，请参阅 <a href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</a>。



要在交叉部署中配置托管的自动助理和订阅者访问联系人对象，必须使用以下 cmdlet：

  - **New-CsExUmContact** 为托管的 UM 创建新的联系人对象。

  - **Set-CsExUmContact** 为托管 Exchange UM 修改现有的联系人对象。

以下示例创建一个自动助理联系人对象：

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

此示例创建一个 SIP 地址为 sip:exumaa1@fabrikam.com 的新 Exchange UM 联系人对象。运行 Lync Server 2013 Registrar 服务的池名称为 RedmondPool.litwareinc.com。将用于存储此信息的 Active Directory 组织单位为 OU=ExUmContacts,DC=litwareinc,DC=com。联系人对象的电话号码为 2065554567。可选参数 -AutoAttendant $True 指定此对象为自动助理联系人对象。将 -AutoAttendant 参数设置为 False（默认值）可指定订阅者访问联系人对象。

有关 New-CsExUmContact 和 Set-CsExUmContact cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

