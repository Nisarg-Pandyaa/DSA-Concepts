# 1L

- Basically it is `1` in `long` format (64-bit space), `not int` (32-bit space). </br> </br>
- When `Two Integers` (32-bit space) multiply then it can exceed `2,147,483,647` (the max value for an int). So when multiplying by `1L`, you trigger `numeric promotion`. </br> </br>
- Java sees a `long multiplied by an int` and promotes the `entire calculation to 64-bit long` math. </br> </br>

- Without `1L` : `int` * `int` -> Result In `int` (can overflow). </br> </br>
- With `1L` : `1L` * `int` * `int` -> Result In `long` (can hold up to 9 x 10^18, which is plenty for 10^14).
