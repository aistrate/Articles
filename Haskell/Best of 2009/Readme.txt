Best Haskell Papers of 2009
( http://netsuperbrain.com/blog/posts/best-haskell-papers-of-2009 )

As the year closed I reminisced on all the Haskell related papers I read in 2009. Some of them lifted my understanding to exciting new heights, while some others seemed impractical or overly tedious. The thought came upon me to present a list of the best of the best with the hope that these excellent papers might inspire and motivate others as they have me.

Naturally, many will reject such a subjective list. I concede that the list is heavily influenced by my own interests and lack of prerequisite knowledge in some cases. However, I'd argue that it isn't entirely useless. First, I'd expect several of these papers to be well respected by experts in their respective fields. In this way, my list does shadow the objective truth. Second, my rare occupation as a commercial Haskell contractor makes my personal viewpoints of particular interest.


The List

#7 Experience Report: Haskell in the "Real World" - Curt J. Sampson
This paper showcases the decision of a software business to use functional programming without any prior experience with the paradigm. The business's choice of Haskell for a programming language was outlined as well as the benefits they enjoyed. What struck me in particular were the problems and disadvantages the programming team encountered. It was refreshing to see my own experiences with these issues put so clearly. I point business associates primarily to this paper for an introduction to using Haskell commercially.


#6 Algebra of programming in Agda: Dependent types for relational program derivation - Shin-Cheng Mu et al.
Agda, a dependently typed programming language with a syntax similar to Haskell, is fueling a lot of research this year. After reading many papers such as this one, I can't help but think that the future lies in dependent types.

This paper presents an unorthodox approach to writing programs called relational program derivation. One starts by encoding a proposition, for example "the algorithm x sorts all lists", and then deriving a program that the proposition is true for, like quicksort. The authors created an algebra for encoding these derivations in Agda. By using Agda, the derived programs include a computer verified proof of correctness.

I think it is going to take a while before the programming community, myself included, becomes fully aware of the implications of this paper.


#5 Fun with Type Functions - Oleg Kiselyov, Simon Peyton Jones, Chung-chieh Shan
Reaching a limitation of the type checker is a common cause of ire for Haskell programmers. Type families, a new feature of ghc, removes a sizable amount of these limitations. Superseding an earlier compiler extension, functional dependencies, type families opens up many new areas of generic programming as well. One of the most interesting examples from the paper is a simple type-safe implementation of printf and scanf.

Note that the final version of this paper has not been published yet.


#4 Commercial uses: Going functional on exotic trades - Simon Frankau et al.
Where the #7 spot paper expounds on the implications of switching to Haskell, this paper gives an in depth detail of a commercial domain specific embedded language (DSEL) using Haskell. The explanations within were atypically clear and well referenced. After studying this paper I felt confidant in using Haskell as a host language for DSEL's.

For someone new to DSEL's, this paper is great first read. In my opinion, DSEL's are one of the most lucrative uses of Haskell commercially.


#3 Safe Functional Reactive Programming through Dependent types - Neil Sculthorpe, Henrik Nilsson
This paper contributed two important findings to the field of functional reactive programming (FRP). First, it presented several obvious defects in current FRP implementations. Those who've programed with FRP in any depth are painfully aware of how easy it is to accidentally create programs that loop or leak memory at run-time. Sculthorpe and Nilsson pinpoint the exact cause of these issues.

The second major contribution is an FRP implementation that they proved does not have these problems. The aforementioned proof is computer verified. Can you guess how they did it? If you guessed that they used Agda, you'd be right! Amazing stuff.


#2 Typeclassopedia - Brent Yorgey
Brent Yorgey's Typeclassopedia, published in the Monad.Reader is the most comprehensive tutorial on the basic Haskell type classes (like Monoids, Monads, etc.) thus far. It stands out in both its accessibility to all levels of Haskell developers and its vast coverage. The paper can be used both as a tutorial and a reference. For more in-depth studies, lots of useful references are also included.

This paper is a great contribution to the Haskell community and will surely become a classic.


#1 Finally Tagless, Partially Evaluated - Jacques Carette, Oleg Kiselyov and Chung-Chieh Shan
The essence of this paper is so simple, it bears repeating right here:

varZ env = fst env
varS vp env = vp $ snd env
b b env = b
lam a env = \x -> a (x,env)
app a b env = (a env) (b env)

What you're looking at is a simple implementation of a typed embedded language using Haskell98 as a host for both the language and the type checking. Prior to this paper, embedded language designers took advantage of Haskell98's syntax, but not its type system.

The problem the authors so elegantly solve using Haskell98 was a main motivation behind the complex generalized algebraic data type (GADT) extensions to Haskell. Perhaps this extension isn't necessary after all.

They further describe how to extend this simple interpreter to various efficient compilers and interpreters without modification of the original embedded language. Although the paper primarily uses OCaml, they provide equivalent Haskell code on their website.

I'm looking forward to seeing more complex embedded languages built on the ideas of this paper. It wins first prize for elegance, utility, and cleverness.


Runner-ups

The Arrow Calculus (Technical Report) - Sam Lindley, Philip Wadler, and Jeremy Yallop
This paper describes a new syntax for arrows that more closely resembles the lambda calculus. It remains to be seen if this syntax is easier to use than our current proc syntax.


Push-pull functional reactive programming - Conal Elliott
This paper is a theoretically elegant refactoring of FRP using standard type classes. Had I not directly encountered the subtle, and serious, bugs of this implementation in a commercial setting, it probably would have made the list.


Denotational Semantics - David Schmidt
This is a book written in 1982 that I read last year. It is just as relevant today as it was back then. An excellent exposition of denotational semantics. My programming has substantially changed for the better since that read. It was regretfully disqualified for the medium and date of publication.
