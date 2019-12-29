# console-color-cpp

A small single-header library for outputting colored text to the console. 

> *Only Windows is currently supported!*


## Using

To connect, simply include the header file in your project:

```cpp
#include "console-color.hpp"
```

To output text, a standard output stream is used. For unification the operator << is used.

The simplest example looks like this:

```cpp
#include "console-color.hpp"

using namespace cs;
using namespace std;

int main()
{
    cout << (("Hello World!"_cs << color(0xF2F61D)) << endl;
    return 0;
}
```

It is important that everything that you output to the standard stream must be wrapped in brackets!

```cpp
// wrong
cout << ""_cs << color();

// good
cout << (""_cs << color());
```

You can output string one by one. Each expression of the form `"" _cs << color()` must be wrapped in brackets:

```cpp 
cout << ((""_cs << color()) << (""_cs << color())) << endl;
```

An expression of the form `"" _cs << color()` can be written as `"" _cs.use(color())`.

Also from any string you can make a string with color:

```cpp
color_string str("Hi!");

// or

string s_string("Other string");
color_string str(s_string);
```

Before outputting a string, you can give it the color with which it will be displayed:

```cpp
str << color(255, 0, 0);

// or

str.use(color(255, 0, 0));
```

Colors can be set using either a 32 bit number (HEX) or in RGB format.

## License

[MIT](https://mit-license.org/)