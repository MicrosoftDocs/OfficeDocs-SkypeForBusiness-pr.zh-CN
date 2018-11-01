---
title: 在 Lync Server 2013 中配置电话拨入式会议个人标识号 (PIN) 规则
TOCTitle: 在 Lync Server 2013 中配置电话拨入式会议个人标识号 (PIN) 规则
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520967(v=OCS.15)
ms:contentKeyID: 49312305
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置电话拨入式会议个人标识号 (PIN) 规则

 

_**上一次修改主题：** 2012-06-19_

组织中具有 Active Directory 域服务 (AD DS) 凭据的 Lync Server 2013 用户可以通过使用个人标识号 (PIN) 以经过身份验证用户的身份加入电话拨入式会议。PIN 策略定义电话拨入式会议 PIN 工作方式的规则。

如果要将特定策略应用于某个站点或某个用户组，可以创建新的 PIN 策略。如果要在整个组织中使用相同的 PIN 策略，则可以使用全局 PIN 策略并根据需要对其进行修改。PIN 策略既可以应用于少数用户，也可以应用于众多用户。如果为用户分配用户级别的 PIN 策略，则优先应用这些设置。如果没有分配用户策略，则将应用站点级别的 PIN 策略（如果存在）。如果未应用用户策略或站点策略，则全局 PIN 策略会提供默认设置。

## 本部分内容

  - [在 Lync Server 2013 中修改默认电话拨入式会议 PIN 设置](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [在 Lync Server 2013 中创建或修改站点或用户组的电话拨入式会议 PIN 设置](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [删除站点或用户组的电话拨入式会议 PIN 设置](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

