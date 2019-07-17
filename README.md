# pretty-simple-accordion

# Demo

<!-- See [Configuration Reference](https://cli.vuejs.org/config/). -->

# Events
| Name  	              | Description                                                           |
|---    	              |---	                                                                  |
| collapse-opened       | Event triggered when a collapse item opened. Returns index of target. |
| collapse-closed       | Event triggered when a collapse item closed. Returns index of target. |

# Props
| Name                  | Description                                        |
|---                    |---	                                               |
| title                 | title of collapse item. required.                  |
| content               | content of collapse item. required.                |
| collapseItemClass     | custom class can be added to component root level. |

# Class
| Name  	              | Description                                                  |
|---    	              |---	                                                         |
| collapse-head--active | A class placed at collapse-head when a collapse item opened. |

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

