# Red-Hat-Apprenticeship---GitHub-Assigment



 Q1   Write a program to check if two given String is Anagram of each other return true if Input
      string is anagram otherwise return false. (By the way, two String is called anagram, if
       they contain the same characters but in different order e.g. army and mary, stop and
        pots, etc. Anagrams are actually a mix-up of characters in String.) 
        
        

 CODE:  
 
      class AnagramCheck {
        public boolean isAnagram(String s, String t) {
                  
                int[] alphabet = new int[26];
                   for (int i = 0; i < s.length(); i++)
                   alphabet[s.charAt(i) - 'a']++;
              for (int i = 0; i < t.length(); i++) 
                 alphabet[t.charAt(i) - 'a']--;
                 for (int i : alphabet)
                  if (i != 0)
                    return false;
             return true;
     }
     }


      Input: s = "anagram", t = "nagaram"
     Output: true

      Input: s = "rat", t = "car"
      Output: false




 Q2   Insert + or - signs anywhere between the digits 123456789 in such a way that the
      expression evaluates to 100. The order of the digits must not be changed.
      Sample solution: 1 + 2 + 3 - 4 + 5 + 6 + 78 + 9 = 100 (DO NOT USE THIS
      COMBINATION)
      
      
 CODE:   
         
         public class Main {
           private static final String DIGITS = "123456789";
    
    public static List<String> sumTo(int target) {
        List<String> result = new ArrayList<>();
        generate(0, 0, target, new StringBuilder(), result);
        return result;
    }
    
    private static void generate(int start, int sum, int target, StringBuilder path, List<String> result) {
        if (start == DIGITS.length()) {
            if (sum == target) {
                result.add(path.toString());
            }
            return;
        }
        
        int len = path.length();
        int num = 0;
        for (int i = start; i < DIGITS.length(); i++) {
            num = 10 * num + DIGITS.charAt(i) - '0';
            
            if (start != 0) path.append('+');
            path.append(num);
            generate(i + 1, sum + num, target, path, result);
            path.setLength(len);
            
            path.append('-');
            path.append(num);
            generate(i + 1, sum - num, target, path, result);
            path.setLength(len);
        }
    }
    
    public static void main(String[] args) {
        test(100);
        test(9);
    }
    
    public static void test(int target) {
        System.out.println(String.format("Sum to %d -----------------", target));
        int count = 1;
        for (String s : sumTo(target)) {
            System.out.println(count + ": " + s);
            count++;
              }
                  }
                   }



 Q3   Write a program to transpose two matrices (3X3 or 4X4) and print the multiplication of
       the transposed matrices.



Code:       

      public class MatrixTranspose{  

                public static void main(String args[]){  

                      int original[][]={{1,3,4},{2,4,3},{3,4,5}};    
    

                        int transpose[][]=new int[3][3];  
           
             for(int i=0;i<3;i++){    
              for(int j=0;j<3;j++){    
              transpose[i][j]=original[j][i];  
          }    
      }    
  
         System.out.println("Printing Matrix without transpose:");  
                      for(int i=0;i<3;i++){    
                      for(int j=0;j<3;j++){    
                    System.out.print(original[i][j]+" ");    
                   }    
                     System.out.println(); 
             }    
                System.out.println("Printing Matrix After Transpose:");  
                    for(int i=0;i<3;i++){    
                    for(int j=0;j<3;j++){    
                     System.out.print(transpose[i][j]+" ");    
           }    
               System.out.println();    
            }    
        }}  




     Printing Matrix without transpose:
       1 3 4 
       2 4 3 
       3 4 5 

     Printing Matrix After Transpose:
       1 2 3 
       3 4 4 
       4 3 5 

