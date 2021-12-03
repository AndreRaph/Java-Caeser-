# Java-Caeser-


package com.company;
import java.lang.String;
import java.util.Scanner;

    public class Main {

    public static StringBuffer encrypt(String text, int c) {

        StringBuffer result = new StringBuffer();

        for (int i = 0; i < text.length(); i++) {
            if (Character.isUpperCase(text.charAt(i))) {
                char ch = (char) (((int) text.charAt(i) + c - 65) % 26 + 65);
                result.append(ch);
            } else {
                char ch = (char) (((int) text.charAt(i) + c - 97) % 26 + 97);
                result.append(ch);
            }
        }
        return result;
    }


    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("PlainText: ");
        String text = in.nextLine();
        System.out.print("Provide an Integer for Number of rotations: ");
        int c = in.nextInt();
        System.out.println("Ciphertext: " + encrypt(text, c) );

    }
}
