---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the DataGrid documentation!

DataGrid uses JSX syntax, react toolbox lib for buttons and lodash for data manipulation.

You can use DataGrid as server side or frontend side processing.

# Initialization

> To initialize DataGird, use this code as example (bServerSide: false):

```javascript
import DataGrid from '[pathToConstants]/DataGridNew'
import { ENTITY_NAMES } from '[pathToConstants]/constants';
import { DATA_GRID_ACTION_TYPE, DATA_GRID_COLUMN_TYPES } from '[pathToConstants]/DataGridNew/dataGridConstants';
constructor(props) {
    super(props);
    this.sEntityIdName = 'stocks';
    this.sEntityId = ENTITY_NAMES.STOCKS;

    this.columns = [
      {
        sName: 'product_name',
        label: i18nMessage('stock.grid.productName'),
        bSearchable: true,
        bSortable: true,
        type: DATA_GRID_COLUMN_TYPES.string,
      },
      {
        sName: 'product_sku',
        label: i18nMessage('stock.grid.productSku'),
        bSearchable: true,
        bSortable: true,
        sortOption: { numeric: true },
        type: DATA_GRID_COLUMN_TYPES.string,
      },
      {
        sName: 'location_code',
        label: i18nMessage('stock.grid.locationCode'),
        bSearchable: true,
        bSortable: true,
        type: DATA_GRID_COLUMN_TYPES.string,
      },
      {
        sName: 'quantity',
        label: i18nMessage('stock.grid.quantity'),
        bSortable: true,
        sortOption: { numeric: true },
        type: DATA_GRID_COLUMN_TYPES.string,
      },
    ];
    this.dataGridOptions = {
      bServerSide: false,
      rowId: 'id',
      sEntityName: i18nMessage('navigation.stocks.stocksAll'),
      sEntityId: this.sEntityId,
      sEntityIdName: this.sEntityIdName,
      bPagination: true,
      onTableChange: this.onTableChange,
    };
  };
<DataGrid
    columns={this.columns}
    data={rows}
    options={_options}
    loading={stocksData.get('rowsLoading')}
    totalResults={totalResults}
    sEntityId={this.sEntityId}
  />
```

> Make sure to replace `sEntityIdName`, `sEntityIdName` with proper values.

Minimal requirements.

<aside class="notice">
Make sure to replace `sEntityIdName`, `sEntityIdName` with proper values.
</aside>

# DataGrid props and options

## Props

```ruby
```

```python
```

```shell
```

> List of all dataGrid options:

```javascript
static propTypes = {
    options: PropTypes.shape( shapeTypes: {...}),
    columns: PropTypes.arrayOf(PropTypes.object).isRequired,
          data: ImmutablePropTypes.list.isRequired,
          totalResults: PropTypes.number.isRequired,
          styleType: PropTypes.number,
          loading: PropTypes.bool,
          bResetSearchFilters: PropTypes.bool,
          bResetPage: PropTypes.bool,
          fabConfig: PropTypes.object,
    };
```
List of all dataGrid props.

Prop | Type | Description
--------- | ------- | -----------
options | shape | Collection of options .
columns | arrayOf(PropTypes.object) | Array of column objects
data | ImmutablePropTypes.list | Immutable data list
totalResults | number | Total data count
styleType | number | Use one of data grid built in styles
loading | boolean | Is data loading
bResetSearchFilters | boolean | Trigger reset table search filters
bResetPage | boolean | Trigger reset table page
fabConfig | object | Used for trigger show form

## All Options

```ruby
```

```python
```

```shell
```

> List of all dataGrid options:

```javascript
options: PropTypes.shape({
      rowId: PropTypes.string.isRequired,
      bMultipleSelect: PropTypes.bool,
      bCheckAble: PropTypes.bool,
      bCheckAbleDisabled: PropTypes.bool,
      bServerSide: PropTypes.bool,
      bPagination: PropTypes.bool,
      bInfo: PropTypes.bool,
      bLengthMenu: PropTypes.bool,
      sEntityName: PropTypes.string,
      sEntityId: PropTypes.number,
      sEntityIdName: PropTypes.string,
      language: PropTypes.object,
      languageCode: PropTypes.string,
      rowsPerPage: PropTypes.number,
      lengthMenu: PropTypes.arrayOf(PropTypes.object),
      onRowSelected: PropTypes.func,
      onRowSelectedId: PropTypes.func,
      onRowClick: PropTypes.func,
      selectedRow: PropTypes.string,
      selectedRows: PropTypes.array,
      selectedRowsIds: PropTypes.array,
      onTableChange: PropTypes.func,
      menuOptions: PropTypes.array,
      menuOptionsSelected: PropTypes.func,
      menuOptionsDisabled: PropTypes.func,
      count: PropTypes.number,
    })
```

List of all dataGrid options.

### HTTP Request

`GET http://pulpo.co`

### Options

Option | Type | Default | Description
--------- | ------- | ------- | -----------
rowId | number or string | rowId | Identify row id property .
bCheckAble | boolean | false | If set to false, table won't have checkbox column
bCheckAbleDisabled | boolean | false | If set to true, check box will be disabled
bServerSide | boolean | true | If set to true dataGrid will receive and fetch data from server on each change
bPagination | boolean | true | pagination show on/off
bInfo | boolean | true | info text show on/off
bFooter | boolean | true | Footer show on/off
bLengthMenu | boolean | false | Show length menu selector
bSelectFirst | boolean | false | Select first row when DataGrid data loaded
sEntityName | string | '' | Set entity name
sEntityId | number | null | Set entity id
sEntityIdName | string | '' | Set entity id name
rowsPerPage | number | 20 | Number or rows displayed
lengthMenu | array | DATA_GRID_DEFAULT_DISPLAY_LENGTH_MENU | Display length menu selector
onRowSelected | function | null | Function
onRowSelectedId | function | null | Function
onRowClick | function | null | Function
selectedRow | string | '' | Selected row id
selectedRows | immutable list | null | Selected rows immutable list
selectedRowsIds | array| null | Selected rows ids array
onTableChange | function| null | Connect this function to get dataGrid changes
menuOptions | array | null | Provide menu options
menuOptionsSelected | function | null | Provide menu options callback function
menuOptionsDisabled | function | null | provide a function to disable menu on some rows



<aside class="success">
Remember — check browser console to see which options you need to pass. DataGrid will throw an error or warning in console!
</aside>

## Data Grid server side example

> Import commands:

```javascript
import DataGrid from '[pathToConstants]/DataGridNew'
import { ENTITY_NAMES } from '[pathToConstants]/constants';
import { DATA_GRID_ACTION_TYPE, DATA_GRID_COLUMN_TYPES } from '[pathToConstants]/DataGridNew/dataGridConstants';
```
> Deine columns and da:

This example will be present with Sales order functionality.

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

