import java.util.Scanner;

public class partyProfit {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int partySize=Integer.parseInt(scanner.nextLine());
        int days=Integer.parseInt(scanner.nextLine());

        int coins=0;
        for (int day=1;day<=days;day++){

            if (day % 10 == 0) {
                partySize-=2;
            }
            if (day % 15 == 0) {
                partySize+=5;
            }
            coins+=(50-(2*partySize));
            if (day%3==0){
                coins-=(3*partySize);
            }
            if (day % 5 == 0) {
                coins += 20 * partySize;
            }
            if (day % 3 == 0 && day % 5 == 0) {
                coins -= (partySize * 2);
            }

            }

        double sumCoin=Math.floor(coins/partySize);
        System.out.printf("%d companions received %.0f coins each.",partySize,sumCoin);
    }
}
