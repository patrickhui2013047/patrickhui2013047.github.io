---
layout: post
title: An idea of logic simulator
---

---

The project is not finished yet, the content here may be change after update

---

This is a post that used to recoed my idea of a logic simulator. I might not working on it this time, so i make a record of this idea.


## Idea
The simulator works on `LogicUnit` , a `LogicUnit` can have mulitple Input and Output chanel. 
Basic logic gate like AND gate, OR gate, NOT gate, NOR gate, NAND gate will be prebuilted as `LogicUnit`.
Multiple `LogicUnit` can connect into a `LogicNetwork`, also consider as a `LogicUnit`.

To provider initial signal to the system, a core element `SignalSource` which also consider as `LogicUnit` but only have Output chanel.

### Signal I/O
All signal are deliver via `SignalWire`, a wire must start from a Output chanel to a Input chanel. 
A Output chanel can have multiple wire connection, but Input chanel can only have one wire connection.
If a Input chanel is not connected will consider as `NoneSignal` which will consider as `Low` in Digital system, `0` in Analog system.

### Signal system
Only two kind of signals, Digitial and Analog, will implement in this simulator.

Digital signal only repackage a boolean value, and Analog repackage a Integer value to make safe convertion between them.

## Structure
A `LogicUnit` is a Base class that must be implemented by all logic processing element, including source, processing element and output element. 
To define the I/O singal type, interface `ISingalInput<TSignal>` and `ISingalOutput<TSignal>`are requirded to implement.