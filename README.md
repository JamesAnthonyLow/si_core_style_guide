# si_core_style_guide

This style guide should be referred to for all future projects.

The following is subject to alteration, additions, and certainly debates.

##under_scores or camelCase
We have not yet decided under_scores or camelCase but what is important is that you choose one and stay consistent.  Here are some guidelines for either:

###under_scores
James prefers this style for readability.  The under_scores provide a stronger delimiter between words than the capitalization and it arguable just looks better.

When you write in under_score style be sure to keep everything in lower_case, the only time you would use UPPER_CASE is for macros, and things like globals and constants.  Keep everything uniform and considerUPPER_CASE for emphasis only.

Example:

```c
void display_hello_world(void);
```

###camelCase
This is the preferred style for the majority of SiCoreans.

When you write camelCase you leave the first word lowercase and capitalise the first letter of the remaining words, for example:

```c
void displayHelloWorld(void);
```

When you write something like a global, constant, or macros you can capitalise the first letter as well.  Also there is some flexibility to switch back to UNDER_SCORE if you want to write a macro and capitalize all letters.

```c
#define FOO_HEADER

const int Foo;
```

##Headers

Important to use preprocessor conditionals in ALL header files to prevent duplicate inclusions. When defining the placeholder macro prepend an underscore.


```c
#ifndef _MY_HEADER
#define _MY_HEADER

//header code goes here.

#endif
```

##Variables (please add types as you use them and try to follow the pattern)

The following should be prefixed to the following variable types to allow the reader to easily determine what type they are dealing with.

Data Type | Prefix |under_score ex.|camelCase ex.
----------|--------|---------------|-------------
char|ch|```char ch_foo```|```char chFoo```
unsigned char|uch|```unsigned char uch_foo```|```unsigned char uch_foo```
int|n|```int n_foo```|```int nFoo```
unsigned int|un|```unsigned int un_foo```|```unsigned int unFoo```
short|sh|```short sh_foo```|```short shFoo```
unsigned short|ush|```unsigned short ush_foo```|```unsigned short ushFoo```
long|l|```long l_foo```|```long lFoo```
unsigned long|ul|```unsigned long ul_foo```|```unsigned long ulFoo```
unsigned long long|ull|```unsigned long long ull_foo```|```unsigned long long ull_foo```

In addition all pointers should be suffixed with "ptr" like so:

```c
//under_score
unsigned long long * ull_foo_ptr;

//camelCase
unsigned long long * ullFooPtr;
```
####Structs

All structs should be defined with a typedef that allows declaration without the 'struct' keyword.  Typedef also allows multiple names for the same struct but PLEASE DON'T DO THIS, one name per struct please!

Also the name of the struct should be the same as the typedef'd name and all structs should have both always even if the struct name is not used.

```c
struct foo_bar_baz {
  //```
}foo_bar_baz;
```
The naming convention for declaration is to prefix the abbreviated initials of the struct name:

```c
foo_bar_baz fbb_foo;
```

