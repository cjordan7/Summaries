
# Useful Commands from different modes of Emacs

## Elisp
* Comment
  ```
  ;; This is an elisp comment
  ```
  
* Set value
  
  ```
  (setq value "test")
  
  ;; Multiple assignment
  (setq v "a" v2 2 v3 42)
  ```
  
* Insert where the cursor is

  ```
  (insert "Hi" "Hi2" value)
  ```
  
  would give "Hi Hi2 test"
* Function definition

  ```
  (defun name (arg1 arg2 arg3 arg4 ...)
      "Optional documentation"
      (interactive argument-passing-info)     ;; optional
      body
  )
  ```
  
  * call the function with arguments
  
  ```
  (name arg1 arg2 arg3 ...)
  ```

## General
* Evaluate *Elisp* code
  
  ```
  C-x C-e: eval-last-sexp
  ```

* Describe all colors from current buffer

    ```
    M-x list-faces-display
    ```
  
* Find and replace query
    
    ```
    M-%
    ```
    
    then click `y` for replace, or `n` don't replace
* Describe the different modes of the current buffer

    ```
    describe-mode
    ```

* Describe the corresponding shortcut (keys)

    ```
    describe-key
    ``` 

* Delete trailing whitespaces in current selected region

    ```
    delete-trailing-whitespaces
    ```

## Yas
* Create a new snippet

    ```
    C-c & C-n : yas-new-snippet
    ```

* Insert a snippet at point

    ```
    C-c & C-s : yas-insert-snippet
    ```

* Insert file

    ```
    C-c & C-v : yas-visit-snippet-file
    ```


## Dumb-jump
* 

## Helm
* Choose file

    ```
    C-x C-f : helm-find-files
    ```

## Projectile
* Find a directory in the project

    ```
    C-p d : projectile-find-dir
    ```
    
* Find a file in the project

    ```
    C-p f : projectile-find-file
    ```

* Crazy shells...

    ```
    C-p x e : projectile-run-eshell
    ```

    ```
    C-p x i : projectile-run-ielm
    ```

    ```
    C-p x s : projectile-run-shell
    ```

    ```
    C-p x t : projectile-run-term
    ```

## Company-irony
Command to install a server on macOS

    cmake -DCMAKE_INSTALL_PREFIX\=/Users/$USER/.emacs.d/irony/ -DCMAKE_INSTALL_RPATH_USE_LINK_PATH=ON -DCMAKE_PREFIX_PATH=/usr/local/opt/llvm -DCMAKE_CXX_COMPILER=/usr/local/opt/llvm/bin/clang++ -DCMAKE_C_COMPILER=/usr/local/opt/llvm/bin/clang -DLIBCLANG_INCLUDE_DIR=/usr/local/opt/llvm/include -DLIBCLANG_LIBRARY=/usr/local/opt/llvm/lib/libclang.dylib  /Users/$USER/.emacs.d/elpa/irony-20200130.849/server && cmake --build . --use-stderr --config Release --target install

## Markdown
* Personalized command, defined by snippet
  * Create new week title of ## and comment before
  
  ```
  week
  ``` 
  
  in week snippet with `n` as parameters

   * image creation:

   ```
   im
   ```
   
   image are defined as 
   
   ```
   <img src="images/week${1:week number}/week$1-${2:N}.png" width="400">
   ```

    * Sub title creation with

    ```
    par
    ``` 
    
    title is the parameter

## Org
* 
