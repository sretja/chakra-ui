---
"@chakra-ui/tabs": minor
---

This change restores the original behavior of the `isLazy` prop and adds a new
`unmountHiddenPanels` prop which configures the behavior of `isLazy`.

Before `1.3.2`, `isLazy` caused tab panels to be rendered only when selected,
meaning that a selected panel was unmounted after another tab was selected.
Unfortunately, a change made as part of `1.3.2` broke that behavior by changing
the default behavior to rendering panels that are selected or were previously
selected, meaning that once a tab panel has been rendered, it remains rendered.

Hidden panel unmounting can now be toggled via the `unmountHiddenPanels` prop.
The default value of this prop (`true`) restores the original behavior of
`isLazy` by unmounting tab panels when they are no longer selected, while
`false` leaves previously selected tab panels mounted.
