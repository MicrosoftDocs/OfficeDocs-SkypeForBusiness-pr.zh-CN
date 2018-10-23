---
title: 修改现有的 PIN 策略
TOCTitle: 修改现有的 PIN 策略
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520993(v=OCS.15)
ms:contentKeyID: 49312838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 修改现有的 PIN 策略

 

_**上一次修改主题：** 2012-06-19_

可以使用“PIN 策略”选项卡为通过 IP 电话连接到 Lync 2013 的用户提供个人标识号 (PIN) 身份验证。要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”。有关详细信息，请参阅[修改现有的 Web 服务配置设置](lync-server-2013-modify-existing-web-service-configuration-settings.md)。

按照以下步骤修改用户级别或站点级别的 PIN 策略。

## 修改现有的 PIN 策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。

4.  在“PIN 策略”页上，单击某个策略，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 PIN 策略”的“最小 PIN 长度”中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。

6.  为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。

7.  如果选中了“指定最大登录尝试次数”复选框，请在“最大登录尝试数”中键入或选择希望允许的最大登录尝试次数。

8.  要使 PIN 过期，请选中“启用 PIN 有效期”复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。

9.  如果选中了“启用 PIN 有效期”复选框，请在“PIN 有效期(天)”中键入或选择 PIN 保持有效的天数。

10. 在“PIN 历史记录计数”中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。

11. 要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 我们建议您不要允许使用通用模式。


12. 单击“提交”。

