REGULAR EXPRESSION

import re

5-letter string: "[0-9]"
Regular Expression: r"[0-9]" 
                    (matches 10 1-letter strings)
                    r"[a-z]"

re.findall(r"[0-9]", "1+2==3")



Maximum Munch Principle
re.findall(r"[0-9]+", "21something1and1776") = ['21', '1', '1776']
                    not ['2', '1', '1', '1', '7', '7', '6']

FINITE STATE MACHINES

    Suppose we want r"[0-9]+%" 30% 99% 2%


    THE QUESTION MARK - Optional (epsilon) operator

    re.findall(r"-?[0-9]+", "1861-1941") = ["1861", "-1941"]
     (the previous thing zero or one time)


MORE REGULAR EXPRESSIONS
    
    THE PLUS + one or more copies
    THE STAR * zero or more copies

    a+ = aa*


        EXERCISE 1:
        # Assign to the variable regexp a Python regular expression that matches
        # lowercase words (a-z) or singly-hyphenated lowercase words.

        # Hint: It may not be possible to get correctly - do your best!

        Possible solution: regexp = r"[a-z]+-?[a-z]+"
         - Doesn't work with single letters like "a" or "i"
         - If we change to r"[a-z]*-?[a-z]+" then mistakenly we accpet "-a" 
         - r"[a-z]+-?[a-z]*" doesn't work either, coz of "a-"


        EXERCISE 2:
        # Assign to the variable regexp a Python regular expression that matches single-
        # argument mathematical functions.

        # The function name is a lowercase word (a-z), the function argument must be a
        # number (0-9), and there may optionally be spaces before and/or after the
        # argument.

    THE ESCAPE \(\) Hint: You may need to escape the ( and ).

        import re

        regexp = r"[a-z]+\([ ]*[0-9]+[ ]*\)"


    THE DOT . any character (except new line)
    re.findall(r"[0-9].[0-9]", "1a1 222 cc3") = 
    ['1a1', '222']
    
    THE HAT (^ inside []) this means not or set complement 
    re.findall(r"[0-9][^ab]", "1a1 222 cc3") = ['1 ', '22', '2']
     
