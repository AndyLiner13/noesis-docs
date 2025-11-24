Source: https://www.noesisengine.com/docs/App.Interactivity._FilterPredicate.html

# FilterPredicate Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Base class for Filter predicate object used by [CollectionFilterBehavior](/App.Interactivity/_CollectionFilterBehavior.md).

# Inheritance Hierarchy

• *FilterPredicate*

• [StringFilterPredicate](/App.Interactivity/_StringFilterPredicate.md)

# Properties

FilterPredicate has no properties

# Attached Properties

FilterPredicate has no attached properties

# Methods

| Name | Description |
| --- | --- |
|  *Matches(item)* | Called to evaluate the predicate against the provided item |
|  *NeedsRefresh(item, propertyName)* | Indicates if filter should be re-evaluated after an item property change |
|  *Refresh()* | Re-evaluates the filter over the list |

# Events

| Name | Description |
| --- | --- |
| ◆ *FilterRequired* | Indicates that conditions changed and filter needs to be re-evaluated |

▸ Routed Event    Non-routed Event   ◆ Delegate Event