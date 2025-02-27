---
date: 2023-04-24
title: LSTM units incorporate temporal data into NNs
description: '"Long Short-Term Memory (LSTM) units incorporate temporal data into a neural network using a series of four "gates", or math operations on data."'
---
Utilizes temporal data, aka LSTM units can use previous information in their determination of current state.

The first sigmoid is the "forget-gate" $f_t$, the second sigmoid is the "input-gate", $i_t$, the tanh is the "cell-update", $\tilde{C}_t$. Forget-gate will determine how much of the previous cell-state we need to remember, input-gate determines how much of the new cell-state we need to remember, and cell-update gate normalizes the cell-state between [-1,1] because of the tanh. The final sigmoid produces the "output-gate", $O_t$, which is combined with the tanh of the new cell-state to produce the next hidden-state, $h_t$.  

$$C_t = f_t * C_{t-1} + i_t * \tilde{C}_t$$
$$ h_t = O_t * tanh(C_t)$$
Variants include:
- "peephole connections", where $C_{t-1}$ feeds into every "Layer"
- "coupled forget-input gates", where $i_t$ and $f_t$ are linked together
- "Gated Recurrent Unit (GRU)", 