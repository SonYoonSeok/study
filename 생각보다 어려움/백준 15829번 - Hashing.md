# ๋ฐฑ์ค 15829๋ฒ - Hashing

```java
public class Main {

    static Scanner sc = new Scanner(System.in);
    static BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    static BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
    static StringBuilder sb = new StringBuilder();

    public static void main(String[] args) throws IOException {

        int N = sc.nextInt();
        BigInteger bigInteger = new BigInteger("0");
        BigInteger mul = new BigInteger("31");
        BigInteger rem = new BigInteger("1234567891");
        String input = sc.next();

        for (int i = 0; i < N; i++) {
            BigInteger val = new BigInteger(String.valueOf((int) input.charAt(i) - 96));
            BigInteger add_val = new BigInteger("1");
            for (int j = 0; j < i; j++) {
                add_val = add_val.multiply(mul);
            }
            add_val = add_val.multiply(val);
            bigInteger = bigInteger.add(add_val);
            bigInteger = bigInteger.remainder(rem);
        }

        System.out.println(bigInteger);
    }
}

```

## ๐จ ์ด๋ ค์ ๋ ์ 

- ์๋ฐ์ Math.pow๋ฅผ ์ฌ์ฉํ์ฌ ํ๋ฉด long ๋ฒ์๊น์ง๋ฐ์ ํํ์ด ์๋์ BigInteger ํํ๋ก ์ ๊ณฑ์ ํด์ผํ๋ค.	

## ๐ ํด๊ฒฐ์ฑ

* ๋ฐ๋ณต๋ฌธ์ ๋๋ ค์ BigInterger์ ๊ณ์ ๊ณฑํด์ฃผ์๋ค.

## ๐ ๋๋์ 

- ์ด๊ฒ ์ ๋ธ๋ก ์ฆ ๋ฌธ์ ์ธ์ง ๋ชจ๋ฅด๊ฒ ๋ค.

