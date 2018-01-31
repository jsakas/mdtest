# Pagination

Creating dynamic pagination with asynchronous data can be done easily using the `withPagination` higher-order component.

## Usage

```es6
import { withPagintion } from 'bp-ui';

const MyComponent = (data) => {
  /* should do something with data prop */
  return ()
}

const fetchFn = (payload) => { /* should return a Promise */};
const defaultPayload = { page: 5 }
const PaginatedDataTable = withPagination(MyComponent)

const OtherComponent = () => {
  return (<PaginatedDataTable fetchFn={fetchFn} defaultPayload={defaultPayload} />);
}
```

## Props

<table>
  <tr>
    <th>
      Name
    </th>
    <th>
      Type
    </th>
    <th>
      Description / Example
    </th>
  </tr>
  <tr>
    <td>
      fetchFn
    </td>
    <td>
      `function(payload)`
    </td>
    <td>
      A function that retrieves data. It is passed a payload which contains `page` and `per_page`. This function should return a Promise.
    </td>
  </tr>
  <tr>
    <td>
      defaultPayload
    </td>
    <td>
      `object`
    </td>
    <td>
      The default payload is used to set query params in the fetchFn. If you supply page or per_page they will be used for the initial request, but handled automatically for any future requests.
    </td>
  </tr>
</table>
