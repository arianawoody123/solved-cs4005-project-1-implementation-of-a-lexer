Download Link: https://assignmentchef.com/product/solved-cs4005-project-1-implementation-of-a-lexer
<br>
<ol>

 <li><strong>Problem: </strong></li>

</ol>

In this assignment you are requested to use the tool ANTLR to write a scanner for a small language Cactus. The language Cactus contains the following categories of token types:




<ol>

 <li>An <em>identifier</em> is a sequence of letters and digits; the first character must be a letter. The underscore ‘_’ counts as a letter. All identifiers are returned as a single token type.</li>

 <li>The following identifiers are reserved for use as <em>keywords</em>, and may not be used otherwise:</li>

</ol>

else fi if int main return while read write Each keyword is returned as a distinct token type.

<ol start="3">

 <li>An <em>integer constant</em> consists of a sequence of digits. All integer constants are returned as a single token type.</li>

 <li><em>Operators</em> include</li>

</ol>

+ – * / % == != &gt; &gt;= &lt; &lt;= &amp;&amp; || ! = ( ) { } ; Each operator is returned as a distinct token type.

<ol start="5">

 <li><em>Blanks</em>, <em>tabs</em>, and <em>newlines</em> are ignored except as they serve to separate tokens.</li>

 <li><em>Comments</em> are ignored except as they serve to separate tokens. The characters /* introduces a comment, which terminates with the characters */. Comments do not nest.</li>

</ol>




You can follow the following steps:

<ol>

 <li>Edit a grammar Cactus.g4 that contains the regular expressions for each of the token types as follows.</li>

</ol>




// The grammar for Cactus language grammar Cactus;




// Parser rules

token : (ELSE | … | ID | CONST | ADD | … )*




// lexer rules

ELSE : ‘else’

…

ID : …

CONST : …

ADD : ‘+’

…

WHITESPACE : …

COMMENT : …




<ol start="2">

 <li>Use the ANTLR tool to generate the scanner and parser java code.</li>

</ol>




$antlr4 Cactus.g4




<ol start="3">

 <li>Compile the generated java code.</li>

</ol>




$javac Cactus*.java




<ol start="4">

 <li>Use the ANTLR tool to execute the scanner and parser.</li>

</ol>




$grun Cactus token -tree




If the input is as follows:




/* A program to sum 1 to n */ main()

{ int n; int s; int i;




read n;

if ( n &lt; 1 ) {

write -1;       return;    } else {       s = 0;

} fi    i = 1;     while ( i &lt;= n) {       s = s + i;       i = i + 1;

} write s;

return;

}




The output should be




(token main ( ) { int n ; int s ; int i ; read n ; if ( n &lt; 1 ) { write – 1 ; return ; } else { s = 0 ; } fi i = 1 ; while ( i &lt;= n ) { s = s + i ; i = i + 1 ; } write s ; return ; })




<ol start="2">

 <li><strong>Handing in your program:</strong></li>

</ol>

To turn in the assignment, upload a compressed file proj1 containing Cactus.g4, Cactus.tokens, Cactus*.java, and Cactus*.class to eCourse2 site.




<ol start="4">

 <li><strong>Grading </strong></li>

</ol>

The grading is based on the correctness of your program. The correctness will be tested by a number of test cases designed by the instructor and teaching assistants.