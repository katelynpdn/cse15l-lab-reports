### Bug: 
filter method in the ListExampleS class
### Failure-inducing input:

My import statements:
`
import static org.junit.Assert.*;
import java.util.ArrayList;
import java.util.List;
import org.junit.*;
`
//
A class to implement the StringChecker interface- it returns true if the string starts with the character 's'
`
class StringChecker2 implements StringChecker {
    public boolean checkString(String s) {
        if (s.charAt(0) == 's') {
            return true;
        }
        return false;
    }
}
`
//
My JUnit Test:
`
public class ListTests {
    @Test
    public void testFilter() {
        List<String> stringList = new ArrayList<String>();
        stringList.add("string");
        stringList.add("ey");
        stringList.add("s2");
        List<String> stringList2 = new ArrayList<String>();
        stringList2.add("string");
        stringList2.add("s2");
        StringChecker2 sc = new StringChecker2();
        assertEquals(stringList2, ListExamples.filter(stringList, sc));
    }
`
The input is an ArrayList containing "string", "ey", and "s2", and the expected result is an ArrayList containing "string" and "s2" which both start with 's'.
### Input that doesn't induce a failure:
I added this JUnit Test to my ListTests class:
`
    @Test
    public void testFilter2() {
        List<String> stringList = new ArrayList<String>();
        stringList.add("string");
        stringList.add("ey");
        List<String> stringList2 = new ArrayList<String>();
        stringList2.add("string");
        StringChecker2 sc = new StringChecker2();
        assertEquals(stringList2, ListExamples.filter(stringList, sc));
    }
  `
This test tests an ArrayList containing "string" and "ey", and since only the first string starts with 's', the expected result is an ArrayList only containing "string."
### Symptom:
### Bug, Before-change
`
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }
`
### Bug, After-change
`
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
`
The fix was changing `result.add(0, s)` to `result.add(s)`. The bug was that it was prepending the valid strings to a new array, when it should be adding them to the end in order to preserve the order. I changed it so that it adds the valid strings to the end of the new array.
