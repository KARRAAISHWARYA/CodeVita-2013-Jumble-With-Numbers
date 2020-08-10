# CodeVita-2013-Jumble-With-Numbers

import java.util.Scanner;
 
public class Main {
 
    public static void main(String[] args) {
        int lower = 0;
        int upper = 0;
        int n = 0;
        Scanner sc = new Scanner(System.in);
        try {
            boolean flag = false;
            try {
                lower = sc.nextInt();
 
            } catch (Exception e) {
                flag = true;
            }
            try {
                upper = sc.nextInt();
 
            } catch (Exception e) {
                flag = true;
            }
            try {
                n = sc.nextInt();
            } catch (Exception e) {
                flag = true;
            }
            if (flag) {
                throw new Exception();
            }
            if (lower > upper) {
                throw new Exception();
            }
 
            int i = 1;
            flag = false;
            int count = 0;
            while (true) {
                int nu = i * (2 * i - 1);
 
                if (nu < lower) {
                    i++;
                    continue;
                }
                if (getMathew(lower,upper,nu)) {
                    count++;
                    if (count == n) {
                        System.out.println(nu);
                        break;
                    }
 
                }
 
                if (nu > upper) {
                    flag = true;
                    break;
                }
 
 
 
                i++;
            }
            if (flag) {
                System.out.println("No number is present at this index");
            }
        } catch (Exception e) {
            System.out.println("Invalid Input");
        }
    }
 
    static boolean getMathew(int lower,int upper,int num) {
 
 
        int i = 1;
        while (true) {
            int nu = i * (i + 1);
            nu /= 2;
            if (nu < lower) {
                i++;
                continue;
            }
 
            if (nu == num) {
                return true;
            }
            if (nu > upper) {
 
                break;
            }
 
 
 
            i++;
 
        }
        return false;
    }
}


