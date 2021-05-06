# HackerRank_Algorithm_Solution
This repo gives a guide and work flow on hackerRank Algorithm from simple to complex, it gives sudo code solution and code solution written in Kotlin

## Simple Array Sum

### Description
https://www.hackerrank.com/challenges/simple-array-sum/problem

### Solution
```
fun simpleArraySum(ar: Array<Int>): Int {
    // Write your code here
     var sum : Int = 0
     for(i in ar ) sum += i
     return sum
}
```


## A Very Big Sum

### Description
https://www.hackerrank.com/challenges/a-very-big-sum/problem

### Solution
```
fun aVeryBigSum(ar: Array<Long>): Long {
  var Bigsum : Long = 0;
for(i in ar) Bigsum += i
return Bigsum
}
```

## Plus Minus

### Description
https://www.hackerrank.com/challenges/plus-minus/problem

### Solution
```
fun plusMinus(arr: Array<Int>): Unit {
    // Write your code here

   val n = arr.size 
   var a : Double = 0.0
   var b : Double= 0.0
   var c : Double = 0.0
 for(i in arr){
     when{
         i > 0 -> a++
         i == 0 -> b++
         i < 0 -> c++
         
     }
}
        println(a/n)
        println(c / n)
        println(b / n)
} 
```

## Mini-Max Sum

### Description
https://www.hackerrank.com/challenges/mini-max-sum/problem

### Solution
```
fun miniMaxSum(arr: Array<Int>): Unit {

                 var sum : Long = 0
                 for(i in arr) sum += i
                 var min = arr.min()
                 var max = arr.max()
                print(sum - max!!)
                print(" ")
                print(sum - min!!)

}
```

## Birthday Cake Candles

### Description
https://www.hackerrank.com/challenges/birthday-cake-candles/problem

### Solution

```
fun birthdayCakeCandles(candles: Array<Int>): Int {
    // Write your code here
    
    var max : Int = 0
    var count : Int = 0
    for(i in candles) {
        when{
            i > max -> {max = i
                        count = 1}
            i == max -> count++
        }
    }
     return count
}
```

## Grading Students

### Description
https://www.hackerrank.com/challenges/grading/problem

### Solution

```
fun gradingStudents(grades: Array<Int>): Array<Int> {
    // Write your code here
    var result : ArrayList<Int> = arrayListOf()
                for (i in grades) {
                        if (i < 38) {
                                    result.add(i)
                        } else {
                                when {
                                        (i + 2) in 0..100 step 5 -> result.add(i+2)
                                        (i + 1) in 0..100 step 5 -> result.add(i+1)
                                        else -> result.add(i)
                                }
                        }
                }


                return result.toTypedArray()

}
```

## Apple and Orange

### Description
https://www.hackerrank.com/challenges/apple-and-orange/problem

## Solution

```
fun countApplesAndOranges(s: Int, t: Int, a: Int, b: Int, apples: Array<Int>, oranges: Array<Int>): Unit {
               
                var applecount: Int = 0
                var orrangecount: Int = 0
                for (i in apples) if ((a + i) in s..t) applecount++
                for (i in oranges)if ((b + i) in s..t) orrangecount++
                

               println(applecount)
                println(orrangecount)

}
```

## Number Line Jumps

### Description
https://www.hackerrank.com/challenges/kangaroo/problem

## Solution
```
fun kangaroo(x1: Int, v1: Int, x2: Int, v2: Int): String {
if( v1 > v2 && ((x1 - x2) % (v2 -v1) == 0 )) return "YES" else return "NO"

}
```

## Breaking the Records

### Description
https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem

## Solution
```
fun breakingRecords(scores: Array<Int>): Array<Int> {
        var high : Int = scores[0]
        var highcount : Int = 0
        var low : Int = scores[0]
        var lowcount : Int = 0
        var output : MutableList<Int> = mutableListOf()

        for ( i in scores){
            when{
                i > high -> {
                    high = i
                    highcount++
                }
                i < low -> {
                    low = i
                    lowcount++
                }
            }
        }
        output.add(highcount)
        output.add(lowcount)

        return output.toTypedArray()

}
```

## Subarray Division

### Description
https://www.hackerrank.com/challenges/the-birthday-bar/problem

### Solution
```
fun birthday(s: Array<Int>, d: Int, m: Int): Int {

     return s.asIterable().windowed(m,1).count{it.sum() == d }
     
}
```


## Divisible Sum Pairs

### Description
https://www.hackerrank.com/challenges/divisible-sum-pairs/problem

### Solution
```
fun divisibleSumPairs(n: Int, k: Int, ar: Array<Int>): Int {
 var count : Int = 0
        var firstSum : Int = 0
        for (i in 0..n-2){

            for(j in i until n -1) {
                firstSum = ar[i] + ar[j + 1]
                if (firstSum % k == 0) count++
            }
        }

    return count

}
```

## Migratory Birds

### Description
https://www.hackerrank.com/challenges/migratory-birds/problem

### Solution
```
fun migratoryBirds(arr: Array<Int>): Int {
   
        return arr.sorted().groupingBy { it }.eachCount().maxBy { it.value }!!.key 
}
```

## Bill Division

### Description
https://www.hackerrank.com/challenges/bon-appetit/problem

##  Solution
```
fun bonAppetit(bill: Array<Int>, k: Int, b: Int): Unit {

var correctBill : Int =  (bill.filterIndexed { index,it -> (index != k)}.sum())/2
        if(b > correctBill) println(b - correctBill)
        else println("Bon Appetit")
}
```

## Sales by Match

### Description 
https://www.hackerrank.com/challenges/sock-merchant/problem

## Solution 
```
fun sockMerchant(n: Int, ar: Array<Int>): Int {
 var sockstack : MutableList<Int> = mutableListOf()
      var count : Int = 0
      for(i in ar){
          if(sockstack.contains(i)) {
              sockstack.remove(i)
              count++
          }else sockstack.add(i)
      }
   return count

}
```

## CamelCase

### Description 
https://www.hackerrank.com/challenges/camelcase/problem

## Solution 
```
fun camelcase(s: String): Int {    
var count = 1
for(i in s) if(i.isUpperCase()) count++
return count
}
```

## Counting Valleys

### Description 
https://www.hackerrank.com/challenges/counting-valleys/problem

## Solution
```
fun countingValleys(steps: Int, path: String): Int {
    // Write your code here
     var count : Int = 0
        var returnCount = 0

        for(i in path){
            if(i == 'D'){
                count--
            }else {
                count++
            }
            if(count == 0 && i == 'U') returnCount++
        }

        return returnCount

}
```
## Electronics Shop

### Description 
https://www.hackerrank.com/challenges/electronics-shop/problem

## Solution
```
fun getMoneySpent(keyboards: Array<Int>, drives: Array<Int>, b: Int): Int {
    
    var moneySpent = 0
        for(i in keyboards){
            for(j in drives){
                var per = i + j
                if( per <= b && per > moneySpent) moneySpent = per
            }
            if(moneySpent == 0) moneySpent = -1
        }
     return moneySpent
}
```
## Save the Prisoner!

### Description 
https://www.hackerrank.com/challenges/save-the-prisoner/problem

### Solution
```
fun saveThePrisoner(n: Int, m: Int, s: Int): Int {
  return if((m + s -1) % n != 0) (m + s -1) % n else n
}
```

## Funny String

### Description 
https://www.hackerrank.com/challenges/funny-string/problem

### Solution
```
fun funnyString(s: String): String {
  var mut = mutableListOf<Int>()
        var mutai = mutableListOf<Int>()
        var mutrev = mutableListOf<Int>()
        for(i in s) mut.add(i.toInt())
        var remut = mut.asReversed()
        for(j in 0..mut.size -2) mutai.add(Math.abs(mut[j] - mut[j + 1]))
        for(k in 0..mut.size -2) mutrev.add(Math.abs(remut[k] - remut[k + 1]))

        if(mutrev == mutai) return ("Funny") else
            return ("Not Funny")

}
```


## Non-Divisible Subset

### Description 
https://www.hackerrank.com/challenges/non-divisible-subset/problem?h_r=internal-search

## Solution
```
fun nonDivisibleSubset(k: Int, s: Array<Int>): Int {
    // Write your code here
          var modulusCount = Array(k) { 0 }
        var count = 0

        s.forEach {
            modulusCount[it % k]++
        }


        for (i in 0..(k / 2)) {
            when {
                i == 0 -> if (modulusCount[0] > 0) count += 1
                k - i == i -> if (modulusCount[i] > 0) count += 1
                else -> {
                    count += if (modulusCount[i] > modulusCount[k - i]) modulusCount[i] else {
                        modulusCount[k - i]
                    }
                }
            }


        }
return count
}
```

