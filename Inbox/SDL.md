## SDL_MAIN_USE_CALLBACKS

```c
#define SDL_MAIN_USE_CALLBACKS 1
```

If `SDL_MAIN_USE_CALLBACKS` is defined, SDL expects the application to provide `SDL_AppInit`, `SDL_AppEvent`, `SDL_AppIterate`, and `SDL_AppQuit`. The application should not define a `main` function if `SDL_MAIN_USE_CALLBACKS` is defined.

https://wiki.libsdl.org/SDL3/SDL_MAIN_USE_CALLBACKS