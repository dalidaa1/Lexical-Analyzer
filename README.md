# Lexical-Analyzer
#Simple scanner (lexer) implemented in Python for CS.211 course assignment.

string = 'the beautiful white moon = 5 + 2'
keywords = ['the', 'white']
operators = ['=', '+', '-']
whitespace = ' '

lexeme = ''
for i, char in enumerate(string):
    if char != whitespace and char not in operators:
        lexeme += char
    elif char in operators:
        if lexeme:
            if lexeme in keywords:
                print(f"KEYWORD: {lexeme}")
            else:
                print(f"IDENTIFIER: {lexeme}")
            lexeme = ''
        print(f"OPERATOR: {char}")
    else:
        if lexeme:
            if lexeme in keywords:
                print(f"KEYWORD: {lexeme}")
            elif lexeme.isdigit():
                print(f"NUMBER: {lexeme}")
            else:
                print(f"IDENTIFIER: {lexeme}")
            lexeme = ''

# Print last lexeme if exists
if lexeme:
    if lexeme in keywords:
        print(f"KEYWORD: {lexeme}")
    elif lexeme.isdigit():
        print(f"NUMBER: {lexeme}")
    else:
        print(f"IDENTIFIER: {lexeme}")
