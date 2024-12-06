# VHDL Integer Overflow Bug

This repository demonstrates a subtle integer overflow bug in VHDL.  The `buggy_counter` entity uses an integer signal without explicit overflow handling. When the counter reaches its maximum value (15), it silently wraps around to 0, causing incorrect functionality.  This is a common issue in hardware design when the range of an integer is not properly managed, and standard VHDL simulators may not throw an error, making it difficult to detect.

## Solution

The `fixed_counter` entity demonstrates a solution which uses a `std_logic_vector` instead of an `integer` and explicitly handles overflow.  This solution uses a modulo operation to prevent any out of range values and to create the expected wrap-around behavior.

The repository is intended to illustrate a common error that may not always raise an obvious warning. Thorough testing, code review and careful variable type selection are key to preventing such bugs.