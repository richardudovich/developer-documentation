<small>Piwik\DataTable\Filter\</small>

Pattern
=======

Deletes every row for which a specific column does not match a supplied regex pattern.

**Example**

    // filter out all rows whose labels doesn't start with piwik
    $dataTable->filter('Pattern', array('label', '^piwik'));

Methods
-------

The class defines the following methods:

- [`__construct()`](#__construct) &mdash; Constructor.
- [`filter()`](#filter) &mdash; See [Pattern](/api-reference/Piwik/DataTable/Filter/Pattern).
- [`enableRecursive()`](#enablerecursive) &mdash; Enables/Disables recursive filtering. Inherited from [`BaseFilter`](../../../Piwik/DataTable/BaseFilter.md)
- [`filterSubTable()`](#filtersubtable) &mdash; Filters a row's subtable, if one exists and is loaded in memory. Inherited from [`BaseFilter`](../../../Piwik/DataTable/BaseFilter.md)

<a name="__construct" id="__construct"></a>
<a name="__construct" id="__construct"></a>
### `__construct()`

Constructor.

#### Signature

-  It accepts the following parameter(s):
    - `$table` ([`DataTable`](../../../Piwik/DataTable.md)) &mdash;
       The table to eventually filter.
    - `$columnToFilter` (`string`) &mdash;
       The column to match with the `$patternToSearch` pattern.
    - `$patternToSearch` (`string`) &mdash;
       The regex pattern to use.
    - `$invertedMatch` (`bool`) &mdash;
       Whether to invert the pattern or not. If true, will remove rows if they match the pattern.

<a name="filter" id="filter"></a>
<a name="filter" id="filter"></a>
### `filter()`

See [Pattern](/api-reference/Piwik/DataTable/Filter/Pattern).

#### Signature

-  It accepts the following parameter(s):
    - `$table` ([`DataTable`](../../../Piwik/DataTable.md)) &mdash;
      
- It does not return anything.

<a name="enablerecursive" id="enablerecursive"></a>
<a name="enableRecursive" id="enableRecursive"></a>
### `enableRecursive()`

Enables/Disables recursive filtering.

Whether this property is actually used
is up to the derived BaseFilter class.

#### Signature

-  It accepts the following parameter(s):
    - `$enable` (`bool`) &mdash;
      
- It does not return anything.

<a name="filtersubtable" id="filtersubtable"></a>
<a name="filterSubTable" id="filterSubTable"></a>
### `filterSubTable()`

Filters a row's subtable, if one exists and is loaded in memory.

#### Signature

-  It accepts the following parameter(s):
    - `$row` ([`Row`](../../../Piwik/DataTable/Row.md)) &mdash;
       The row whose subtable should be filter.
- It does not return anything.

