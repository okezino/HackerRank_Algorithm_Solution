# HackerRank_Algorithm_Solution
This repo gives a guide and work flow on hackerRank Algorithm from simple to complex, it gives sudo code solution and code solution written in Kotlin



## Solve Me First

### Description
https://www.hackerrank.com/challenges/solve-me-first/problem

### Solution

```
fun solveMeFirst(a: Int, b: Int): Int {
    return a + b
}
```

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
## Compare the Triplet

### Description
https://www.hackerrank.com/challenges/compare-the-triplets/problem

### Solution
```
fun compareTriplets(a: Array<Int>, b: Array<Int>): Array<Int> {
        var up : Int = 0
        var down : Int = 0
        for (i in a.indices){
            when {
                a[i] > b[i] -> up++
                b[i] > a[i] -> down++
            }
        }
        return arrayOf(up,down)

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
## Diagonal Difference

### Description
https://www.hackerrank.com/challenges/diagonal-difference/problem

### Solution
```

fun diagonalDifference(arr: Array<Array<Int>>): Int {
    // Write your code here
    var left2Right = 0
        var right2Left = 0
        var first = 0
        var second = 0
        var fourth = arr.size -1
        for (i in arr.indices) {
            left2Right += arr[first][second]
            right2Left += arr[first][fourth]
            first++
            second++
            fourth--
        }
        return Math.abs(left2Right - right2Left)

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

## Staircase
### Description
https://www.hackerrank.com/challenges/staircase/problem

### Solution
```
fun staircase(n: Int): Unit {
  for (i in 1..n) {
            print(" ".repeat((n - i)) + "#".repeat(i))
            println()
        }

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

## Time Conversion
### Description
https://www.hackerrank.com/challenges/time-conversion/problem
### Solution

```
fun timeConversion(s: String): String {
                var timeFormat : String = s.takeLast(2)
                var time: String = s.take(8)
                var (hr,min,sec) = time.split(":")
                var calhr = hr.toInt()
               return  when{
                      timeFormat == "PM" -> {
                            if(hr == "12"){ 
                              "${hr}:${min}:${sec}"
                              }else {
                                  calhr += 12
                                "${calhr}:${min}:${sec}"
                              }
                      }
                      else ->{
                              if(hr == "12") {
                              "00:${min}:${sec}"
                              } else{
                                "${hr}:${min}:${sec}"
                              }

                      }

                }
}
```

## Grading Student

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
## Between Two Sets

### Description
https://www.hackerrank.com/challenges/between-two-sets/problem

## Solution
```
fun getTotalX(a: Array<Int>, b: Array<Int>): Int {  
return  (a.last()..b.first() step a.last()).count { num -> a.all{num % it == 0} && b.all{it % num == 0 } }
}
```

## BreakingBreaking the Records

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
## Day of the Programmer

### Description
https://www.hackerrank.com/challenges/day-of-the-programmer/problem

### Solution
```
fun dayOfProgrammer(year: Int): String {

  if(year in 1700..1917 && year % 4 == 0) return "12.09.$year"
               else if(year in 1919..2700) {
                   if(year % 400 == 0 || (year % 4 == 0 && year % 100 != 0)){
                      return  "12.09.$year"
                   }else return  "13.09.$year" }
                else if(year == 1918) return  "26.09.1918"
                else return  "13.09.$year"
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

## Drawing Book

### Description 
## Solution 
```
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
https://www.hackerrank.com/challenges/non-divisible-subset/problem

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

## Separate the Numbers

### Description
https://www.hackerrank.com/challenges/separate-the-numbers/problem

## Solution
```
fun separateNumbers(s: String): Unit {
    // Write your code here
     var result = "NO"

    if (s[0] != '0'){
        var size = s.length / 2
        var digit = 1
        var first : Long = (s[0].toInt() - 48).toLong()
        var second = ""




        loo@ while (first.toString().length <= size) {
            second = ""
            var third = (first).toString()
            var forth = (first).toString()
            while (third.length < s.length) {
                first++

                third += (first).toString()


                if (third == s) {
                    result = "YES $forth"
                    break@loo
                    return
                }
            }

            for (i in 0..digit) {
                second += s[i]
            }
            digit++
            first = second.toLong()


        }
    }


    println(result)

}
```
## Mars Exploration

### Description
https://www.hackerrank.com/challenges/mars-exploration/problem

## Solution
```
fun marsExploration(s: String): Int {
    // Write your code here
    var count = 0
        var countMars = 0

        for (i in s){

            when(count){
                0 -> {
                    count = 1
                    if(i != 'S') countMars++

                }
                1 -> {
                    count = 2
                    if(i != 'O') countMars++

                }
                2 -> {
                    count = 0
                    if(i != 'S') countMars++
                    
                }
            }
        }

        return countMars
}
```

## Gemstones

## Description
https://www.hackerrank.com/challenges/gem-stones/problem

```
fun gemstones(arr: Array<String>): Int {
    // Write your code here
var str = arrayListOf<Char>()
    var ununique = ""

    for(i in arr[0]) if(!str.contains(i)) str.add(i)

    for(i in 1..arr.lastIndex){
        for(j in str) if(!arr[i].contains(j)) ununique +=j
    }
    for (i in ununique ) str.remove(i)
    
    return str.size
}
```

## Unique Paths
## Description
https://leetcode.com/problems/unique-paths/
### Dynamic Programming

```
class Solution {
    fun uniquePaths(m: Int, n: Int, hashMap: HashMap<String, Int> = HashMap()): Int {
        
        val key = "$m,$n"
        if(key in hashMap.keys) return hashMap[key]!!
        if(m == 1 && n == 1)  return 1
        if(m == 0 || n == 0 ) return 0
        
        hashMap[key] = uniquePaths(m - 1, n, hashMap) + uniquePaths(m , n - 1, hashMap )
        
        return hashMap[key]!!
        
    }
}
```

## Fibonacci
## Description
https://leetcode.com/problems/fibonacci-number/

### Dynamic Programming
```
class Solution {
    fun fib(n: Int, hashMap : HashMap<Int,Int> = HashMap()): Int {
        
       if(n in hashMap.keys)  return  hashMap[n]!!  
       if(n == 0) return 0
        if(n <= 2) return 1
        
       hashMap[n] =   fib(n - 1, hashMap) + fib(n - 2, hashMap)
       
       return hashMap[n]!!
        
    }
}
```


