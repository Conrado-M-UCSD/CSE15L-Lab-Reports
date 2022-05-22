[Return to Homepage](https://Conrado-M-UCSD.github.io/CSE15L-Lab-Reports/index.html)
# Lab Report 4: Testing Implementations of MarkdownParse

## Running snippets

I will test my implementation of MarkdownParse as well as the implementation my group reviewed as part of Lab 7. Here are the results! 

My implemention can be found [here](https://github.com/Conrado-M-UCSD/markdown-parser).

The implementation that I tested in lab 7 can be found [here](https://github.com/anhthony/markdown-parser).

__Test snippet 1:__ 

`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)

__Test Snippet 2:__

[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)


__Test Snippet 3:__

[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text
