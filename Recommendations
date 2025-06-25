package Rec; 
import java.io.*;
import java.util.*;
public class Recommendations {
    public static void main(String[] args) {
        String filePath = "data/data.csv";
        Map<Integer, List<Integer>> userItemMap = new HashMap<>();

        try (BufferedReader br = new BufferedReader(new FileReader(filePath))) {
            String line;

            while ((line = br.readLine()) != null) {
                String[] parts = line.split(",");
                int userId = Integer.parseInt(parts[0]);
                int itemId = Integer.parseInt(parts[1]);

                userItemMap.computeIfAbsent(userId, k -> new ArrayList<>()).add(itemId);
            }

     
            for (Map.Entry<Integer, List<Integer>> entry : userItemMap.entrySet()) {
                int user = entry.getKey();
                List<Integer> items = entry.getValue();
                System.out.println("User " + user + " might also like item " + (items.get(0) + 10));
            }

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
