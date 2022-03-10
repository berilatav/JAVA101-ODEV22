Program to calculate the sum of digits of a number.

örnek = 407
toplam = 11
armstrong = (4^3)+(0^3)+(7^3)= 407


import java.util.Scanner;
public class Odev22 {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);
        System.out.println("Enter a number :");                  // Sayı giriniz.
        int number = input.nextInt();
        int numberOfDigits = 0;                                  // Basamak Sayısı
        int tempNumber = number;                                 // Kullanıcının girdiği sayının sıfırlanmaması adına geçici sayı atandı.
        int valueOfDigits = 1;                                   // Basamak Değeri
        int result = 0;
        int powerOfDigits;                                       // Basamağın basamak sayısı ile üssünün alınma işlemi


        while(tempNumber != 0) {
            tempNumber /=10;
            numberOfDigits ++;

        }

        int sum = 0;
        tempNumber = number;
        while (tempNumber != 0){
            valueOfDigits = tempNumber % 10;                     // Basamak değerini 10'a bölümden kalan ile bulma
            powerOfDigits = 1;

            for(int i =1; i<=numberOfDigits ; i++ ){
                powerOfDigits *= valueOfDigits;
            }
            result += powerOfDigits;                              // Armstrong sayısını hesaplama
            tempNumber /=10;

        }

        if(result == number){
            System.out.println(number + " is an armstrong number. ");
        }

        else{
            System.out.println(number + " is not an armstrong number. ");
        }

        while(number >= 1){                                       // Basamakların toplamını hesaplama
            sum += (number % 10);
            number = number / 10;
        }
        System.out.println( sum + " the of the digits of the number.");

    }
}
