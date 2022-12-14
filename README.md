<a href="http://www.c3-lang.org/"><img style="vertical-align:middle" src=https://i.imgur.com/jtVwIgz.png></a>
# Raylib C3

[C3](http://www.c3-lang.org/) binding for [Raylib](http://www.raylib.com/) a simple and easy-to-use library to learn videogames programming.

*Using Raylib Version 4.5-dev*

## Supported Platforms
- Windows
- MacOS
- Linux

## Covered APIs
- [X] raylib.h
- [X] raymath.h
- [X] easings.h
- [ ] raygui.h 

## Installation - Using C3s build system
**1.** Create a C3 project. (instructions without project.c3p below)

**2.** Clone the Raylib C3 repository.
```bash
https://github.com/Its-Kenta/Raylib-C3.git
```

**3.** Move the *raylib.c3l* folder to your projects *lib*.

**4.** Add the compiled static library or use your system shared (make sure its added to path!) to the desired target inside the *raylib.c3l* folder. Please make sure it matches the binding version.

**4.** Edit your *project.json* file to include the library and the library directory as an example:
```json
{
  "langrev": "1",
  "warnings": [ "no-unused" ],
  "dependency-search-paths": ["lib"],
  "dependencies": [ "raylib" ],
  "authors": [ "YOURNAMEHERE" ],
  "version": "1.0",
  "sources": [ "src/**" ],
  "targets": {
    "PROJECTNAMEHERE": {
      "type": "executable"
    }
  }
}

```

**5.** Add the example code to your main.c3 in *src/YOURPROJECTNAME/main.c3*
```c
import rl;

const int SCREEN_WIDTH = 800;
const int SCREEN_HEIGHT = 450;

fn void main()
{
    rl::initWindow(SCREEN_WIDTH, SCREEN_HEIGHT, "raylib [core] example - basic window");
    defer rl::closeWindow();
    
    rl::setTargetFPS(60);

    while(!rl::windowShouldClose())
    {
        rl::beginDrawing();
        rl::clearBackground(rl::RAYWHITE);
        rl::drawText("Congrats! You created your first window!", 190, 200, 20, rl::LIGHTGRAY);
        rl::endDrawing();
    }
}
```

**6.** Run `c3c run` command to test it out!

**7.** Enjoy your time by learning C3 and create some amazing games!

### Running the example without using C3s build system
Running C3 with external libraries is really easy!

**1.** Create your source code file with the example above.

**2.** Clone the Raylib C3 repository.
```bash
https://github.com/Its-Kenta/Raylib-C3.git
```

**3.** Place your the downloaded *raylib.c3l* preferrably in a folder called "lib", but that is up to you. You will just have to pass the path to it later.

**4.** Run the following command `c3c compile-run --lib raylib --libdir /path/to/the/dir/with/raylibc3l/ main.c3`
This command will compile and run the code and pass the library being imported with it's path.


## Contributing

1. Fork it (<https://github.com/your-github-user/Raylib-C3/fork>)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

If you plan to contribute please make sure you follow the same coding convention to match overall style of this binding (camelCases)

## Contributors

- [Kenta](https://github.com/Its-Kenta) - Creator and maintainer

## Credits
Massive thank you to Christoffer L (C3 Creator) for his help on [C3 Discord community server](https://discord.gg/UWUTtUGJBT) and his vendor library template that Raylib-C3 grew from.
