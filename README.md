JS Auto Semicolon
===========

This Sublime Text 3 macro automatically adds a semicolon to the end of the line when you're inside parentheses or brackets.

## Main Use Case
You're putting in an anonymous (or named, since that's good too) function as an argument. Sublime helpfully closes your brackets, but then you have to remember to key around and add the semicolon at the end.

**Another use case**

Would also work if your argument is an object or an array, basically any block inside parentheses. See the [logic](#macro-logic) section below for details on what the macro is doing.

*Assume the cursor is at the pipe*

```js
myObject.task('doSomething', function() {|})
```
Then pressing **super + ;** will result in

```js
myObject.task('doSomething', function() {
  //cursor here
});
```

## Installing

### Without Git
Download the zip file of the repo, extract it, then continue with step 2 below.

### With Git
1. Clone the repo wherever you want using `git clone https://github.com/jdhines/Sublime-JS-Auto-Semicolon.git`

2. Go into the directory just created, and copy `javascript-function-semicolon.sublime-macro` into your Packages/User directory. If you do not know where that is, under Preferences in Sublime, choose "Browse packages..."

3. Then, in Sublime, go to Preferences --> Key Bindings - User, and add in the content of the `js-auto-semicolon.sublime-keymap` file. *Don't forget your commas (either before or after depending on where in your keymap file you put this)!*

That's it, you should be able to use it without restarting Sublime.

### Troubleshooting
If the macro doesn't work, check the User Key Bindings file for the binding code, and make sure that the `args.file` argument is pointing to the right location depending on your system and where you put the macro file.

## Macro Logic
It's a pretty simple macro, but it just goes to the end of the line, inserts a semicolon, then backs up three spaces, then inserts a new line.