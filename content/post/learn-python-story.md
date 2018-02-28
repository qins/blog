---
title: "Learn Python Story"
date: 2018-03-01T00:43:18+08:00
draft: false
---

### Python code:
```python
#!/usr/bin/python3
import sys
from math import sin,pi,e

# Long long time ago...
'''
There is a King.
He has a Queen.
'''
print("King: Hello, my Queen!")

child1 = "boy"

if child1=="girl":
    print("They have a princess.")
elif child1=="boy":
    print("They have a prince.")
else:
    print("They have a ...")

title = {'boy': 'prince', 'girl': 'princess'}
print('Albert: Yes, I\'m a', title[child1], end='.\n')

print('And There are two princesses.')
class people:
    name=''
    age=0
    intro=''
    # One's weight is private.
    __weight=0
    def __init__(self,n,a,w,s):
        self.name = n
        self.age = a
        self.sex = s
        self.__weight = w
    def introduce(self):
        isOverWeight = ''
        if self.__weight < 60:
            isOverWeight = 'not '
        self.intro = "{}: I'm {} years old and {}overweight.".format(self.name, self.age, isOverWeight)
        #print(self.intro)

class royal_student(people):
    title = ''
    learn = ''
    hobby = ''
    def __init__(self,n,a,w,s,l,h):
        people.__init__(self,n,a,w,s)
        self.learn = l
        self.title = title[s]
        self.hobby = h
    def introduce(self):
        people.introduce(self)
        self.intro = "{} My title is {}. I'm study {}, and I like {}.".format(self.intro, self.title, self.learn, self.hobby)
        print(self.intro)


child2 = royal_student('Alice', 22, 59, 'girl', 'math', 'coding')
child2.introduce()
child3 = royal_student('Lily', 18, 69, 'girl', 'art', 'eating')
child3.introduce()

#j = complex(0,-1)
#euler = e**(pi*j) + 1
euler = 0
angle = sin(pi/2)
print('Alice: Math is beautiful. e^(pi*i) + 1 = {}, sin(pi/2) = {}'.format(euler, angle))

seq = 'ANDroiD'
revSeq = seq[::-1]
print('Alice: I am gona write a app for {}(Android) which reverse sequence is {}.'.format(seq, revSeq))

print("Albert: I'm writing our family tree to familyTree.txt.")
f = open("familyTree.txt", "w")
f.write("King Queen\n")
f.write("Lily Alice Albert\n")
f.close()

print("Albert: I'm reading our family tree to you:")
#f = open("familyTree.txt", "r")
with open("familyTree.txt", "r") as f:
    for line in f:
        print(line.rstrip())

count = 0
i = 1
while i <= 100:
    count += i
    i += 1
print('Alice: What is the sum of 1 to 100? The answer is {} which calculate by the most stupid but simple coding method.'.format(count))

beer_puzzle = '''
King: Alice, You are so clever, my sweet heart.
I have $10. And $2 can buy 1 bottle of beer.
4 bottle caps can be exchanged for 1 bottle beer.
2 empty bottles can be exchanged for 1 bottle of beer.
So, how many bottles of beer can I drink?
I will make you the next Queen if you give the correct answer.
'''
print(beer_puzzle)
money, bottles, caps = 10, 0, 0
count = 0
def drinkAndExchange(money, bottles, caps):
    global count
    Round = 0
    # drink & exchange
    Round += money // 2
    money = money % 2
    Round += bottles // 2
    bottles = bottles % 2
    Round += caps // 4
    caps = caps % 4
    # count
    if Round == 0:
        return count
    bottles += Round
    caps += Round
    count += Round
    #print("count: ", count)

    return drinkAndExchange(money, bottles, caps)

bottles_count = drinkAndExchange(money, bottles, caps)

print('You can drink {} bottles, dady.'.format(bottles_count))

print('Sorry, darling, but I can only drink 2 bottles atmost.')


print('\n---\n' + 'The story is written on', sys.platform + '.')
```

### Run story.py, Output Story:
* King: Hello, my Queen!
* They have a prince.
* Albert: Yes, I'm a prince.
* And There are two princesses.
* Alice: I'm 22 years old and not overweight. My title is princess. I'm study math, and I like coding.
* Lily: I'm 18 years old and overweight. My title is princess. I'm study art, and I like eating.
* Alice: Math is beautiful. e^(pi\*i) + 1 = 0, sin(pi/2) = 1.0
* Alice: I am gona write a app for ANDroiD(Android) which reverse sequence is DiorDNA.
* Albert: I'm writing our family tree to familyTree.txt.
* Albert: I'm reading our family tree to you:  

> King Queen
>> Lily Alice Albert
* Alice: What is the sum of 1 to 100? The answer is 5050 which calculate by the most stupid but simple coding method.

* King: Alice, You are so clever, my sweet heart.  

>I have $10. And $2 can buy 1 bottle of beer.
>4 bottle caps can be exchanged for 1 bottle beer.
>2 empty bottles can be exchanged for 1 bottle of beer.
>So, how many bottles of beer can I drink?
* I will make you the next Queen if you give the correct answer.

^\_^: You can drink 15 bottles, dady.  
XD: Sorry, darling, but I can only drink 2 bottles atmost.

---
The story is written on linux.
