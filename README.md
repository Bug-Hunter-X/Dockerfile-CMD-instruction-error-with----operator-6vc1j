# Dockerfile CMD Instruction Error

This repository demonstrates a common error when using the `&&` operator within the `CMD` instruction of a Dockerfile. The intention is to execute `pip install` followed by running the main application, but this does not work due to how the shell is handled within the CMD.

## Bug Description
The issue arises because the `&&` operator relies on shell execution, and the CMD instruction doesn't always guarantee a shell environment. Therefore, the second command won't execute if the first command fails.

## Solution
The solution is to use `&&` as part of a shell script executed by the `CMD` instruction.