---
layout: post
title:  "!!"
date:   2016-03-30 19:45:31 +0530
categories: notes
author: "Serena Liu"
---
[Regex](https://www.tutorialspoint.com/java/java_regular_expressions.htm)

Practices:

1. [Detect Email](https://www.hackerrank.com/challenges/detect-the-email-addresses):
```
([a-zA-Z0-9\\-\\.\\_]+)\\@([a-zA-Z0-9\\-\\.]+)(\\.[a-zA-Z]+)(/\\S*)?
```
2. [Detect HTML Tags]():
```
<[^>]*>
```
3. [Detect URLs](https://www.hackerrank.com/challenges/detect-the-domain-name):
```
(http|https)\\://(www.|ww2.|)([a-zA-Z0-9\\-\\.]+)(\\.[a-zA-Z]+)(/\\S*)?
```

  ```
  import java.io.*;
  import java.util.*;
  import java.util.regex.*;

  public class Solution {

      public static void main(String[] args) {
          /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
          Scanner in = new Scanner(System.in);
          String format = "(http|https)\\://(www.|ww2.|)([a-zA-Z0-9\\-\\.]+)(\\.[a-zA-Z]+)(/\\S*)?";
          Pattern pattern = Pattern.compile(format);
          Set<String> set = new HashSet<String>();

          int testcase = in.nextInt();
          String dec = in.nextLine();

          for(int i = 0;i < testcase;i++){
              String assessed = in.nextLine();
              Matcher match = pattern.matcher(assessed);
              while(match.find()){
                      match.groupCount();
                      String curStr = match.group(3)+match.group(4);
                      set.add(curStr);
              }
          }

          List<String> res = new ArrayList<String>(set);
          Collections.sort(res);

          for(int i = 0;i < res.size(); i++){
              if(i == res.size()-1){
                  System.out.print(res.get(i));
              }
              else{
                  System.out.print(res.get(i)+";");
              }
          }
      }
  }
  ```

Reference:
- http://regexr.com/
