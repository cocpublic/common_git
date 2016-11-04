##题目 
>
每天要给很多人发邮件。有一天他发现发错了邮件，把发给A的邮件发给了B，把发给B的邮件发给了A。
于是他就思考，要给n个人发邮件，在每个人仅收到1封邮件的情况下，有多少种情况是所有人都收到
了错误的邮件？即没有人收到属于自己的邮件。

解析：
>
错排问题。
若前n-1个数已经满足错排，现考虑第n个数：
（1）第n个数可以和前n-1个中任意一个数互换，结果仍然是错排，所以有(n-1)*D(n-1)种；
（2）第n个数可以放到前n-1任意一个位置，但是原来位置的数不能放到最后，
     则其只可以能放在其他n-2个位置，并且保证这n-2的位置是错排，所以有(n-1)*D(n-2)
 
综上，一共有 D(n) =（n-1）*(D(n-1)+D(n-2))
特殊地，D(1) = 0, D(2) = 1.

###Java实现
```java
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while (sc.hasNext()) {
            int n = sc.nextInt();
            System.out.println(count(n));
        }
    }
    
    /**
     * 错排算法,注意是long型
     * @param n
     * @return
     */
    public static long count(int n) {
        if (n == 1) {
            return 0;
        } else if (n == 2) {
            return 1;
        } else {
            return (n - 1) * (count(n - 1) + count(n - 2));
        }
    }
}
```
