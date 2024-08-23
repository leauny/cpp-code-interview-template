## Cpp Code Interview Template

### Recommend

1. Set `input/inputx` as the input redirection file of the executable file `x`.
2. Use clang to get more comprehensive undefined behavior alerts.
   - gcc cannot detect out-of-bounds errors unless address-sanitizer is turned on.
3. Try not to turn on address-sanitizer to avoid unnecessary reminders caused by memory leaks when implementing linked list tree related code.
