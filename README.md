# pretty-simple-accordion

## [Demo](https://codesandbox.io/s/pretty-simple-accordion-48lll)

## Events
| Name  	              | Description                                                           |
|---    	              |---	                                                                  |
| collapse-opened       | Event triggered when a collapse item opened. Returns index of target. |
| collapse-closed       | Event triggered when a collapse item closed. Returns index of target. |

## Props
| Name                  | Description                                        |
|---                    |---	                                               |
| title                 | title of collapse item. required.                  |
| content               | content of collapse item. required.                |
| collapseItemClass     | custom class can be added to component root level. |

## Class
| Name  	              | Description                                                  |
|---    	              |---	                                                         |
| collapse-head--active | A class placed at collapse-head when a collapse item opened. |