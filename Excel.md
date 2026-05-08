---
tags:
  - CS491
---
## Functions

### COUNTIF

Use `COUNTIF`, one of the statistical functions, to count the number of cells that meet a criterion; for example, to count the number of times a particular city appears in a customer list.

#### Syntax
`COUNTIF(range, criteria)

| **Argument name**       | **Description**                                                                                                                                                                                                                                                                                                                                                                                                             |
|:----------------------- |:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **range** (required)    | The group of cells you want to count. **_Range_** can contain numbers, arrays, a named range, or references that contain numbers. Blank and text values are ignored. <br><br>Learn how to [select ranges in a worksheet](https://support.microsoft.com/en-us/office/select-cell-contents-in-excel-23f64223-2b6b-453a-8688-248355f10fa9).                                                                                    |
| **criteria** (required) | A number, expression, cell reference, or text string that determines which cells will be counted. <br><br>For example, you can use a number like 32, a comparison like ">32", a cell like B4, or a word like "apples". <br><br>COUNTIF uses only a single criteria. Use [COUNTIFS](https://support.microsoft.com/en-us/office/countifs-function-dda3dc6e-f74e-4aee-88bc-aa8c2a866842) if you want to use multiple criteria. |

### FREQUENCY

The `FREQUENCY` function calculates how often values occur within a range of values, and then returns a vertical array of numbers. For example, use `FREQUENCY` to count the number of test scores that fall within ranges of scores. Because `FREQUENCY` returns an array, it must be entered as an array formula.

#### Syntax
`FREQUENCY(data_array, bins_array)`

The `FREQUENCY` function syntax has the following arguments:
- **data_array** Required. An array of or reference to a set of values for which you want to count frequencies. If data_array contains no values, FREQUENCY returns an array of zeros.
- **bins_array** Required. An array of or reference to intervals into which you want to group the values in data_array. If bins_array contains no values, FREQUENCY returns the number of elements in data_array.