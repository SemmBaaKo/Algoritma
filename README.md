# Soal 1: Membalik String dengan Angka di Akhir
## Java:
```
public class ReverseString {
    public static void main(String[] args) {
        String input = "SEMANGKA1";
        String reversed = reverseAlphabet(input);
        System.out.println(reversed);
    }
    public static String reverseAlphabet(String input) {
        char[] chars = input.toCharArray();
        int left = 0, right = chars.length - 2; // Ignore the last character (the digit)        
        while (left < right) {
            char temp = chars[left];
            chars[left] = chars[right];
            chars[right] = temp;
            left++;
            right--;
        }        
        return new String(chars);
    }
}
```
## PHP:
```
<?php
function reverseAlphabet($input) {
    $alphabets = substr($input, 0, -1);
    $digit = substr($input, -1);
    $reversed = strrev($alphabets);
    return $reversed . $digit;
}

$input = "SEMANGKA1";
echo reverseAlphabet($input);
?>
```
# Soal 2: Mencari Kata Terpanjang dalam Kalimat
## Java:
```
public class LongestWord {
    public static void main(String[] args) {
        String sentence = "saya senang berinteraksi dengan lingkungan sekitar";
        String longest = findLongestWord(sentence);
        System.out.println(longest + ": " + longest.length() + " character");
    }

    public static String findLongestWord(String sentence) {
        String[] words = sentence.split(" ");
        String longest = "";
        
        for (String word : words) {
            if (word.length() > longest.length()) {
                longest = word;
            }
        }
        
        return longest;
    }
}
```
## PHP:
```
<?php
function findLongestWord($sentence) {
    $words = explode(" ", $sentence);
    $longest = "";

    foreach ($words as $word) {
        if (strlen($word) > strlen($longest)) {
            $longest = $word;
        }
    }
    
    return $longest;
}

$sentence = "saya senang berinteraksi dengan lingkungan sekitar";
$longest = findLongestWord($sentence);
echo $longest . ": " . strlen($longest) . " character";
?>
```

# Soal 3: Menghitung Frekuensi Kata dalam Array
## Java:
```
import java.util.HashMap;

public class WordFrequency {
    public static void main(String[] args) {
        String[] input = {"xx", "dx", "bbcb", "dx"};
        String[] query = {"bbcb", "ac", "dx"};
        int[] result = countQueryFrequency(input, query);
        
        for (int count : result) {
            System.out.print(count + " ");
        }
    }

    public static int[] countQueryFrequency(String[] input, String[] query) {
        HashMap<String, Integer> frequencyMap = new HashMap<>();
        for (String word : input) {
            frequencyMap.put(word, frequencyMap.getOrDefault(word, 0) + 1);
        }
        
        int[] result = new int[query.length];
        for (int i = 0; i < query.length; i++) {
            result[i] = frequencyMap.getOrDefault(query[i], 0);
        }
        
        return result;
    }
}
```
## PHP:
```
<?php
function countQueryFrequency($input, $query) {
    $frequency = array_count_values($input);
    $result = [];

    foreach ($query as $word) {
        $result[] = isset($frequency[$word]) ? $frequency[$word] : 0;
    }
    
    return $result;
}

$input = ['xx', 'dx', 'bbcb', 'dx'];
$query = ['bbcb', 'ac', 'dx'];
$result = countQueryFrequency($input, $query);
print_r($result);
?>
```

# Soal 4: Menghitung Selisih Jumlah Diagonal dalam Matriks NxN
## Java:
```
public class DiagonalDifference {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 5},
            {4, 3, 6},
            {7, 6, 9}
        };
        int result = diagonalDifference(matrix);
        System.out.println(result);
    }

    public static int diagonalDifference(int[][] matrix) {
        int primaryDiagonal = 0;
        int secondaryDiagonal = 0;
        
        for (int i = 0; i < matrix.length; i++) {
            primaryDiagonal += matrix[i][i];
            secondaryDiagonal += matrix[i][matrix.length - 1 - i];
        }
        
        return Math.abs(primaryDiagonal - secondaryDiagonal);
    }
}
```
## PHP:
```
<?php
function diagonalDifference($matrix) {
    $primaryDiagonal = 0;
    $secondaryDiagonal = 0;
    $size = count($matrix);

    for ($i = 0; $i < $size; $i++) {
        $primaryDiagonal += $matrix[$i][$i];
        $secondaryDiagonal += $matrix[$i][$size - 1 - $i];
    }
    
    return abs($primaryDiagonal - $secondaryDiagonal);
}

$matrix = [
    [1, 2, 5],
    [4, 3, 6],
    [7, 6, 9]
];
echo diagonalDifference($matrix);
?>
```

