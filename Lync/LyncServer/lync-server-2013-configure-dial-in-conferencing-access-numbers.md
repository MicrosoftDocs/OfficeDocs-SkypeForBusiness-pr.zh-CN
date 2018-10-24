---
title: Lync Server 2013：配置电话拨入式会议访问号码
TOCTitle: 配置电话拨入式会议访问号码
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398952(v=OCS.15)
ms:contentKeyID: 49314429
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置电话拨入式会议访问号码

 

_**上一次修改主题：** 2011-07-17_

部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打以加入会议的音频部分的电话号码。这些拨入访问号码显示在会议邀请和“电话拨入式会议设置”网页上。

创建拨入访问号码前，必须首先规划电话拨入式会议区域，然后配置区域的拨号计划。有关区域的详细信息，请参阅规划文档中的 [电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)。有关为电话拨入式会议配置拨号计划的详细信息，请参阅 [在 Lync Server 2013 中配置电话拨入式会议的拨号计划](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)。

> [!NOTE]  
> 在 Active Directory 域服务 (AD DS) 完成对一个新拨入访问号码的复制前，无法使用该拨入访问号码。复制可能需要几个小时才能完成。



> [!NOTE]  
> 创建拨入访问号码后，可以修改 Active Directory 联系人对象的显示名称，以便用户可以更加轻松地识别正确的访问号码。可使用 <strong>Set-CsDialInConferencingAccessNumber</strong> cmdlet 修改显示名称。不应手动修改 Active Directory 对象。有关修改访问号码的详细信息，请参阅 Lync Server 命令行管理程序文档，了解 <strong>Set-CsDialInConferencingAccessNumber</strong> cmdlet 的相关内容。



## 本部分内容

[在 Lync Server 2013 中创建或修改电话拨入式会议访问号码](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

## 另请参阅

#### 概念

[电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)  

#### 其他资源

[在 Lync Server 2013 中配置电话拨入式会议的拨号计划](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

