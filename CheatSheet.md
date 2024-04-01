# Pine Script v5 Cheat Sheet

A comprehensive guide to Pine Script language used for creating trading indicators and strategies on TradingView.

## Basics

### Version Declaration
```pine
//@version=5
```
Declare the version of Pine Script being used. Always include this at the top of your script.

### Indicator & Strategy Declaration
```pine
indicator(title="My Indicator", shorttitle="MI", overlay=true)
```
```pine

strategy(title="My Strategy", shorttitle="MS", overlay=true, ...)
```
Indicate whether your script is an indicator or a strategy.

## Script Structure
1) Version Declaration: //@version=5
2) Library Imports: (if any)
3) Parameter Inputs: Using input()
4) Variable Declarations
5) Main Code: Includes calculation and plotting logic
6) Plotting Functions/Strategy Conditions
## Variables and Types
### Variable Declaration and Assignment
```pine
int myInt = 10
float myFloat = 123.45
bool myBool = true
string myString = "Hello, World"
color myColor = color.red
```
### Mutable Variables
Use := for reassignment of variables.

```pine

var int myCounter = 0
myCounter := myCounter + 1
```
## Control Structures
### Conditional Statements
```pine

if (condition) {
    // code
} else if (otherCondition) {
    // code
} else {
    // code
}
```
## Loops
Mainly for loops are used for iterating.

```pine
for var i = 0 to 10 by 1
    // code
```
## Functions and Built-ins
### User-Defined Functions
Define your own functions for reuse throughout your script.

```pine

f_myFunction(param1, param2) =>
    // code
    result
```
### Built-in Functions
Utilize built-in functions like sma(source, length), ema(source, length), rsi(source, length), etc.

## Plotting and Visualization
### Plotting Data
Use plot to visualize data on the chart.

```pine
plot(sma(close, 14))
```
Use plotshape or plotarrow for visualizing conditions.

```pine
plotshape(series=cross(close, sma(close, 14)), location=location.belowbar, color=color.green, style=shape.triangleup)
```
## Strategies
For strategies, define entry, exit, and trade management.

```pine
strategy.entry("Long", strategy.long, when=longCondition)
strategy.exit("Exit Long", "Long", profit=targetProfit, loss=stopLoss)
```
## Inputs and Parameters
### Input Parameters
Allow script customization without altering the code.

```pine
length = input(14, "MA Length")
src = input(close, "Source")
```
## Debugging and Comments
### Comments
Use comments to explain sections of your script or to disable code.

```pine
// This is a single-line comment
/*
This is a
multi-line comment
*/
```
## Debugging
For debugging, use visual elements like label.new or line.new.

## Tips
- Avoid Repainting: Be aware of repainting, especially in strategies. Historical data in backtesting is not predictive.
- Versioning: Always specify the Pine Script version for compatibility and future reference.

This cheat sheet offers a foundational overview for getting started with Pine Script v5. For in-depth exploration, refer to the official TradingView Pine Script documentation.
