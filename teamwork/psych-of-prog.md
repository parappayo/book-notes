
# About

* [The Psychology of Computer Programming](https://geraldmweinberg.com/Site/Programming_Psychology.html)
* by Gerald Weinberg
* Van Nostrand Reinhold, 1971

# Thoughts

Fantastic read, full of truth.

# Take-Aways

* All laws have limits; the limits are typically more important to know than the laws themselves
* Discussions may failure to distinguish between professional and hobby programming
* Programming has a mystique, often not well understood; some programmers encourage this, so execs seek to mitigate the human factors
* Decades long efforts to eliminate programmers from the software business have failed; typically such schemes are invented by programmers
* Once people have a new perspective, they will implement improvements on their own
* "Many college-trained developers approach a project like a one-semester class assignment. They think about it or ignore it for a while, then suddenly start jamming on the keyboard to produce something that will earn a passing grade. Software projects done at universities generally don’t have to be maintainable, usable, or testable by another person."
* These days the goal tends to be value delivered to a customer rather than program efficiency; runtime is typically cheap
* "There probably is, in almost every program, some code which actually does the work that was specified" / "even if we succeed in extracting this kernel of the program, we must not be misled into the illusion that we could have started with this kernel as a specification" / "in most cases, we do not know what we want to do until we have taken a flying leap at programming it" / "writing a program is a process of learning"
* The code that is most frequently read is typically problematic code (a bug may have lead the reader there); if a coder doesn't know what good code looks like, they may fail to lean good practices from reading code; the good get better, the bad get worse

## On Managers

* "Basic principle of the psychology of management: Managers who pay attention to people get good results"
* Bad managers ask for everything; "It’s as if they think all you have to do to manage the New York Yankees is tell every batter to hit a home run, and every pitcher to strike the batter out."
* managers who demand efficient programs often balk at the cost of changes; managers who demand adaptable programs often accept some sacrifice in performance
* "Nobody can seriously have believed that executives could read programs. Why should they? Even programmers do not read programs."

## On Studies

* Past studies focused on programming as an individual activity, not a social activity; devs spend 2/3rd of their time working with others
* study what people do rather than what they think they do; observation tells us what people do, but not what they can do
* historically, studying programmer behaviour was costly because computer systems and the time of computer programmers were both expensive
* knowing what to measure is a problem; a sociologist can use knowledge of their own culture to construct a reasonable questionnaire, but an anthropologist is harder pressed to know what to ask
* "psychology is the psychology of 18-year-old college freshmen" - common population bias in studies

## On Optimizations

* Software optimizations by relaxing the spec may come at the cost of people time, can easily be a net negative; eg. consider a program that is 20% faster but needs to be re-run 50% of the time
* "We have long since passed the point where the typical installation spends more money on programming than it does on production work. This imbalance is even more striking when all the work improperly classified as “production” is put under the proper heading of “debugging.”"
* Whether it is an efficiency gain to consume more memory to save runtime depends on the execution environment and can vary rapidly over time; dynamic load balancing needs to consider that users may be more sensitive to standard deviation than mean execution time
* Evaluating a compiler by the rate of instructions generated per minute may simply reward compilers that produce verbose object code; source code lines processed per minute is similarly misleading
* Typically a compiler that omits 10% of a language's features can compile code 50% faster; which 10% varies by architecture
* "When the programmer includes something that is intended to overcome some limitation of the machine, he rarely marks it explicitly as such"

# Concepts

* Accidental Complexity - not inherent to the problem being solved; can be mitigated with psychological change
* Blame-Analysis - find the person at fault for the problem; motivates people to hide the true cause
* Clarity / Readability - not just maintainability, also how well ideas are transmitted; limitations affecting clarity include hardware limits (memory, performance), language / tooling (work-arounds, boilerplate), programmer limits (mastery of the dev environment, misunderstandings), historical accidents, essential complexity; often these are past limitations, the code would have been written differently today and that may drive jr devs to resent sr staff
* Correctness - above all other concerns, code needs to solve the problem; efficient, elegant code doesn't matter if it arrives at the wrong answer
* Essential Complexity - inescapable complexity of the problem domain
* Experiment Design - poorly designed experiments may only be testing the measurement instruments themselves, not any phenomena; studies about problem solving often fail to translate to programming because the problems used in studies are simple enough to have a known, best solution
* Fisher's Fundamental Theorem - the better adapted a system is to a given environment, the less adaptable it is to new environments; optimizations often make code less portable, less future proof
* Hawthorne Effect - consider that study subjects change their behaviour merely as a result of being studied; studies at the Hawthorne Works of the Western Electric Company failed to consider that workers under observation increased their productivity out of pride; anthropologists struggle to become invisible to the cultures they visit so that life will continue as normal
* Historical Accidents - hacks to solve problems that have been obscured by time
* Predictable Delivery - unpredictable delivery is psychologically upsetting; "it is not the mean length of estimated time that annoys people but, rather, the standard deviation in the actual time taken"; managing for quality involves delivering predictably
* Psychology - the psychology of programmers can be studied in terms of social structure (how individuals relate), material culture (tools), recruitment (how people become programmers), and myths (common beliefs)
* Quality - how to measure? elegance and adaptability cannot be quantified, metrics such as line count, cyclomatic complexity are gameable, performance and adherence to spec cannot be determined merely by reading the code; we try to discuss relative code quality by comparing code listings that solve the same problem
* Root-Cause Analysis - introspect on the processes that lead to the problem
* Specs - "When there are multiple users, there are multiple specifications."
* Virtual Memory - swap on disk

# Techs

* COBOL - lang, promised to make code read-able to non-techies
* FORTRAN - lang, lacks the facility to recognize an end-of-file marker
* JCL - OS/360 Job Control Language
* PL/I - lang, apparently better than Fortran; beware math (floating) versus arithmetic (integer) libs
* Terminals - terminal programming made it less fashionable to read program listings in the whole

# Names Dropped

* ACM Special Interest Group on Personnel Research - loose association studying programming from the perspective of management concerns (ie. hiring and training)
* Albert Einstein - "The important thing is to never stop questioning."
* Ambrose Bierce - myths are the sacred beliefs of other people
* Bertrand Russel - faith is belief in something for which there is no evidence
* Bill Gates - perhaps the best programmer in the world, if your success measure is money earned
* IBM Systems Research Institute - this book includes research from here
* James Clerk Maxwell - "To measure is to know."
* Lord Kelvin - "I can state flatly that heavier than air flying machines are impossible."
* Sigmund Freud - notes the importance of introspection, self-analysis
* State University of New York - this book includes research from here
* William James - founder of American psychology

# Publications

* A General Introduction to Psychoanalysis - Sigmund Freud
* Fourth Generation Computers: User Requirements and Transition - Fred Gruenberger book
* PL/I Language Log - IBM internal doc, spec for the PL/I lang
* PL/I Programming: A Manual of Style - Weinberg book
* Planning a Computer System: Project Stretch - book by Werner Bucholz
* Quality Software Management series - by the author
* The Genetical Theory of Natural Selection - Ronald Fisher book
* The Social Psychology of Industry - J.A.C. Brown, about Industrial Psychology
