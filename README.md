# Set
Group members: Narine Vardanyan, Narek Khachikyan, Karine Asoyan
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Random;


public class SetGame {
    private static Random random = new Random(); // needs to be initialized for the tests
    private static long totalRounds = 0;
    private static long gamesWithOnly12Cards = 0;
    private static long[][] setCounter = new long[70][70]; // deck-size, table-size
    private static long[][] noSetCounter = new long[70][70]; // deck-size, table-size
    private static long[][] availableSets = new long[70][70]; // deck-size, table-size

    class Card implements Comparable {
        private int number;
        private int symbol;
        private int shading;
        private int colour;
        private float sortOrder;

        public Card(int nu, int sy, int sh, int co) {
            number = nu;
            symbol = sy;
            shading = sh;
            colour = co;
            sortOrder = random.nextFloat(); // used when shuffling the deck
        }
        public int compareTo(Object other) {
            if (this.sortOrder == ((Card) other).sortOrder)
                 return 0;
             else if ((this.sortOrder) > ((Card) other).sortOrder)
                 return 1;
             else
                 return -1;
        }

        public String toString() {
            return number + ":" + symbol + ":" + shading + ":" + colour; // + " - " + sortOrder;
        }
    }

