# Snippet 1

## Mine

### Code
```
@Test
public void checkSnippet1() throws IOException{

    String fileName = "s1.md";
    Path fileName1 = Path.of(fileName);
    String content = Files.readString(fileName1);
    ArrayList<String> expected = new ArrayList<String>();
    expected.add("url.com");
    expected.add("ucsd.edu");

    assertArrayEquals(expected.toArray(), MarkdownParse.getLinks(content).toArray());
}
```

### Expected Output

An ArrayList with the following values:

1. url.com
1. ucsd.edu

### Actual output

### Why?

There is no logic that cares about backticks. Therefore, it will expect "\`google.com" as well. This does not follow Markdown regulations.

## Theirs

### Code

```
@Test
public void checkSnippet1() throws IOException{

    String fileName = "s1.md";
    Path fileName1 = Path.of(fileName);
    String content = Files.readString(fileName1);
    ArrayList<String> expected = new ArrayList<String>();
    // expected.add("url.com");

    expected.add("google.com");
    expected.add("ucsd.edu");

    assertArrayEquals(expected.toArray(), MarkdownParse.getLinks(content).toArray());
}
```



### Expected Output

### Actual output

### Why?

# Snippet 2

## Mine

### Code

### Expected Output

### Actual output

### Why?

## Theirs

### Code

### Expected Output

### Actual output

### Why?

# Snippet 3

## Mine

### Code

### Expected Output

### Actual output

### Why?

## Theirs

### Code

### Expected Output

### Actual output

### Why?

# Questions

## Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks?

I think there is a way. Since everything within backticks would not be counted towards the identification of a link, you could just remove them entirely. I would write a function to remove everything including and between backticks.

## Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets?

I think there is a way, but it would be more involved. There would need to be new checks for the following situations:

1. nested parentheses
1. brackets
1. escaped brackets

For 1 and 2, you would need two new functions to give the index of the closing bracket or parentheses respectively in order to abide by clean coding standards. You would have to include logic to ignore escaped characters, which would have to run on each bracket or parentheses. In total, each function would require three variable definitions, a while loop with logic that increments a variable for open or closed parentheses, and logic to account for escaped characters. Easily, this would pass 10 lines.


## Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses?

I think there is a way. You could simply remove every instance of newline between open and closed parentheses. While this could carry risks towards misrecognition, it probably wouldn't be that bad. 
