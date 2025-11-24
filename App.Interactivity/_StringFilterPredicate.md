Source: https://www.noesisengine.com/docs/App.Interactivity._StringFilterPredicate.html

# StringFilterPredicate Class

## namespace [NoesisApp](/Gui.Core/_ClassHierarchy.md#noesisapp-namespace)

Predicate that matches a filter string against item text representation.

# Inheritance Hierarchy

• [FilterPredicate](/App.Interactivity/_FilterPredicate.md)

• *StringFilterPredicate*

# Properties

| Name | Description |
| --- | --- |
| ○ *Filter* | Gets or sets string filter used by this predicate |

● Dependency Property   ○ Reflection Property

# Attached Properties

StringFilterPredicate has no attached properties

# Methods

## From [FilterPredicate](/App.Interactivity/_FilterPredicate.md)

| Name | Description |
| --- | --- |
|  *Matches(item)* | Called to evaluate the predicate against the provided item |
|  *NeedsRefresh(item, propertyName)* | Indicates if filter should be re-evaluated after an item property change |
|  *Refresh()* | Re-evaluates the filter over the list |

# Events

## From [FilterPredicate](/App.Interactivity/_FilterPredicate.md)

| Name | Description |
| --- | --- |
| ◆ *FilterRequired* | Indicates that conditions changed and filter needs to be re-evaluated |

▸ Routed Event    Non-routed Event   ◆ Delegate Event