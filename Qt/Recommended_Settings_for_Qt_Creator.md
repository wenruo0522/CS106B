### Recommended Settings for Qt Creator

***

- Below are our suggested configuration settings for Qt Creator. You are not required to adopt these settings, but we recommend them for a more pleasant experience.

- Access the preferences/settings for Qt Creator from the top menu bar:
  - on Mac, menu item is Qt Creator -> Preferences…
  - on Windows, menu item is Edit -> Preferences…
  - on Linux, menu item is Tools -> Options…

- **Build & Run settings**

  We recommend checking the following boxes:

  - **Save all files before build**

    This saves your code files before you compile or run your project.

  - **Compile Output: Open pane when building**

    Display information about the compilation process when your project is being built.

  - **Application Output: Open pane on output when running always**

    Display your program's output in a pane at the bottom of window. Normally you can see the output in the popup graphical console and don't need this bottom pane, but if your window crashes, the bottom output can be helpful to figure out what went wrong. **Note: In newer versions of Qt this option is presented as a dropdown menu instead of a checkbox.**

  - **Application Output: Clear old output on a new run**

    This clears out previous output from the output pane.

- **Debugger settings**

  - **Debugger font size follows main editor**

    This will make your debugger font size grow if the main text editor font size is enlarged.

  - **Switch to previous mode on debugger exit**

    This closes unneeded debugger panes when the debugger is no longer running.

- **Turn off analyzer**

  Qt Creator uses a code analyzer to check your code for stylistic errors and conformance to industry standard "best practices". While some of this guidance might be valuable, the default settings are much too nitpicky and the error messages are alarmist and often obtuse. We think students are best served by **disabling this feature** altogether to eliminate the unhelpful chatter.

  The analyzer is controlled by two preferences, one for "clangd" and another for "clazy".

  - Search for "clangd" on the Preferences pane. It should bring up the "C++ -> clangd" pane where there is a checkbox labeled "**Use clangd**". Make sure this checkbox is **unchecked**.
  - Search for "clazy" on the Preferences pane. It should bring up the "Analyzer -> Clang Tools" pane where there is a checkbox labeled "**Analyze open files**". Make sure this checkbox is **unchecked**.

  Click "Ok" to save your changes, the analyzer is now off. Your code will still get proper highlights for build warnings and errors, but this removes all the squawking about stylistic quibbles.



