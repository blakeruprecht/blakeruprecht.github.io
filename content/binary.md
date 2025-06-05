---
title: Binary
description: '"Binary logic, boolean logic, is the foundation of all modern computing."'
---
At it's fundamental level, a [computer](/computers) is basically just adding and subtracting binary numbers using a trick of computer wiring called digital logic, where you use configurations of circuits to represent basic math equations. All of the lowest-level code is written in binary instructions to these math gates, and the results are "interpreted" by us humans to represent math equations.

A binary question is a yes/no question that could be answered with the symbols:
- **1** = Yes, true, on, light.
- **0** = No, false, off, dark.

A lightbulb with two wires and a battery:
- Is **on** when the circuit is complete and lightbulb is *lit*.
- Is **off** when the circuit is broken (e.g. a switch is flipped "off").

A lightbulb, two wires, a battery, and a *switch*:
- **Negation**: y = NOT(X) = -x (only has one input)

A lightbulb, many wires, a battery, and *two switches in series*:
- **Conjuction**: y = AND(x1,x2) = x1 AND x2 = x1 * x2 

A lightbulb, many wires, a battery, and *two switches in parallel*:
- **Disjuction**: y = OR(X1, X2) = x1 OR x2 = x1 + x2

Binary truth table for and/or
- (x, y, **AND, OR**)
- (0, 0, **0, 0**) both x and y are off, so AND and OR both produce off
- (1, 0, **0, 1**) just x is on, y is off, so AND is off and OR is on
- (0, 1, **0, 1**) just y is on, x is off this time, AND off, OR on
- (1, 1, **1, 1**) x and y are both on, so AND and OR are on

## Related
- [computing](computing.md)
- [computers](/computers)