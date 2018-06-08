# Action: Enable and Disable

Use an enable/disable rule to make a field editable based on one or more conditions.

+$$$

**Example:** Part of the race registration fee pays for dog food. You don't have
to feed your chicken team with the provided dog food though. There's a single
selection field that asks *Would you like use the provided dog food?*. If you
check the box, you can select how much food, in US pounds, you'll need for your
team throughout the race. Since you're racing chickens, you won't check the box,
and the *Amount (US lb.)* field will be grayed out and disabled.

To follow the example, add a single selection field *Would you like to use the
provided dog food?* with two options: *Yes* and *No*.

Add a numeric field called *Amount (US lb.)* and make it an Integer. Use field
validation to make sure it's not greater than *100*.

To set up the enable/disable rule, 

1. Open the Rules tab of the Edit Form page and click the Add
   (![Add](../../../images/icon-add.png) button.

2. Define the rule:
    - If the *Would you like to use the provided dog food?* field is equal to *Yes*, enable the
        *Amount (US lb.)* field.

    ![Figure x: Build form rules quickly by defining your conditions and
    actions.](../../../images/forms-enable-rule.png)

    - Save the rule. 

    ![Figure x: Once a rule is saved, it is displayed so that you can easily understand what it does.](../../../images/forms-enable-rule2.png)

$$$

Now the user can fill out the amount of dog food they'll need only if they
specify that they do indeed want to use the provided food.
