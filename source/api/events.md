# Events

All component events can be captured using the usual Vue event syntax:
```html
  <template>
    <tree-vue
        :items="items"
        :options="options"
        ref="treeVue"
        @tree:checked:all="onCheckedAll"
        @node:enabled="onNodeEnabled"
    />
  </template>
  ...
```

The component events are divided into two groups: tree events and node events.

## Tree events

| Name                   | Parameters   |  Description |
|------------------------|:------------:|:-------------|
| **tree:checked:all**           | none   | Emits on `checkAll` function call |
| **tree:checked:visible**           | none   | Emits on `checkVisible` function call |
| **tree:collapsed:all**           | none   | Emits on `collapseAll` function call |
| **tree:disabled:all**           | none   | Emits on `disableAll` function call |
| **tree:enabled:all**           | none   | Emits on `enableAll` function call |
| **tree:filtered**           | matched nodes, search object   | Emits on `filter` function call. First parameter is the array of all nodes that are matched the search object passed to `filter` function. Second one is the search object passed to `filter` function.|
| **tree:filter:cleared**           | none   | Emits on `clearFilter` function call.|
| **tree:unchecked:all**           | none   | Emits on `uncheckAll` function call |
| **tree:unchecked:visible**           | none   | Emits on `uncheckVisible` function call |

## Node events

| Name                   | Parameters   |  Description |
|------------------------|:------------:|:-------------|
| **node:child:added**           | source item, child node   | Emits on  adding child node to another node (`addChild` or `insertChild` functions). First parameter is the source item that is being added as a child. Second one is the child node representing this source item. |
| **node:child:removed**           | node   | Emits on removing child node (`remove` function call on a child node). The parameter is the removed child node. |
| **node:clicked**           | node   | Emits on clicking a node text. The parameter is the clicked node. |
| **node:collapsed**           | node   | Emits on collapsing node (for instance after `collapse` function call). The parameter is the collapsed node. |
| **node:disabled**           | node   | Emits on disabling node (for instance after `disable` function call). The parameter is the disabled node. |
| **node:enabled**           | node   | Emits on enabling node (for instance after `enable` function call). The parameter is the enabled node. |
| **node:expanded**           | node   | Emits on expanding node (for instance after `expand` function call). The parameter is the expanded node. |
| **node:focused**           | node   | Emits after a node received focus on its text component. The parameter is the focused node. |
| **node:removed**           | node   | Emits on removing root node (`remove` function call on a root node). The parameter is the removed root node. |
| **node:selected**           | node &#124; null  | Emits on slecting node (`select` function call or when a node receives focus). The parameter is the selected node. |
