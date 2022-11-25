```
 find . -iname "*.sh" -exec sh -c 'grep IP {} >/dev/null && dirname {} && basename {} && grep IP {}' \;
```
