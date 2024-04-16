# Env variable loading bug reproduction

This works from the workspace root
```
nx-examples % npx nx run env-printer:print

> nx run env-printer:print

ENV_PRINTER_LOCAL_ENV=hello
ENV_PRINTER_ROOT_ENV=hola

————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————

 NX   Successfully ran target print for project env-printer (336ms)

```

but if you cd into `apps/` it does not
```
nx-examples % cd apps 
apps % npx nx run env-printer:print

> nx run env-printer:print

Warning: command "env | grep ENV_PRINTER_" exited with non-zero status code
————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————————

 NX   Ran target print for project env-printer (108ms)

   ✖  1/1 failed
   ✔  0/1 succeeded [0 read from cache]
```
