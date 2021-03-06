#Python to C++ Code Converter

The main intention in building this project is to achieve the ease of coding of
python and execution speed of C/C++. Out of many ways to do so, one of the ways
is to convert the code written in Python to C++. And this seems achievable. Why
i think so is because we have already seen something like this happen before.
All of us know that even C/C++ code is converted to the Assembly code by the
compiler. Also, C is a Turing Complete language, and what we want to achieve
might be tough but is computationally possible. Something similar exists but is
not meant to convert Python to C++. HipHop PHP coverts PHP to C++, developed at
Facebook.

#How to Approach the Project?

The approach i am taking in developing this project is to first identify the
elements of a programing language that are language independent. And i have
found that in any programing language, literals and identifiers are language
independent. The only thing which is language dependent are the terminals,
syntax and semantics of the language. So the thought is to first create an
intermediate state of the source code, which contains the literals, identifiers,
flow of the program and some of the computational standards which coluld be fond
in almost every programing languages like conditionals, iterators, procedures,
etc. Hence when the intermediate stage is achieved, it is processed sequentially
and is used to fill in the missing place-holders of the output source code.
Obviously, all the statements of python cannot be directly converted to C++
statements. So we need to implement some of the functionality of Python in C++
and use it as a module in C++ output source code.

#Implementation Details:

1. First the Python code is lexically parsed to identify the atomic parts that
 make the python code. These will be statements, functions, conditionals,
 itearatives, etc.
2. Then the identifiers and literals are extracted from it and are stored in a
 file marking with them the type of statement.
3. Seperate atomic parts could be placed in seperate files.
4. A master file is prepared which contains the flow of the code and contains
 pointers to all the atomic parts of the code.
5. Hence traversing over the master file, the output code is generated.

Consider the whole process as a jigsaw puzzle with few missing pieces. The
missing pieces are the identifiers and literals and we place them into the
output source code to complete it.

#Objects to be used in this project:

##INTERMEDIATE STATE:

1. Block: Similar to the Python and C++ block. It can contain within it
 statements, functions, conditionals, iteratives, etc. 
 Exp: If block, for block
2. Block with return: Similar to Block but contains a return value.
 Exp: Function Block
3. Function: It will have a:
  1. Return Type
  2. Arguments
  3. Function Identifier
  4. Block/Block with return
4. Iterative:
  1. for:
  range/iterator
  2. while:
  Condition
  Common Things: block
5. Conditional: If-Else
  1. Condition
  2. If-Block
  3. Else-Block (Optional)
6. Statements:
  1. Arithmetic: a=b+c-d
  2. Declarative: a=10;b=[];c={}
  3. Instructive: print "Hello World"

#Step By Step Development of the Code Parsing Stage:

1. Parse the given python source code to identify terminals, literals and
 identifiers.
2. Analyse the parsed data to identify statements and categorise them.
3. Also generate the intermediate state along side the syntax analysis, which
 shows the flow of the code to be generated.
4. Operate upon the statements one by one and paas these statements to their
 respective functions which shall generate the C/C++ code.
