### COMP 3104 - DEVELOPER OPERATION
--VIDJANAGNI JACQUES 

# github Action Statuts Badge
[![CI](https://github.com/jacques758/COMP3104/actions/workflows/ci.yml/badge.svg)](https://github.com/jacques758/COMP3104/actions/workflows/ci.yml)



commit readme.md

#!/bin/sh
COMMIT_MSG_FILE=$1
COMMIT_MSG=$(cat $COMMIT_MSG_FILE)

if ! echo "$COMMIT_MSG" | grep -Eq "^(feat|fix|docs|style|refactor|test|chore): .+"; then
  echo "Commit message must follow the format: <type>: <description>"
  echo "Example: feat: add user authentication"
  exit 1
fi



# pre- push 

#!/bin/sh
echo "Running pre-push hook: Running tests..."
npm test
if [ $? -ne 0 ]; then
  echo "Tests failed! Fix them before pushing."
  exit 1
fi