# Password-Generator
Homework 03

See the live URL here:
https://ryanellingson.github.io/Password-Generator/

# Project description

![Screenshot of password generator](https://github.com/RyanEllingson/Password-Generator/blob/master/assets/images/screenshot.JPG)

The password generator is a web application that uses random number generators to generate a password of a given length using a variety of character types.  The user uses a drop-down menu to select a password length (from 8 to 16 characters), then uses checkboxes to tell the generator whether they would like to include lowercase letters, uppercase letters, numbers, special characters, or any combination thereof.  Then the user clicks the "Generate Password" button.  If no character types are selected, then an error message is printed on the screen.  Otherwise if at least one character type is chosen, a random password is generated and displayed on the screen.  The user than then press the "Copy to Clipboard" button to copy the generated password to the clipboard, from which it may be pasted anywhere the user would like.

An interesting problem was the issue of guaranteeing that at least one example of each selected character type was included in the password.  Naturally, if one were to pick at random 8 characters from a pool containing all 4 character types, one could conceivably get one of the types (numbers for example) zero times.  To avoid this, for each type of character selected one example of that type chosen at random is added to the generated password, then that character type is added to a larger pool of characters which will be selected at random later.  The problem with this is that each time a password is generated, the password would start with the selected character types in the same order (lowercase, then uppercase, then number, etc).  To avoid non-random sequencing, after all the characters for the password are selected, the order of the characters in the password is shuffled.  In order to achieve this, the array containing the characters used for the password is shuffled using the Fisher-Yates algorithm.  After this is done the contents of the array are assigned to a string and displayed on the screen.