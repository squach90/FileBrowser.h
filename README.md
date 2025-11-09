# FileBrowser.h

FileBrowser.h is a lightweight C library to navigate and select files directly from the terminal.

#### Install

Simply put `file_browser.h` in your `includes` folder.
*Yeah it's simple like that*

#### How to use ?

To use `file_browser.h` in a **C** file you need to adds:

```c
#include "../includes/file_browser.h" // If needed you can adjust the path
```

Then you can call `select_file()` to launch the file browser:
```c
char *file_path = select_file(); // Launch file_browser.h

if (file_path) {
    printf("Selected File : %s\n", file_path);
    free(file_path); // free the memory
} else {
    printf("No file selected.\n");
}
```

### Exemple
```c
#include <stdio.h>
#include "file_browser.h"

int main(void) {
    char *file_path = select_file(); // Launch file_browser.h

    if (file_path) {
        printf("Selected File : %s\n", file_path);
        free(file_path); // free the memory
    } else {
        printf("No file selected.\n");
    }

    return 0;
}
```

##### Notes
- Works in terminal using arrow keys to navigate and Enter to select.
- Only supports Unix-like systems (Linux/macOS) because of `termios` and `unistd.h`.


### Dependencies

- **Standard C** – `stdio.h`, `stdlib.h`, `string.h`
- **POSIX / Terminal** – `unistd.h`, `dirent.h`, `termios.h`, `sys/stat.h`, `limits.h`

> Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.