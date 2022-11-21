在 Microsoft Teams 中，每个自动助理或呼叫队列都需要一个资源帐户。 还可以为资源帐户分配服务电话号码。 这是将电话号码分配给自动助理和呼叫队列的方式，允许来自 Teams 外部的呼叫者到达自动助理或呼叫队列。

本文介绍如何创建资源帐户，并准备好将其与自动助理和呼叫队列配合使用。

在开始本文中的过程之前，请确保已完成以下操作：

- [获取Microsoft Teams 电话资源帐户许可证](#obtain-microsoft-teams-phone-resource-account-licenses)
- [获取服务编号](#obtain-service-numbers)

> [!NOTE]
> 用于自动助理和呼叫队列的资源帐户在登录时处于禁用状态，并且必须保持登录状态。 聊天和状态不适用于这些帐户。

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>获取Microsoft Teams 电话资源帐户许可证

每个资源帐户都需要许可证才能使用自动助理和呼叫队列，称为 *Microsoft Teams 电话资源帐户* 许可证。 使用 Teams Phone 的订阅会自动免费分配 *Microsoft Teams 电话资源帐户* 许可证，如果需要更多许可证，可以购买其他 *Microsoft Teams 电话资源帐户* 许可证。 有关如何获取这些许可证的详细信息，请参阅[Microsoft Teams 电话资源帐户许可证](../teams-add-on-licensing/virtual-user.md)。

[本文稍后介绍如何将许可证分配给资源帐户](#assign-a-license)。

如果你购买了具有通话套餐捆绑许可证 **的 Teams 电话标准版** 或 **Teams 电话**，则你的帐户中已有 *Teams 电话资源帐户* 许可证。

若要查看是否已拥有资源帐户许可证，请使用具有全局管理员权限的帐户登录到 Microsoft 365。 然后，转到 [“你的产品>计费](https://admin.microsoft.com/Adminportal/Home#/subscriptions)”。 如果有资源帐户许可证，则它们将显示为 **资源帐户Microsoft Teams 电话**。

1. 打开Microsoft 365 管理中心并使用全局管理员用户登录。这通常是用于注册 Microsoft 365 的帐户。
2. 在左侧导航窗格中，转到 [**“计费** > **购买服务**](https://admin.microsoft.com/Adminportal/Home#/catalog) > **”“** > 加载项 **”“查看所有加载项产品**”。
3. 滚动到末尾以查找 **Microsoft Teams 电话资源帐户** 许可证。 选择 **“详细信息**”，然后选择“ **购买**”。
4. 在许可证购买页上，选择所需的资源帐户许可证数。 需要为每个计划设置的自动助理和呼叫队列提供一个资源帐户许可证。 建议至少选择五个许可证，以便将来可以轻松设置更多自动助理和呼叫队列，而无需立即购买更多许可证。
5. 取消选中“ **自动分配给没有许可证的所有用户**”。
6. 选择“ **立即签出**”。
7. 确认订单，选择“ **下一步**”，然后选择“ **下订单**”。

成本为零，但仍需要按照以下步骤获取许可证。

### <a name="obtain-service-numbers"></a>获取服务编号

服务号码对于自动助理和呼叫队列是可选的，但至少需要一个服务号码才能让呼叫者访问你的自动助理和呼叫队列配置。 对于希望通过服务号码直接访问的任何自动助理或呼叫队列，必须具有具有关联的服务号码的资源帐户。

资源帐户可以使用收费或免费服务号码。 可以从其他运营商请求新号码或转网现有号码。

若要获取新的服务号码，请参阅 [获取服务电话号码](../getting-service-phone-numbers.md)。

若要从其他运营商转网号码，请参阅 [将电话号码转移到 Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

## <a name="create-a-resource-account"></a>创建资源帐户

可以在 Teams 管理中心创建资源帐户。

1. 在 Teams 管理中心中，展开“ **语音**”，然后选择“ **资源帐户**”。
2. 选择“**添加**”。
3. 在 **“添加资源帐户** ”窗格中，填写 **“显示名称**”、“ **用户名”** 和“ **资源帐户类型**”。 资源帐户类型可以是 **自动助理** 或 **呼叫队列**，具体取决于你打算如何使用此资源帐户。
4. 选择“**保存**”。

## <a name="assign-a-license"></a>分配许可证

对于每个资源帐户，必须分配 *Microsoft Teams 电话资源帐户* 许可证或 *Teams 电话标准版* 许可证。

1. 在Microsoft 365 管理中心中，展开 **“用户**”，然后选择“**活动用户**”。
2. 选择要向其分配许可证的资源帐户。 将显示资源帐户的用户窗格。
3. 在“**许可证和应用**”选项卡上的“**许可证**”下，选择 **“Microsoft Teams 电话资源帐户**”。
4. 选择 **“保存更改**”。

## <a name="assign-a-service-number"></a>分配服务编号

如果计划将资源帐户与需要服务号码的自动助理或呼叫队列配合使用，请为资源帐户分配号码。

1. 在 Teams 管理中心的“ **资源帐户** ”页上，选择要为其分配服务编号的资源帐户，然后选择“ **分配/取消分配**”。
2. 在 **“电话号码类型** ”下拉列表中，选择要使用的号码类型。
3. 在 **“分配的电话号码** ”框中，搜索要使用的号码，然后选择“ **添加**”。 请确保包含国家/地区代码 (例如，) +1 250 555 0012。
4. 选择“**保存**”。

若要将直接路由或混合编号分配给资源帐户，需要使用 PowerShell：

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`
