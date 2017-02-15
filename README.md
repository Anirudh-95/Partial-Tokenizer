Description:
This program allows the user to input a string on the command line, either a floating point number or an integer, which can be in either decimal, hexadeimal, or octal form. The program will then output each of these "tokens" along with the type of number it is. 

Algorithm:
After a string is entered throught the command line, it is broken up into smaller strings with no whitespaces in between. It is checked to make sure its not empty. Then it is sent to the helper method that searches for any character that may not be a part of one of the token types (decimal, hexadecimal, octal, and float). The specific characters it lets enter the string are ".", "+", "- ", "x", "X", upper and lower cases letters from a-f, and all digits 0-9. If the first character is not a number, an error is printed on the screen, but the program is allowed to continue. If an escape character that was not in the list above is in the string, the program outputs the hexadeciaml value of that character, returns the string that was created before the escape character to the main, then continues to serach the rest of the string for escape characters and tokens. Any string returned from the helper function is passed into TKCreate, and is entered into a token struct with two fields, type and token. The string type is properly identified as either decimal, hexadecimal, octal, float, or mal based off of the Finite State Machine given as part of the assignment, and the token is the string. All errors involving the characters that are part of the token types (specific characters listed above) result in an error of type mal and is not considered an escape character error. A token struct is then returned to the main and the token and type is printed. After being printed, the memory is freed using the TKDestroy function. The TKGetNextToken function was not used because the program itereates through the strings given in the command line with the main method and helper function. The "e" and "x" characters can be used as both uppercase and lower case characters in their respective uses. The program runs as closesly to the FSM as possible, so if the string enters the fsm (by starting with a 0-9) and contains characters that are valid in any of the token types, it will either be properly identified as a type of token or be considered type mal. If the string begins with a 0-9 digit then has an escape character, then the escape character will be output and whatever token that is created from the one pass rule is returned. If escape characeter(s) are encountered in the helper fucntion, the first one will be always printed before the string that it comes after. Hoewever, any additional escape characters will be printed after the string.
