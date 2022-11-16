Not handing erros leads to:
- Insecure code: Crackers often exploit poor error handling to break into software systems.
- Brittle code: Code that's filled with exciting, hard to find bugs.
- Poor structure: If there are errors from your code that are tedious to deal with continually, you have probably a poor interface . Express it so that the errors are less intrusive and their handling is less onerous.

Just as you should check all potential errors in your code, you need to expose all potentially erroneous conditions in your interface. Do not hide them, pretending that your services will always work.