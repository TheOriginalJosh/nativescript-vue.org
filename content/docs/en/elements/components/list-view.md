---
title: ListView
apiRef: https://docs.nativescript.org/api-reference/classes/_ui_list_view_.listview
contributors: [MisterBrownRSA, rigor789]
---

The ListView component shows items in a vertically scrolling list. You can set different `v-template`'s to specify how each item in the list should be displayed.

---

```html
<ListView for="item in listOfItems" @itemTap="onItemTap">
  <v-template>
    <Label :text="item.text" />
  </v-template>

  <v-template if="$odd">
    <Label :text="item.text" color="red" />
  </v-template>
</ListView>
```

In the above example the second template will be used if the item's index is odd.
For convenience you can use `$index`, `$even` and `$odd` helpers, but as needed you can use any valid javascript expression for a `v-template`'s `if` condition.

To learn more about the `v-template` component, head over to the [`v-template` documentation](/en/docs/utilities/v-template).

[> screenshots for=ListView <]

## Props

| name | type | description |
|------|------|-------------|
| `for` | `String` | The expression for iterating through the items, examples:<br>- `item in listOfItems`<br>- `(item, index) in listOfItems`<br>- `item in [1, 2, 3, 4, 5]`
| `items` | `Array<any>` | An array of items to be displayed in the ListView. **Note**: This property is only for advanced use, we recommend using the `for` property in most cases.

## Events

| name | description |
|------|-------------|
| `itemTap`| Emitted when an item in the ListView has been tapped. (To access the tapped item use `event.item`).

## Native Component
| Android | iOS |
|---------|-----|
| android.widget.ListView | UITableView
