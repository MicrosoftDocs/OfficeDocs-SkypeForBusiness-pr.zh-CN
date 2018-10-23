---
title: Lync Server 2013：配置语音策略、PSTN 用法记录和语音路由
TOCTitle: 配置语音策略、PSTN 用法记录和语音路由
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398272(v=OCS.15)
ms:contentKeyID: 49312199
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由

 

_**上一次修改主题：** 2012-10-10_

语音策略、PSTN 用法记录和语音路由是一个有机整体。可以通过选择一组呼叫功能，然后为策略分配一组 PSTN 用法记录来配置语音策略，这些记录指定为分配了语音策略的用户或组授予哪些权限。系统还向语音路由分配 PSTN 用法记录，这些记录用于将路由与有权使用它们的用户进行匹配。也就是说，用户只能发出使用用户对于其有匹配的 PSTN 用法记录的路由的呼叫。

通过配置包含相应的 PSTN 用法记录的语音策略来启动新企业语音部署的建议工作流，然后将相应的路由关联到每个 PSTN 用法记录。

> [!NOTE]  
> 您还可以创建具有<em>用户</em>作用域的语音策略，并将其分配到各个用户或组。



有关执行上述各项任务的详细步骤，请参阅本节中的过程。

## 本部分内容

  - [在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [在 Lync Server 2013 中查看 PSTN 用法记录](lync-server-2013-view-pstn-usage-records.md)

  - [在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [在 Lync Server 2013 中导出和导入语音路由配置](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)

