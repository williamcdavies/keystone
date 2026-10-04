## SDL_MAIN_USE_CALLBACKS

```c
#define SDL_MAIN_USE_CALLBACKS 1
```

If `SDL_MAIN_USE_CALLBACKS` is defined, SDL expects the application to provide `SDL_AppInit`, `SDL_AppEvent`, `SDL_AppIterate`, and `SDL_AppQuit`. The application should not define a `main` function if `SDL_MAIN_USE_CALLBACKS` is defined.

`SDL_AppInit`, `SDL_AppEvent`, `SDL_AppIterate`, and `SDL_AppQuit` are defined in `SDL_main.h` with the `extern` keyword. i.e., these functions must be defined in another file. This other file will typically be main.

`SDL_AppResult` can be one of `SDL_APP_SUCCESS`, `SDL_APP_FAILURE`, or `SDL_APP_CONTINUE`. `SDL_APP_CONTINUE` is primarily returned by `SDL_AppEvent` and `SDL_AppIterate`.

## Initialisation
All `SDL` programs need to initialise the SDL library before it can be used. This is done via `SDL_Init`. e.g.

```

```


https://wiki.libsdl.org/SDL3/SDL_MAIN_USE_CALLBACKS