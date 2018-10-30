---
title: Lync Server 2013 中的架构类和说明
TOCTitle: Lync Server 2013 中的架构类和说明
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398625(v=OCS.15)
ms:contentKeyID: 49313379
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的架构类和说明

 

_**上一次修改主题：** 2015-03-09_

本节介绍 Lync Server 2013 使用的所有架构类。

## 架构类和说明


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>类</th>
<th>说明</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Exchange 统一消息 (UM) 电子邮件收件人。</p></td>
<td><p>与 Exchange UM 共享此辅助类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>此类是多个应用程序联系人的容器，并且自身不包含任何属性。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>此类包含统一通信应用程序服务 (UCAS) 实例的服务控制点的相应项。</p></td>
<td><p>Office Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>此类提供从特定池到其应用程序服务的关联。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>这是 msRTCSIP-ApplicationServer 的辅助类，其中包含表示应用程序服务实例的设置的属性。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive（作废）</p></td>
<td><p>这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与存档相关的所有设置。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer（作废）</p></td>
<td><p>此类表示单个即时消息存档服务器。将计算机作为即时消息存档服务器（如安装了即时消息存档服务的计算机）激活时将创建此类的实例。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>此类是会议目录的多个实例的容器，并且自身不包含任何属性。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>此类包含表示特定会议目录的设置的属性。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>将计算机指定为运行 Lync Server 的服务器的通用服务控制点 (SCP)。</p></td>
<td><p>Lync 2010 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>此辅助类包含 Microsoft Lync Web App 组的设置。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>此类包含定义 SIP 注册器的已配置域的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>此类容器表示单个访问边缘服务。由于访问边缘服务部署在外围网络中，而客户通常不允许来自外围网络的 Active Directory 域服务 访问，因此访问边缘服务未加入到 Intranet 的 Active Directory 网络。这样，访问代理就不会在 AD DS 中自动注册。管理员必须手动配置 AD DS 中存在的每个访问边缘服务实例。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>这是 msRTCSIP-MCU 的辅助类，其中包含表示会议服务器的设置的属性。</p></td>
<td><p>Microsoft Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>这是 msRTCSIP-MediationServer 的辅助类，其中包含表示中介服务器的设置的属性。</p></td>
<td><p>Office Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>这是 msRTCSIP-Server 的辅助类，其中包含表示 SIP 服务器的设置的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与联盟相关的所有设置。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>此类包含应用于整个 Lync Server 部署的所有设置。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy（作废）</p></td>
<td><p>此类表示单个 Office Communications Server 会议策略。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>本地全局拓扑设置对象。</p></td>
<td><p>Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>包含全局拓扑设置对象的容器。</p></td>
<td><p>Lync Server 2010 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>此类是表示位置规范化规则的实例的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>此类由会议助理应用程序创建，并包含用于按区域将会议电话号码分类的属性。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>此类是位置联系人映射的多个实例的容器，并且自身不包含任何属性。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>此类是表示特定位置配置文件的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles（作废）</p></td>
<td><p>此类是多个位置配置文件的容器，并且自身不包含任何属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations（作废）</p></td>
<td><p>此类是多个本地规范化规则的容器，并且自身不包含任何属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>此类表示单个会议服务器。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>此类包含多个 msRTCSIP-MCUFactory 类，并且自身没有任何属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>此类是表示单个媒体类型的会议服务器中心的容器。当激活对应于此特定类型和供应商的第一台会议服务器时，将创建此类的实例。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>此类提供从特定池到其会议服务器中心的关联。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>此类包含中介服务器的服务控制点的相应项。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting（作废）</p></td>
<td><p>这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示可配置会议设置的属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>存储全局移动性设置的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>此类包含表示单个监控服务器的设置的属性。</p></td>
<td><p>Communications Server 2007 R2 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute（作废）</p></td>
<td><p>此类是表示到一个网关或一组网关的最低成本路由的实例的容器。所有企业版池或运行 Standard Edition 的服务器使用此信息，以最经济有效的方式将传出呼叫路由至公用电话交换网 (PSTN)。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes（作废）</p></td>
<td><p>此类是多个最低成本路由的容器，并且自身不包含任何属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies（作废）</p></td>
<td><p>此类包含多个 Lync Server 策略类，并且自身没有任何属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>此类表示单个 Lync Server 池。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>此类包含多个 Lync Server 池，并且自身没有任何属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>此类表示池的服务控制点。如果用户承载于池中，其 msRTCSIP-PrimaryHomeServer 属性将指向此类的实例。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>存储全局状态设置的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示由 SIP 注册器服务器维护的用户设置的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage（作废）</p></td>
<td><p>此类是表示电话路由用法的实例的容器。电话路由用法类由一个属性字段和一个说明字段组成。属性字段定义用法类型。通过说明字段，管理员可以描述此属性在电话路由中的用法。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages（作废）</p></td>
<td><p>此类包含 msRTCSIP-RouteUsage 类的多个实例，并且自身没有任何属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>这是 msRTCSIP-GlobalContainer 的辅助类，它包含用于限定和控制搜索结果范围的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>此类表示运行 Lync Server 的单个 SIP 服务器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>此类包含全局设置容器和 msRTCSIP-Domain 对象。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>此类包含表示受信任会议服务器的设置的属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>此类包含 msRTCSIP-TrustedMCU 类的多个实例，并且自身没有任何属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>此类包含多个 msRTCSIP-TrustedProxy 类，并且自身不包含任何属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>此类是表示运行代理服务器的服务器的容器。在加入 AD DS 的计算机上激活新的代理服务器时，将创建此类的实例。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>此类包含表示受信任服务器的设置的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>此类是表示可使用全局可路由用户代理 URI (GRUU) 地址进行路由的受信任服务的容器。激活受 Lync Server 信任的新服务器时，将创建此类的实例。此受信任服务器必须加入 Active Directory 域。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>此类是多个 GRUU 服务器的容器，并且自身不包含任何属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>此类包含表示受信任 Web 组件的设置的属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>此类包含 msRTCSIP-TrustedWebComponentServer 类的多个实例，并且自身没有任何属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications（作废）</p></td>
<td><p>这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与统一通信相关的属性。</p></td>
<td><p>Lync Server 2010 中已作废的类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>此类包含 Internet Information Server (IIS) 的服务控制点。它将服务器标识为 Web 组件服务器。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>此类提供从特定池到该池将使用的 Web 组件的关联。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>这是 msRTCSIP-WebComponents 的辅助类，其中包含表示 Web 组件的设置的属性。</p></td>
<td><p>Communications Server 2007 中的新增类。</p></td>
</tr>
</tbody>
</table>

