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

I was unable to discover the intended solution to this challenge.

I experimented with various ways of reformatting the time in RevisionFormatter.
I initially searched for a prebuilt way of formatting the time, but none of them
appeared to fit better than what was already in use. Nonetheless, I still tried
one of them - RFC_1123_DATE_TIME - but discovered that Wikipedia seemingly did
not support parsing time in this format.

I then tried to use the .ofPattern() method of formatting the time, but I was
not able to discover a pattern that the project would accept. For example,
DateTimeFormatter.ofPattern("MMMM d yyyy hh:mm:ss a").format(revision.timestamp),
was intended to return something like "July 6, 2021 4:15:37 PM", but I continually
received errors claiming "Unsupported Field".

I read several articles on the internet and was not able to come up with a solution here.
I looked back at some assignments from CS222 that were about parsing from Wikipedia, but even
the solutions I implemented there did not work when I tried to use them here. Genuinely lost.

(As a side note, I removed the various code experiments that I did as I have reason to believe that
they may be flagged as clean code violations.)

## Challenge #3 Complete

For my solution to Challenge #3, I condensed the original StringBuilder code block
into one line:
String stringBuilder = response.revisions().stream().map(formatter::format).map(message -> message + "\n").collect(Collectors.joining());

I believe this line of code takes a response that is given to it from the revisionParser
and sends it to a hashmap such that it can be reformatted properly (having the time formatting
applied, adding a linebreak after each collected response, etc.) It then returns all of this to be
viewed by the user.

## Reflection Question #1: Functional vs OO

For Challenge #3, I am much more familiar with StringBuilders than collectors, so generally
speaking I would lean towards StringBuilders if I had my own choice. I am not aware of which
option is more efficient than the other (if there is any efficiency difference at all, for that
matter). It was very interesting to learn new things though, so in that light Collectors shine.
It is also fascinating to me to be able to condense several lines of code down into one line of code.
I imagine one day, when I am skilled at a language, I'll be able to accomplish something like that
on my own project (or those of my peers). I look forward to that day.

## Reflection Question #2: Polymorphism and Dependency Inversion

I believe that polymorphism engendered dependency inversion in this little
application when we used Guice dependency injection. For example, in the following
code snippet from Class "App.java" at line 28 through 34:

@Override
public void start(Stage primaryStage) {
Injector injector = Guice.createInjector(
new QueryEngineModule(),
executorServiceModule
);
WikipediaAnalyzer analyzer = injector.getInstance(WikipediaAnalyzer.class);

I believe this to be an example of dependency inversion being used in the little
application. This supports polymorphism by allowing us to use the same dependency
injection code block to handle multiple methods in multiple classes. Thus, this
code block is being used in multiple different ways by different types of objects
and methods.

