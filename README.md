# 30-days-of-code

During the next 30 days, the goal is to practice hight level JavaScript function and work on my hability to solve problems. I am going to develop a solution for [Codewars](https://www.codewars.com/) problems, called "katas".   

- [ ] [Bug in Apple](https://www.codewars.com/kata/56fe97b3cc08ca00e4000dc9)
- [x] [Father and Son](https://www.codewars.com/kata/56fe9a0c11086cd842000008)
- [x] [Jumping Dutch act](https://www.codewars.com/kata/570bcd9715944a2c8e000009)
- [ ] [Planting Trees](https://www.codewars.com/kata/5710443187a36a9cee0005a1)
- [x] [Give me the equation](https://www.codewars.com/kata/56fe9b65cc08cafbc5000de3)
- [ ] [Find the murderer](https://www.codewars.com/kata/570f3fc5b29c702c5500043e)
- [ ] [Reading a Book](https://www.codewars.com/kata/570ca6a520c69f39dd0016d4)
- [ ] [Eat watermelon](https://www.codewars.com/kata/570df12ce6e9282a7d000947)
- [ ] [Special factor](https://www.codewars.com/kata/570e5d0b93214b1a950015b1)
- [ ] [Guess the Hat](https://www.codewars.com/kata/570ef7a834e61306da00035b)
- [ ] [Symmetric Sort](https://www.codewars.com/kata/5705aeb041e5befba20010ba)
- [ ] [Are they symmetrical?](https://www.codewars.com/kata/5705cc3161944b10fd0004ba)
- [ ] [Max Value](https://www.codewars.com/kata/570771871df89cf59b000742)
- [ ] [Trypophobia](https://www.codewars.com/kata/56fe9ffbc25bf33fff000f7c)
- [ ] [Virus in Apple](https://www.codewars.com/kata/5700af83d1acef83fd000048)
- [ ] [Balance Attraction](https://www.codewars.com/kata/57033601e55d30d3e0000633)
- [ ] [Remove screws I](https://www.codewars.com/kata/5710a50d336aed828100055a)
- [ ] [Remove screws II](https://www.codewars.com/kata/5710a8fd336aed00d9000594)
- [ ] [Regular expression compression](https://www.codewars.com/kata/570bae4b0237999e940016e9)
- [ ] [Collatz Array(Split or merge)](https://www.codewars.com/kata/56fe9d579b7bb6b027000001)
- [ ] [Tidy up the room](https://www.codewars.com/kata/5703ace6e55d30d3e0001029)
- [ ] [Waiting for a Bus](https://www.codewars.com/kata/57070eff924f343280000015)


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
