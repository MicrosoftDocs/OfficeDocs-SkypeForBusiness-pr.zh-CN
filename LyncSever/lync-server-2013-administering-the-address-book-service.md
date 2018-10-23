---
title: 在 Lync Server 2013 中管理通讯簿服务
TOCTitle: 在 Lync Server 2013 中管理通讯簿服务
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429711(v=OCS.15)
ms:contentKeyID: 49313398
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理通讯簿服务

 

_**上一次修改主题：** 2016-12-08_

通讯簿服务是 Lync Server企业版 或 Standard Edition Server 部署的一部分，将默认安装。通讯簿服务使用的数据库 RTCab 在 SQL Server 中创建（对于 企业版，这是后端 SQL Server；对于 Standard Edition Server，这是并置的 SQL Server）。

> [!NOTE]  
> 有关使用 <strong>ADSI Edit</strong> 编辑 Active Directory 域服务 对象属性的信息，请参阅 <a href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</a>。有关资源工具包中专用于通讯簿服务的工具的信息，请参阅 <a href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 资源工具包工具</a>。



## 通讯簿服务器电话号码规范化

Lync Server 需要标准化的 RFC 3966/E.164 电话号码。要使用非结构化或格式不一致的电话号码，Lync Server 依赖通讯簿服务器在将电话号码转交至规范化规则之前对其进行预处理。当使用通讯簿中的电话号码并应用规范化规则后，客户端（如 Lync Phone Edition 和 Lync Mobile）可以使用这些规范化的号码。

对于以前版本中使用的规范化规则，如果不进行某些调整，可能无法正常使用。由于在规范化规则之前删除了空格和非必需的字符，因此如果正则表达式专门查找已删除的短划线或其他字符，则规范化规则可能失败。应检查规范化规则以确保它们不查找这些非必需字符，或者允许规则在期望字符出现但未出现的情况下正常中止并继续执行。

## 用户复制程序和通讯簿服务器

通讯簿服务器使用由用户复制程序提供的数据来更新最初从全局地址列表 (GAL) 中获取的信息。用户复制程序将每个用户、联系人和组的 Active Directory 域服务 属性写入数据库中的 AbUserEntry 表，然后通讯簿服务器将数据库中的用户数据同步至通讯簿服务器文件存储中的文件和通讯簿数据库 RTCab。AbUserEntry 表的架构使用两列：**UserGuid** 和 **UserData**。**UserGuid** 是索引列，包含 Active Directory 对象的 16 字节 GUID。**UserData** 是图像列，包含前面提到的该联系人的所有 Active Directory 域服务 属性。

用户复制程序通过读取位于 AbUserEntry 表所在的同一基于 SQL Server 的实例的配置表确定要写入的 Active Directory 属性。AbAttribute 表包含四列：**ID**、**Name**、**Flags** 和 **Enable**。该表在数据库安装期间创建。如果 AbAttribute 表为空，用户复制程序将跳过其 AbUserEntry 表处理逻辑。通讯簿服务器属性是动态的，可以从 AbAttribute 表中检索，该表最初在通讯簿服务器激活时由通讯簿服务器写入。

通讯簿服务器激活将使用下表中所示的值填充 AbAttribute 表。


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
<td><p>Title</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
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
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
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
<td><p>Mail</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Department</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17</p></td>
<td><p>Description</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


**ID** 列中的数字必须唯一，并且绝对不能重复使用。另外，使 ID 值低于 256 可以节省通讯簿服务器写入的输出文件的空间。然而，最大 ID 值是 65535。**Name** 列对应于用户复制程序应在 AbUserEntry 表中为每个联系人放入的 Active Directory 属性名称。**Flags** 列中的值用于定义属性类型。以下类型的通讯簿服务器属性由用户复制程序标识，并由 **Flags** 列中的值的低位字节指示。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>字符串属性。用户复制程序在将此类型存储在 AbUserEntry 表中之前，先将其转换成 UTF-8。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>二进制属性。用户复制程序不进行任何转换即将此类型存储在 blob 中。</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>字符串属性，但是仅当属性值以“tel:”开头时才包含此类型。此类型主要用于多值字符串属性，特别是 <strong>proxyAddresses</strong>。在这种情况下，通讯簿服务器仅关注以“tel:”开头的 <strong>proxyAddresses</strong> 条目。因此，为了节省空间，用户复制程序将仅存储以“tel:”开头的条目。</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>布尔字符串属性，如果为 TRUE，用户复制程序不会将此联系人包含在 AbUserEntry 表中。如果为 FALSE，用户复制程序会将此联系人的属性包含在 AbUserEntry 表中，但不包含具有此标志的特定属性。这是另一种特殊类型，主要用于 <strong>msExchHideFromAddressLists</strong> 属性。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>字符串属性，但是仅当属性值以“smtp:”开头并包含“@”符号时才包含此类型。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>字符串属性，但是仅当属性值以“tel:”或“smtp:”开头并包含“@”符号时才包含此类型。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>如果设置，则是可针对每个联系人出现多次的多值属性。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>如果设置，将标识联系人的电子邮件用户帐户名属性。通讯簿服务器使用此标志来标识在电话规范化事件日志条目中显示的属性值。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果设置，将标识联系人的必需属性。仅当在 Active Directory 中存在此属性的值时，通讯簿服务器才会在 AbUserEntry 表中包含用户。如果存在多个必需属性，只需其中一个属性具有值即会在 AbUserEntry 表中包含用户。</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>如果设置，通讯簿服务器将始终规范化此属性的值。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>如果设置并且 <strong>UseNormalizationRules</strong> CMS 设置为 FALSE，通讯簿服务器将使用 <strong>proxyAddresses</strong> 中的规范化号码；否则通讯簿服务器的行为将与标志位是 0x1000 时相同。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果设置，通讯簿服务器不会在 AbUserEntry 表中包含为指定属性设置了此值的对象。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 属性设置了此标志位，则不会将具有此属性的联系人写入数据库。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果设置，通讯簿服务器不会在 AbUserEntry 表中包含没有为指定属性设置此值的对象。如果在一个对象上设置了 0x4000 和 0x8000 标志位，则标志位值设置为 0x4000 的属性优先，并且会在 AbUserEntry 表中排除该对象。</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>如果设置，则代表组对象。用户复制程序使用此标志位包含具有 <strong>groupType</strong> 属性且状态指示组（例如，通讯组列表或安全组）的联系人。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>如果设置，用户复制程序将使用此标志位在特定于设备的通讯簿服务器文件（即扩展名为 .dabs 的文件）中包含此属性。</p></td>
</tr>
</tbody>
</table>


在早期版本的 Lync Server 中，当向 Active Directory 应用更改时，管理员将需要运行 **Update -CSUserDatabase** 和 **Update –CSAddressBook**Windows PowerShell cmdlet 以立即保留对 Lync Server 用户数据库和 RTCab 数据库的更改。在 Lync Server 2013 中，Lync Server 用户复制程序将从 Active Directory 选取更改并根据配置的间隔更新 Lync Server 用户数据库。Lync Server 用户复制程序还会快速传播对 RTCab 数据库的更改，此时管理员不必运行 Update-CSAddressBook。如果启用了地址簿 Web 查询，则这些更改将由 Lync 客户端在搜索结果中反映。如果启用了地址簿文件下载，则管理员只需运行 Update -CSAddressBook。

> [!NOTE]  
> 默认情况下，Lync Server 用户复制程序每 5 分钟自动运行一次。您可以使用 Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt; 配置此间隔。



## 筛选通讯簿

通讯簿服务器文件中填充的用户可以基于 AbAttribute 表中列出的特定 Active Directory 域服务 属性进行控制。**msExchangeHideFromAddressBook** 属性是一个用于筛选的此类属性。这是由 Exchange 架构添加的用户属性。如果将此属性的值为 TRUE，Exchange Server 将使用此属性隐藏 Outlook 全局地址列表 (GAL) 中的联系人。同样，如果此属性的值为 TRUE，用户复制程序不会在 AbUserEntry 表中包含该用户，并且该用户不会包含在通讯簿服务器文件中。

可以使用某些标志位定义用于通讯簿服务器属性的筛选器。例如，某些标志位的状态可以将属性标识为包含属性或排除属性。用户复制程序筛选出包含排除属性的联系人，并筛选出不包含包含属性的联系人。

> [!WARNING]
> 有关筛选通讯簿的详细信息，请参阅<a href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">通讯簿服务器 Cmdlet</a> 和<a href="http://go.microsoft.com/fwlink/?linkid=330430">筛选 Lync 2013 通讯簿</a>


目前，存在三种不同的筛选器。下表列出了这些筛选器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果设置，将标识联系人的必需属性。用户复制程序使用此标志位筛选出未包含至少一个必需属性的联系人。OuPathId 是必需属性，始终会设置。因此，应至少设置一个其他必需属性。否则，仍无法将联系人（即具有必需属性 OuPathId 的值）写入数据库。例如，如果将 <strong>telephoneNumber</strong> 和 <strong>homePhone</strong> 定义为必需属性，则只有至少具有其中一个属性的联系人才会写入数据库。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果设置，将标识排除属性。用户复制程序使用此标志位筛选出包含此属性的联系人。例如，如果将 <strong>msRTCSIP-PrimaryUserAddress</strong> 定义为排除属性，则不会将具有此属性的联系人写入数据库。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果设置，将标识包含属性。用户复制程序使用此标志位筛选出不包含此属性的联系人。例如，如果将 <strong>msRTCSIP-PrimaryUserAddress</strong> 定义为包含属性，则仅将具有此属性的联系人写入数据库。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 如果同时设置了 0x4000（排除属性）和 0x8000（包含属性）标志位，0x4000 位将覆盖 0x8000 位，并且将排除联系人。



尽管可以筛选通讯簿以仅包含特定用户，但是限制条目不会限制其他用户联系筛选出的用户或查看其状态的能力。通过输入用户的完整登录名，用户始终可以查找通讯簿中不存在的用户，手动向这些用户发送即时消息或者手动发起呼叫。此外，还可以在 Outlook 中找到用户的联系人信息。

如果通讯簿文件中包含完整的联系人记录，您将可以使用 Lync Server 向未配置会话初始协议 (SIP) 的用户发送电子邮件、拨打电话或发起企业语音呼叫（即，如果在服务器中启用了企业语音）。尽管如此，某些组织还是更愿意在通讯簿服务器条目中仅包含已启用 SIP 的用户。通过在以下必需属性的**标志**列中清除 0x800 位，可以对通讯簿进行筛选，使通讯簿仅包含已启用 SIP 的用户：**mailNickname**、**telephoneNumber**、**homePhone** 和 **mobile**。还可以通过在 **msRTCSIP-PrimaryUserAddress** 属性的**标志**列中设置 0x8000（包含属性），对通讯簿进行筛选，使通讯簿仅包含已启用 SIP 的用户。这还有助于排除通讯簿文件中的服务帐户。

修改 AbAttribute 表后，可以通过运行 cmdlet **Update-CsUserDatabase** 命令刷新 AbUserEntry 表中的数据。UR 复制完成后，可以通过手动运行 cmdlet **UpdateCsAddressBook** 命令更新通讯簿服务器文件存储中的文件。

> [!NOTE]  
> 无法以管理方式配置通讯簿服务器所在的前端服务器。在部署期间选定一个前端服务器，通常是部署的第一个前端服务器。出现故障时，通讯簿服务将转移至另一个前端服务器，并且不需要进行管理。



> [!IMPORTANT]  
> 如果合并或修改了多林部署或父/子部署的基础结构（例如，在移动至 Lync Server 之前合并基础结构），可能导致某些用户执行通讯簿服务下载和通讯簿 Web 查询时失败。在包含多个域或林的部署中时，将在出现此问题的用户对象上填充 <strong>MsRTCSIP-OriginatorSid</strong> 属性。为了解决此问题，必须在这些对象上将 <strong>MsRTCSIP-OriginatorSid</strong> 属性设置为 NULL。

