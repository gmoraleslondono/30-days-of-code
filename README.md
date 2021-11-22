# 30-days-of-code

During the next 30 days, the goal is to practice hight level JavaScript function and work on my hability to solve problems. I am going to develop a solution for [Codewars](https://www.codewars.com/) problems, called "katas".   

- [ ] [Bug in Apple](https://www.codewars.com/kata/56fe97b3cc08ca00e4000dc9)
- [x] [Father and Son](https://www.codewars.com/kata/56fe9a0c11086cd842000008)
- [ ] [Jumping Dutch act]()
- [ ] [Planting Trees]()
- [ ] [Give me the equation]()
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
