package sit.int202.jcfreview;
Testddde
import java.io.File;
import java.io.FileNotFoundException;
import java.util.*;

public class ProblemThree {
    public static void main(String[] args) throws FileNotFoundException {
        File file = new File("Data.txt");
        if (!file.exists()){
            System.out.println(file.getName() + " dose NOT exist!!!");
            return;
        }else{
            Scanner scanner = new Scanner(file);
            Map<String, List<Integer>> map = new HashMap<>(132);
            while (scanner.hasNextLine()){
                String line = scanner.nextLine();
                StringTokenizer stk = new StringTokenizer(line, " .=<>()\"+-*/{},0123456789[];");
                int index = 0;
                while (stk.hasMoreTokens()){
                    String word = stk.nextToken();
                    if(map.get(word) == null){
                        map.put(word,new LinkedList<>());
                    }
                    map.get(word).add(++index);
                }
            }
            scanner.close();
            for (Map.Entry<String, List<Integer>> entry : map.entrySet()){
                System.out.print(entry.getKey() + "(" + entry.getValue().size()+ "): ");
                for (Integer i : entry.getValue()){
                    System.out.print("@" + i + " ");
                }
                System.out.println();
            }
        }

    }
}
