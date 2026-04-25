import ply.lex as lex
tokens = (
    'KEYWORD', 'STRING', 'FLOAT', 'INT', 'OPERATOR', 'ID',
    'LPAREN', 'RPAREN', 'SEMI', 'LBRACE', 'RBRACE', 'DOT'
)
keywords = {
    'if', 'else', 'for', 'while', 'int', 'float', 'void',
    'char', 'double', 'break', 'do'
}
t_STRING   = r'\".*?\"'
t_FLOAT    = r'\d+\.\d+'
t_INT      = r'\d+'
t_OPERATOR = r'\+|-|\*|/|=|==|<=|>=|<|>'
t_LPAREN   = r'\('
t_RPAREN   = r'\)'
t_SEMI     = r'[;:,]'
t_LBRACE   = r'\{'
t_RBRACE   = r'\}'
t_DOT      = r'\.'
t_ignore   = ' \t'
def t_ID(t):
    r'[a-zA-Z_][a-zA-Z0-9_]*'
    if t.value in keywords:
        t.type = 'KEYWORD'
    return t
def t_newline(t):
    r'\n+'
    t.lexer.lineno += len(t.value)
def t_error(t):
    print("Illegal character:", t.value[0])
    t.lexer.skip(1)
lexer = lex.lex()
with open("text.cpp") as f:
    lexer.input(f.read())
for token in lexer:
    print(token)