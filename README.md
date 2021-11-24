# 30-days-of-code

During the next 30 days, the goal is to practice hight level JavaScript function and work on my hability to solve problems. I am going to develop a solution for [Codewars](https://www.codewars.com/) problems, called "katas".   

- [ ] [Bug in Apple](https://www.codewars.com/kata/56fe97b3cc08ca00e4000dc9)
- [x] [Father and Son](https://www.codewars.com/kata/56fe9a0c11086cd842000008)
- [x] [Jumping Dutch act](https://www.codewars.com/kata/570bcd9715944a2c8e000009)
- [ ] [Planting Trees]()
- [x] [Give me the equation]()
- [ ] [Find the murderer]()
- [ ] [Reading a Book]()
- [ ] [Eat watermelon]()
- [ ] [Special factor]()
- [ ] [Guess the Hat]()
- [ ] [Symmetric Sort]()
- [ ] [Are they symmetrical?]()
- [ ] [Max Value]()
- [ ] [Trypophobia]()
- [ ] [Virus in Apple]()
- [ ] [Balance Attraction]()
- [ ] [Remove screws I]()
- [ ] [Remove screws II]()
- [ ] [Regular expression compression]()
- [ ] [Collatz Array(Split or merge)]()
- [ ] [Tidy up the room]()
- [ ] [Waiting for a Bus]()


##  Father and Son

### Task:
Every uppercase letter is Father, The corresponding lowercase letters is the Son.

Give you a string s, If the father and son both exist, keep them. If it is a separate existence, delete them. Return the result.

For example:

sc("Aab") should return "Aa"

sc("AabBc") should return "AabB"

sc("AaaaAaab") should return "AaaaAaa"(father can have a lot of son)

sc("aAAAaAAb") should return "aAAAaAA"(son also can have a lot of father ;-)

### Solution: 

```JavaScript
function sc(s){
  
  const arr = []
  
  for (const letter of s) {
    
    if((/^[A-Z]*$/u).test(letter)) {
      if(s.indexOf(letter.toLowerCase()) >= 0) {
        arr.push(letter);
      }
    }
    if((/^[a-z]*$/u).test(letter)) {
      if(s.indexOf(letter.toUpperCase()) >= 0) {
        arr.push(letter);
      }
    } 
  }
  
  return arr.length > 0 ? arr.join('') : "";
}
```

## Jumping Dutch act

### Task:
Mr. despair wants to jump off Dutch act, So he came to the top of a building.

Scientific research shows that a man jumped from the top of the roof, when the floor more than 6, the person will often die in an instant; When the floor is less than or equal to 6, the person will not immediately die, he would scream. (without proof)

Input: floor, The height of the building (floor)

Output: a string, The voice of despair(When jumping Dutch act)

Example:
sc(2) should return "Aa~ Pa! Aa!"

It means:

Mr. despair jumped from the 2 floor, the voice is "Aa~"
He fell on the ground, the voice is "Pa!"
He did not die immediately, and the final voice was "Aa!"
sc(6) should return "Aa~ Aa~ Aa~ Aa~ Aa~ Pa! Aa!"

sc(7) should return "Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Pa!"

sc(10) should return "Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Aa~ Pa!"

if floor<=1, Mr. despair is safe, return ""

### Solution:

```JavaScript
function sc(floor){
  const pattern = "Aa~ "
  let voice;
  
  if(floor <= 1) {
    voice = ""
  } else if (floor <= 6) {
    voice = pattern.repeat(floor - 1) + "Pa!" + " " + "Aa!"
  } else {
    voice = pattern.repeat(floor - 1) + "Pa!"
  }
  return voice
}
```

## Give me the equation

### Task:
Give you three numbers:a b c,please return an equation(Operators include +,-,*,/), return type is string.

For example:

sc(1,2,3) should return "1+2=3" or "2+1=3" or "3-2=1" or "3-1=2"

sc(2,2,4) should return "2+2=4" or "2*2=4" or "4/2=2" or "4-2=2"

sc(6,2,3) should return "2*3=6" or "3*2=6" or "6/2=3" or "6/3=2"

Return one of the possible answer, you can pass the test.

If there is no equation between a,b,c, return ""


### Solution:

```JavaScript
function sc(a,b,c){
  const operations = ['+', '-', '*', '/'];
  [a, b, c] = [a, b, c].sort((a,b) => a-b)
  
  
  if(a + b === c) {
    return `${a}+${b}=${c}`
  }
  
  else if(a - b === c) {
    return `${a}-${b}=${c}`
  }
  
  else if(a * b === c) {
    return `${a}*${b}=${c}`
  }
  
  else if(a / b === c) {
    return `${a}/${b}=${c}`
  }
  
  else {
    return ""
  }
}
```
___
Made with love By Gloria Morales.
