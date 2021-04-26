# Project Report

Kaleb Matchett

## Challenge #1 Complete

My solution for challenge #1 was to modify class "QueryEngineModule.java".

In the Override, the original code had the line:
"bind(QueryEngine.class).to(FakeQueryEngine.class);"
I instead changed this to:
"bind(QueryEngine.class).to(WikipediaQueryEngine.class);"

I also had to modify the import statement for this class.
I changed "import edu.bsu.cs.model.FakeQueryEngine;" to 
"import edu.bsu.cs.model.WikipediaQueryEngine;"

## Challenge #2 Incomplete

(Explain your solution to Challenge #2. If it is not complete, change
the subsection title above to "Incomplete" and explain how far you got
and where you got stuck.)

## Challenge #3 Incomplete

(Explain your solution to Challenge #3. If it is not complete, change
the subsection title above to "Incomplete" and explain how far you got
and where you got stuck.)

## Reflection Question #1: Functional vs OO

(Write one or more paragraphs comparing and contrasting the iterative and functional  
approaches to string concatenation you explored in challenge #3. Which do you
prefer, and why?)

## Reflection Question #2: Polymorphism and Dependency Inversion

(Explain how polymorphism engendered dependency inversion in this little
application. Be clear and precise here, as this is, in part, an assessment of
your correct use of technical terminology.
Consider, for example, where exactly is polymorphism used?
Where exactly is a dependency inverted?)

