# PHP-Practice-file
20 practice is included 



---

1. 

function dynamicOperation($input1, $input2) {
    if (is_numeric($input1) && is_numeric($input2)) {
        return $input1 * $input2;
    } elseif (is_string($input1) && is_string($input2)) {
        $arr = [$input1, $input2];
        sort($arr);
        return implode(' ', $arr);
    } else {
        return $input1 . $input2;
    }
}



---

2.

define('EXCHANGE_RATE', 0.85); // USD to EUR rate

function convertCurrency($amounts, $direction) {
    return array_map(function($amount) use ($direction) {
        return $direction === 'USD_TO_EUR' ? $amount * EXCHANGE_RATE : $amount / EXCHANGE_RATE;
    }, $amounts);
}



---

3

function reverseWords($paragraph) {
    $sentences = explode('. ', $paragraph);
    $reversedSentences = array_map(function($sentence) {
        return implode(' ', array_reverse(explode(' ', $sentence)));
    }, $sentences);
    return implode('. ', $reversedSentences);
}



---

4. 

function detectDataType($var) {
    try {
        $type = gettype($var);
        if ($type == 'resource') throw new Exception("Invalid resource type");
        return $type;
    } catch (Exception $e) {
        return $e->getMessage();
    }
}



---

5. 

function fizzBuzzOrPrime($number) {
    if (isPrime($number)) {
        return "Prime";
    } elseif ($number % 3 == 0 && $number % 5 == 0) {
        return "FizzBuzz";
    } elseif ($number % 3 == 0) {
        return "Fizz";
    } elseif ($number % 5 == 0) {
        return "Buzz";
    }
}

function isPrime($num) {
    if ($num < 2) return false;
    for ($i = 2; $i <= sqrt($num); $i++) {
        if ($num % $i == 0) return false;
    }
    return true;
}



---

6. 

function bitwiseEqual($a, $b) {
    return ($a ^ $b) === 0;
}



---

7. 

function evaluateConditions($conditions) {
    return $conditions['a'] && ($conditions['b'] || !$conditions['c']);
}



---

8. 

function calculateDiscount($years, $isPremium) {
    $discount = 0;

    if ($years > 5) {
        $discount = 30;
    } elseif ($years >= 3 && $years <= 5) {
        $discount = 20;
    } elseif ($years < 3) {
        $discount = 10;
    }

    if ($isPremium) {
        $discount += 10;
    }

    return $discount;
}



---

9.

function ternaryChallenge($age, $membership, $purchase) {
    return $age > 18 
        ? ($membership == 'premium' 
            ? ($purchase > 100 ? 'Gold Member' : 'Silver Member') 
            : 'Regular Member') 
        : 'Not Eligible';
}



---

10. 

function calculator($expression) {
    $parts = explode(' ', $expression);
    $num1 = $parts[0];
    $operator = $parts[1];
    $num2 = $parts[2];

    switch ($operator) {
        case '+':
            return $num1 + $num2;
        case '-':
            return $num1 - $num2;
        case '*':
            return $num1 * $num2;
        case '/':
            return $num1 / $num2;
        default:
            return "Invalid operator";
    }
}



---

11. 

function printPyramid($size) {
    for ($i = 1; $i <= $size; $i++) {
        for ($j = 1; $j <= $i; $j++) {
            echo $j . " ";
        }
        echo "\n";
    }
}



---

12. 

function generateArrayAndSum($num) {
    $arr = array();
    for ($i = 0; $i < $num; $i++) {
        $arr[] = rand(1, 100);
    }

    $sum = 0;
    for ($i = 0; $i < count($arr); $i++) {
        if ($i % 2 == 1) continue;
        $sum += $arr[$i];
    }

    return $sum;
}



---

13. 

function fibonacci($n) {
    $sequence = [0, 1];
    while (count($sequence) < $n) {
        $sequence[] = end($sequence) + prev($sequence);
    }
    return $sequence;
}



---

14. 

function findPrimes($limit) {
    $primes = [];
    for ($i = 2; $i <= $limit; $i++) {
        if (isPrime($i)) {
            $primes[] = $i;
        }
    }
    return $primes;
}

function isPrime($num) {
    if ($num < 2) return false;
    for ($i = 2; $i <= sqrt($num); $i++) {
        if ($num % $i == 0) return false;
    }
    return true;
}



---

15. 

function sortProductsByPrice($products) {
    arsort($products);
    return $products;
}



---

16. 

function findTopStudent($students) {
    $topStudent = '';
    $highestAverage = 0;

    foreach ($students as $student => $scores) {
        $average = array_sum($scores) / count($scores);
        if ($average > $highestAverage) {
            $highestAverage = $average;
            $topStudent = $student;
        }
    }

    return [$topStudent, $highestAverage];
}



---

17. :

function searchArray($arr, $threshold) {
    return array_filter($arr, function($num) use ($threshold) {
        return $num > $threshold;
    });
}



---

18

function filterAndReverse($words) {
    $filtered = array_filter($words, function($word) {
        return !preg_match('/[aeiou]/i', $word);
    });

    return array_map('strrev', $filtered);
}



---

19

function mergeScores($arr1, $arr2) {
    foreach ($arr2 as $key => $value) {
        if (isset($arr1[$key])) {
            $arr1[$key] = max($arr1[$key], $value);
        } else {
            $arr1[$key] = $value;
        }
    }
    return $arr1;
}



---
20

function isPalindrome($str) {
    if (strlen($str) <= 1) return true;
    if ($str[0] != $str[strlen($str) - 1]) return false;
    return isPalindrome(substr($str, 1, -1));
}


$divisibleBy3And7 = array_filter($numbers, function($num) {
    return $num % 3 == 0 && $num % 7 == 0;
});





