# Code Context Highlighting Sample

I need to see the set of classes that GitHub/Markdown/Jekyll uses to
highlight code.  To that end, this page contains several code sections
in different languages to see how the text is categorized.

Let's first try some c code:
~~~c
/**************************
* This is a block comment.
**************************/

const char global_message[] = "This is a multiline
text string.  How does it render?";

int bdate = { 1960, 4, 21 };

int main(int argc, char **argv)
{
   for (int i=0; i<argc; ++i)
   {
      printf("%d: %s\n", i, *argv[i]);
   }

   switch(argc)
   {
   case 1: printf("First case.\n"); break;
   case 2: printf("Second case.\n"); break;
   default: printf("Default case for %d.\n", argc); break; 
   }
}
~~~

And now some shell script.
~~~sh
#!/bin/bash

if [ $# -gt 0 ]; then
   name="$1"
   echo "Hi, $name"
fi
~~~


