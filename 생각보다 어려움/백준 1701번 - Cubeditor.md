# λ°±μ€ 1701λ² - Cubeditor

```java
package sonny.study;

import java.io.*;
import java.util.*;

public class Main {

    static Scanner sc = new Scanner(System.in);
    static BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    static BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
    static StringBuilder sb = new StringBuilder();

    public static void main(String[] args) throws IOException {
        String T = sc.nextLine();

        int max = Integer.MIN_VALUE;
        for (int i = 0; i < T.length(); i++) {
            String s = T.substring(i);

            int[] table = makeTable(s);

            for (int j : table) {
                if (max < j) {
                    max = j;
                }
            }
        }

        System.out.println(max);
    }

    static int[] makeTable(String string) {
        int n = string.length();
        int[] table = new int[n];

        int idx = 0;
        for (int i = 1; i < n; i++) {
            while (idx > 0 && string.charAt(i) != string.charAt(idx)) {
                idx = table[idx - 1];
            }

            if (string.charAt(i) == string.charAt(idx)) {
                idx += 1;
                table[i] = idx;
            }
        }
        return table;
    }
}



```

## π¨ μ΄λ €μ λ μ 

- piλ°°μ΄μ μ¬μ©νμ¬ λ°°μ΄μμ κ°μ₯ ν° κ°μ μΆλ ₯νλ©΄ λλμ€ μμμ§λ§ νλ Έλ€κ³  νλ€.

## π ν΄κ²°μ±

- μ§λ¬Έμμ λ°λ‘λ₯Ό μ°Ύμλλ°, `qbqtzqqt`μ `qt`κ° μ€κ°μ νλ λμ νλ 2λ² λ°λ³΅λλ€. makeTable λ©μλμμλ μμ μΈλ±μ€κ° 0μΈ κ²λ§ λ°°μ΄λ‘ μ μ₯νκΈ° λλ¬Έμ μ€κ°κ³Ό λμ μ€λκ±΄ μΈμ§ μλλ€.
- λλ¬Έμ λ¬Έμμ΄ κΈΈμ΄λ§νΌμ λ°λ³΅νλ forλ¬Έμ μΆκ°νλ€.
  - μ΄λ¬λ©΄ κ°λ₯ν λͺ¨λ  λ¬Έμμ΄μ λͺ¨λ νμνλ―λ‘ κ°μ₯ κΈ΄ λ¬Έμμ΄μ μ°Ύμ μ μλ€.


## π λλμ 

- μ€κ°κ³Ό λμ λ λ² μ€λ κ²μ μκ°νλκ±° μμ²΄κ° μ΄λ ΅λ€κ³  μκ°νλ€.