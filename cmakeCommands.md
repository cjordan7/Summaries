
*** 
# Useful CMake commands

# 
## Overview
* CMake is a tool that allows to compile and create packages for source code
* CMake commands are written in a file called CMakeLists.txt
* Usually build file are put in a directory called `build`, but it could be anything
* The following commands are used to build a project using cmake:

  ```
  cd path/to/projectDirectory/
  mkdir build
  cd build/
  cmake ..
  make
  ```
# 
## Commands
* This is a comment

    `# cmake see this as a comment`

* Simple hello world cmake

    `cmake_minimum_required(VERSION 3.18.2)
   project (hello)
   add_executable(app HelloWorld.cpp)`

* We require C++ 17

    ```
    set(CMAKE_CXX_STANDARD 17)
    set(CMAKE_CXX_STANDARD_REQUIRED ON)
    set(CMAKE_CXX_EXTENSIONS OFF)
    ```
    
* We set the minimum version required for *cmake* by typing:

    `cmake_minimum_required(VERSION 3.18.2)`

    * we can throw an error if the version is below
    
    `cmake_minimum_required(VERSION 3.18.2 FATAL_ERROR)`

* We define the name of the project with:

    `project (cmake project)`

  * Enable C++
  
    `project(name CXX)`
    
* To add a directory, we write:

  `add_directory(src)`
  
* We can specify the include directory, in clang it is the famous *-I* command

  `include_directory(include)`
  
* We can manually add the sources of the files

  `set(SRC src/one.cpp src/two.cpp)`
  
  * from the documentation
  
  `set(<variable> <value>... [PARENT_SCOPE])`
  
  * Other examples:
  
  `set(Test "Some Text")`
  
  `set(TestWithVariable "A variable coming from test: ${Test}")`
  
* Use `string` to create string

  `string(APPEND Test "")`
  
* The file allows for wildcard additions:

  `file(GLOB SRC "src/*.cpp")`
  
* Like any programming language, if, else are defined:

  ```
  if(condition)
      # ...
  elseif(conditionTwo)
      # ...
  else
      # ...
  ```

* Logic operations:

  ```
  if((TRUE OR FALSE) AND (TRUE OR TRUE))
      message("Don't display!")
  endif()
  ```
  
* Defining loops:

  ```
  foreach(loopVar arg1 arg2 ...)
      COMMAND1(ARGS ...)
      COMMAND2(ARGS ...)
  endforeach(loopVar)
  ```
  
* Adding the executable

  ```
  ${projectName} refers to Learn_CMake 
   add_executable(${projectName} ${src})
   ```
   
* To link libraries

  `target_link_libraries(${projectName} ${libraries} m)`
  
* To recognize `UNIX` or `UNIX`-Like systems, we use

  ```
  if(UNIX)
   endif(UNIX)
  ```
  
  * To recognize, *Darwin*/*Apple*, we use
  
  ```
   if(APPLE)
   endif(APPLE)
   ```
   
   * or we could use:
   
   ```
   if(${CMAKE_SYSTEM_NAME} MATCHES Darwin)
       # ...
   endif()
    ```

