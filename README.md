# Number-To-Words
This program prints out passed number(s) using words for digits 

public class NumberToWords {

    public static void main(String[] args) {
        numberToWords(19930406);
        // System.out.println(getDigitCount(10000));
        // System.out.println(reverse(680));
    }
    public static void numberToWords(int number) {
        if(number < 0) {
            System.out.println("invalid Value");
        }

        int turned = reverse(number);

        //System.out.println("Using " + turned + " as a reverse reference");

        for(int i = 0; i < getDigitCount(number); i++) {
                int lastDigits = turned % 10;
                switch (lastDigits) {
                    case 0 -> System.out.println("Zero");
                    case 1 -> System.out.println("One");
                    case 2 -> System.out.println("Two");
                    case 3 -> System.out.println("Three");
                    case 4 -> System.out.println("Four");
                    case 5 -> System.out.println("Five");
                    case 6 -> System.out.println("Six");
                    case 7 -> System.out.println("Seven");
                    case 8 -> System.out.println("Eight");
                    case 9 -> System.out.println("Nine");
                }
                turned = turned / 10;
        }
    }

    public static int reverse(int number) {

        int reverse = 0;

        while (number != 0) {
            int lastDigit = number % 10;
            reverse *= 10;
            reverse += lastDigit;
            number /= 10;

            }
        return reverse;
    }
    public static int getDigitCount (int number){
        if (number < 0) {
            return -1;
        }

        int count = 0;
        int countOfNumbers = 0;
        if (number == 0) {
            countOfNumbers += 1;
            return countOfNumbers;
        }

        while (number > 0) {
            count = number % 10;
            countOfNumbers += 1;
            number = number / 10;
        }
        return countOfNumbers;
    }
}
