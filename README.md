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