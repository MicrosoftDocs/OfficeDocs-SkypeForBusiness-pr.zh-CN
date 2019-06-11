---
title: 'Lync Server 2013: 管理通讯簿服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>在 Lync Server 2013 中管理通讯簿服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-05_

作为 Lync Server、企业版或标准版服务器部署的一部分, 默认情况下会安装通讯簿服务。 通讯簿服务使用的数据库-RTCab-在 SQL Server 上创建 (对于企业版), 这是后端 SQL 服务器; 对于标准版服务器, collocated SQL Server。

<div>


> [!NOTE]  
> 有关使用 " <STRONG>Adsi 编辑</STRONG>" 编辑 Active Directory 域服务对象属性的信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI edit</A>。 有关特定于通讯簿服务的资源工具包中的工具的信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 资源工具包工具</A>。



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>通讯簿服务器电话号码规范化

Lync 服务器需要标准 RFC 3966/E: 164 个电话号码。 若要使用未结构化或格式不一致的电话号码, Lync Server 依赖于通讯簿服务器来预处理电话号码, 然后再将其移交给规范化规则。 当从通讯簿使用电话号码并且应用规范化规则时, 客户 (如 Lync Phone Edition 和 Lync Mobile) 可以使用这些标准化的数字。

无需进行一些调整, 以前版本中使用的规范化规则可能无法正常工作。 由于在规范化规则之前删除空白和非强制字符, 因此如果你的正则表达式表达式专门查找短划线或被删除的其他字符, 则你的规范化规则可能会失败。 你应该检查你的规范化规则, 以确保它们不会查找这些非强制字符, 或者规则可以正常失败, 并在该规则预期的位置不显示字符的情况下继续执行。

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>用户复制程序和通讯簿服务器

通讯簿服务器使用用户复制程序提供的数据更新最初从全局地址列表 (GAL) 中获取的信息。 用户复制程序将每个用户、联系人和组的 Active Directory 域服务属性写入数据库中的 AbUserEntry 表, 通讯簿服务器将数据库中的用户数据同步到通讯簿服务器文件存储中的文件和插入通讯簿数据库 RTCab。 AbUserEntry 表的架构使用两列**UserGuid**和**UserData**。 **UserGuid**是 index 列, 其中包含 Active Directory 对象的16字节 GUID。 **UserData**是一个图像列, 其中包含该联系人的所有前面提到的 Active Directory 域服务属性。

用户复制器通过读取位于基于 SQL Server 的同一 SQL 实例中的配置表来确定要写入哪些 Active Directory 属性。 AbUserEntry 表。 AbAttribute 表包含三列、 **ID**、**名称**、**标志**和**Enable**。 该表在数据库安装期间创建。 如果 AbAttribute 表为空, 则用户副本将跳过其 AbUserEntry 表处理逻辑。 通讯簿服务器属性是动态的, 从 AbAttribute 表中检索, 它是在激活通讯簿服务器时由通讯簿服务器初始编写的。

通讯簿服务器激活用下表中所示的值填充 AbAttribute 表。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>名称</th>
<th>标志</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>标题</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>子公司</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>个</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>db-9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>移动</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>至</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>邮件</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>岁</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>utf-16</p></td>
<td><p>部门</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>日</p></td>
<td><p>说明</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
<td><p>经理</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>名</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>条目</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


**ID**列中的数字必须是唯一的, 并且永远不应重复使用。 此外, 在256下保留 ID 值可节省由通讯簿服务器写入的输出文件中的空间。 但是, 最大 ID 值为65535。 "**名称**" 列对应于每个联系人的 AbUserEntry 表中用户复制器应放置的 Active Directory 属性名称。 **Flags**列中的值用于定义属性的类型。 以下类型的通讯簿服务器属性可由用户复制程序识别, 由 "**标志**" 列中值的低字节表示。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>字符串属性。 在将此类型存储在 AbUserEntry 表中之前, 用户副本会将此类型转换为 UTF-8。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>二进制属性。 用户复制程序将此存储在 blob 中, 无需任何转换。</p></td>
</tr>
<tr class="odd">
<td><p>反</p></td>
<td><p>字符串属性, 但仅当属性值以&quot;电话:&quot;开始时才包括该属性。 这主要适用于多值字符串属性, 特别是<strong>proxyAddresses</strong>。 在这种情况下, 通讯簿服务器仅感兴趣的<strong>proxyAddresses</strong>条目以&quot;电话开始&quot;:。 因此, 为了节省空间, 用户复制器仅存储以&quot;电话开始的条目:。&quot;</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>布尔字符串属性, 如果 TRUE, 则在 AbUserEntry 表中导致用户副本不包含此联系人。 如果为 FALSE, 则会导致用户复制器在 AbUserEntry 表中包含此联系人的属性, 而不是此标志的特定属性。 这是一个主要用于<strong>msExchHideFromAddressLists</strong>属性的特殊情况类型。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>字符串&quot;属性, 但仅当属性值以 smtp:&quot;开头并包含符号时才包括该&quot; @ &quot;属性。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>字符串属性, 但仅当属性&quot;值以电话:&quot;或&quot;smtp:&quot;开头, 并且包括&quot; @ &quot;符号时才包括该属性。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>如果设置, 这是一个多值属性, 可以为每个联系人多次显示。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>如果设置, 这将标识联系人的电子邮件用户帐户名属性。 通讯簿服务器使用此标志标识要在电话规范化事件日志条目中显示的属性值。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果设置, 这将标识联系人的必需属性。 只有当 Active Directory 中有此属性的值时, 通讯簿服务器才在 AbUserEntry 表中包含用户。 如果存在多个必需的属性, 则只有其中一个值需要具有一个值才能将用户包括在 AbUserEntry 表中。</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>如果设置, 通讯簿服务器将始终对此属性的值进行标准化。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>如果设置, 通讯簿服务器将使用<strong>proxyAddresses</strong>中的标准化数字 (如果<strong>UseNormalizationRules</strong> CMS 设置为 FALSE);否则, 其行为与标志位为0x1000 的情况相同。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果设置, 通讯簿服务器将不包括 AbUserEntry 表中具有指定属性的此值的对象。 例如, 如果<strong>msRTCSIP-PrimaryUserAddress</strong>属性具有此标志位集, 则具有此属性的联系人不会写入数据库。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果设置, 通讯簿服务器将不包含 AbUserEntry 表中的对象, 指定的属性没有此值。 如果在对象上设置了0x4000 和0x8000 标志位, 则将优先使用标志位值设置为0x4000 的属性, 并将该对象从 AbUserEntry 表中排除。</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>如果设置, 则表示群组对象。 用户复制器使用此标志位将联系人与<strong>groupType</strong>属性 (其状态表示 "通讯组列表" 或 "安全组") 一起包含。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>如果设置, 则用户复制器使用此标志 bit 将此属性包含在特定于设备的通讯簿服务器文件中 (即扩展名为 dabs 的文件)。</p></td>
</tr>
</tbody>
</table>


在早期版本的 Lync Server 中, 当应用对 Active Directory 的更改时, 管理员需要运行**CSUserDatabase**和**update-CSAddressBook** Windows PowerShell cmdlet 以将更改保存到 Lync 服务器用户数据库和 RTCab 数据库立即使用。 在 Lync Server 2013 中, Lync Server 用户复制程序将从 Active Directory 中获取更改, 并根据配置的间隔更新 Lync Server 用户数据库。 Lync Server 用户复制程序还将在无需运行 CSAddressBook 的情况下快速将更改传播到 RTCab 数据库。 如果启用了 "通讯簿" Web 查询, 则这些更改将反映在 Lync 客户端的搜索结果中。 只有当通讯簿文件下载已启用时, 管理员才需要运行 CSAddressBook 更新。

<div>


> [!NOTE]  
> 默认情况下, Lync Server 用户复制程序每隔5分钟自动运行一次。 你可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;配置此间隔。



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>筛选通讯簿

根据 AbAttribute 表中列出的某些 Active Directory 域服务属性, 可以控制在通讯簿服务器文件中填充的用户。 用于筛选的一个此类属性是**msExchangeHideFromAddressBook**属性。 这是 Exchange 架构添加的用户属性。 如果此属性的值为 TRUE, Exchange Server 将使用此属性从 Outlook 全球通讯簿 (GAL) 中隐藏联系人。 同样, 如果此属性的值为 TRUE, 则用户复制程序不会在 AbUserEntry 表中包含该用户, 并且此用户将不会位于通讯簿服务器文件中。

可以使用某些标志位来定义要在通讯簿服务器属性中使用的筛选器。 例如, 某些标志位的存在可以将属性标识为 include 属性或 exclude 属性。 用户复制程序筛选出包含 "排除" 属性的联系人, 并且筛选器包含不包含 "包含" 属性的筛选器。

<div>


> [!WARNING]  
> 有关筛选通讯簿的详细信息, 请参阅<A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Lync server 2013 中的通讯簿服务器 cmdlet</A>和<A href="http://go.microsoft.com/fwlink/?linkid=330430">筛选 lync 2013 通讯簿</A>



</div>

目前有三种不同的筛选器。 下表列出了这些筛选器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果设置, 这将标识联系人的必需属性。 用户复制程序使用此标志位筛选出不包含至少一个必需属性的联系人。 OuPathId 是一个必需的属性, 它是始终设置的。 因此, 至少应设置其他所需的属性之一。 否则, 联系人 (即具有必需属性 OuPathId 的值) 仍不会写入到数据库中。 例如, 如果<strong>telephoneNumber</strong>和<strong>homePhone</strong>定义为所需的属性, 则只有至少包含这些属性之一的联系人才会写入数据库。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果设置, 这将标识 "排除" 属性。 用户复制程序使用此标志位筛选出包含此属性的联系人。 例如, 如果<strong>msRTCSIP-PrimaryUserAddress</strong>定义为 exclude 属性, 则具有此属性的联系人不会写入数据库。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果设置, 这将标识一个 include 属性。 用户复制程序使用此标志位筛选出不包含此属性的联系人。 例如, 如果<strong>msRTCSIP-PrimaryUserAddress</strong>定义为 include 属性, 则仅将具有此属性的联系人写入数据库。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果同时设置了 0x4000 (exclude 属性) 和 0x8000 (include 属性) 标志位, 则0x4000 位将重写0x8000 位, 并且将排除该联系人。



</div>

虽然你可以筛选通讯簿以仅包含特定用户, 但限制条目不会限制其他用户联系筛选的用户或查看其状态。 通过输入用户的完整登录名, 用户始终可以查找、手动发送即时消息或手动发起对不在通讯簿中的用户的呼叫。 此外, 还可以在 Outlook 中找到用户的联系人信息。

在通讯簿文件中拥有完整的联系人记录后, 你就可以使用 Lync Server 启动电子邮件、电话或企业语音呼叫 (即, 如果在服务器上启用了企业语音), 并且用户没有为会话初始化配置的用户协议 (SIP), 某些组织希望在其通讯簿服务器条目中仅包含启用 SIP 的用户。 你可以通过清除以下必需属性的**Flags**列中的0x800 位来筛选通讯簿以仅包含启用了 SIP 的用户: **mailNickname**、 **telephoneNumber**、 **homePhone**和**mobile**。 您还可以通过在**msRTCSIP-PrimaryUserAddress**属性的**Flags**列中设置 0x8000 (include 属性) 来筛选通讯簿以仅包含启用了 SIP 的用户。 这还有助于从通讯簿文件中排除服务帐户。

修改 AbAttribute 表后, 您可以通过运行 cmdlet **Update-CsUserDatabase**命令来刷新 AbUserEntry 表中的数据。 在 UR 复制完成后, 你可以通过手动运行 cmdlet **UpdateCsAddressBook**命令来更新通讯簿服务器文件存储中的文件。

<div>


> [!NOTE]  
> 通讯簿服务器所在的前端服务器不能以管理方式进行配置。 在部署期间选择一个, 通常是部署的第一台前端服务器。 如果出现故障, 通讯簿服务将移动到另一台前端服务器, 不需要管理员注意。



</div>

<div>


> [!IMPORTANT]  
> 如果你已从多林部署或父/子部署 (如在移动到 Lync Server 之前合并基础结构) 进行了合并或更改了你的基础结构, 你可能会发现通讯簿服务下载和某些用户的通讯簿 Web 查询失败。 在具有多个域或林的部署中, 将在出现问题的用户对象上填充属性<STRONG>MsRTCSIP-OriginatorSid</STRONG> 。 要解决此问题, 必须在这些对象上将<STRONG>MsRTCSIP-OriginatorSid</STRONG>属性设置为 NULL。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

