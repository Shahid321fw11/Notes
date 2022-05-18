- ```javascript
  npm init --> to make a json file.
  npm i express // to install express
  module.exports = obj // to export anything any file. // file name is second
  const name=require("./second");// obj will be sotredd in name
  ```

  - **Node is the runtime built on chrome V8 engine.**
  - **Node is the javascript running on the server.**
  - **Why use nodejs compare to other langauage**
  - **What is REPL in node**
    - REPL(**Read Eval Print Loop**) in same like CMD. When you write node on cmd and hit enter the interface you see is REPL.
    - Or you can say REPL in same like your console on browser.
  - **Modules in node**
    - **fs**  --> This module helps in handling file system.
    - 
  
  ```
  import java.io.*;
  import java.math.*;
  import java.security.*;
  import java.text.*;
  import java.util.*;
  import java.util.concurrent.*;
  import java.util.function.*;
  import java.util.regex.*;
  import java.util.stream.*;
  import static java.util.stream.Collectors.joining;
  import static java.util.stream.Collectors.toList;
  
  
  
  class Result {
  
      /*
       * Complete the 'processLogs' function below.
       *
       * The function is expected to return a STRING_ARRAY.
       * The function accepts following parameters:
       *  1. STRING_ARRAY logs
       *  2. INTEGER threshold
       */
  
      public static List<String> processLogs(List<String> logs, int threshold) {
      // Write your code here
      Map<String,Integer> map=new HashMap<>();
      for(String str:logs)
      {
          String[] str1=str.split(" ");
          String val1=str1[0];
          String val2=str1[1];
          if(val1.equals(val2))
          {   if(map.containsKey(val1))
              map.put(val1,map.get(val1)+1);
              else map.put(val1,1);
          }
          else
          {
              if(map.containsKey(val1))
              map.put(val1,map.get(val1)+1);
              else map.put(val1,1);
              if(map.containsKey(val2))
              map.put(val1,map.get(val2)+1);
              else map.put(val2,1);
          }
      }  
      List<String> lst=new ArrayList<>();
      for(Map.Entry m:map.entrySet())
      {  
         String key= m.getKey();
         int val=m.getValue();
         if(val>=threshold)
          lst.add(key);
      }  
    
    return lst;
      }
  
  }
  
  public class Solution {
      public static void main(String[] args) throws IOException {
          BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
          BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));
  
          int logsCount = Integer.parseInt(bufferedReader.readLine().trim());
  
          List<String> logs = IntStream.range(0, logsCount).mapToObj(i -> {
              try {
                  return bufferedReader.readLine();
              } catch (IOException ex) {
                  throw new RuntimeException(ex);
              }
          })
              .collect(toList());
  
          int threshold = Integer.parseInt(bufferedReader.readLine().trim());
  
          List<String> result = Result.processLogs(logs, threshold);
  
          bufferedWriter.write(
              result.stream()
                  .collect(joining("\n"))
              + "\n"
          );
  
          bufferedReader.close();
          bufferedWriter.close();
      }
  }
  
  ```
  
  