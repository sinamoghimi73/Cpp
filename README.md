# C/C++
C/C++ codes !

In this repository I am going to write my C++ codes using text editor (for now I choose Sublime as my text editor), Compile, build and run in Command-Line(macOS Terminal)!

# In Command-Line!

***Notice: If you do not feel to read this story, just skip to the end!***

To run a cpp file in Command-Line, we need to enter the command below:

`
g++ -Wall -std=<C++_Standard_you_prefer> <SourceFile.cpp>
`

- `-Wall` will turn on all warnings!

C++ Standards are as follows:
- `C++98` for year ***1998***,
- `C++03` for year ***2003***,

  and modern C++:
  - `C++11` for year ***2011***,
  - `C++14` for year ***2014***,
  - `C++17` for year ***2017***
  and
  - `C++20` for year ***2020***!

The standard I use is `C++17`. Let's see what our command looks like? for a sourcefile `main.cpp`!

`
g++ -Wall -std=c++17 main.cpp
`

To run our code we need to make an executable file as well. Let's assume its name is `run`.

The command will be like:

`
g++ -Wall -std=c++17 main.cpp -o run
`

It makes an executable file called `run`. Then you can run your code by writing `./run` .
It might be confusing so let's go a little further and make an alias for it! In order to generalize it for any file names, we need to alias only the first part!

`echo 'alias cpp="g++ -Wall -std=c++17"' >> ~/.bashrc`, or `~/.zshrc`for those who use `ZSH`. Our command would be like: `cpp main.cpp`. But we need it to make an executable file as well!!!

***`alias` might not be able to do that!***

***We need to turn it into a function. How?***

`echo 'gpp (){g++ -Wall -std=c++17 "$@" -o run;}' >> ~/.bashrc`

Now, it can Compile the source file and make an executable file as well. Yet, let's go a little further and tell it to show you the result! We should add `&& ./run` to the end of our function.

`echo 'gpp (){g++ -Wall -std=c++17 "$@" -o run && ./run;}' >> ~/.bashrc`

well, until now we made executable file, you might find another file named `a.out`.

we might benefit cleaning our object files. In this case we should add a little exra commands to perfect our compile and build process!

`echo 'gpp (){rm -rf run a.out && g++ -Wall -std=c++17 "$@" -o run && ./run;}' >> ~/.bashrc`

Now, write:

`
gpp main.cpp
`

***This time, it is much like running a python code in Command-Line!***
