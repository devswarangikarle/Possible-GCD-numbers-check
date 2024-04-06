# Possible-GCD-numbers-check
Find if positive integers a and b for given numbers l and r so that: 1) The sum a+b lies between l and r inclusive. 2) The greatest common divisor(GCD) of a and b isn't 1. are possible or not? If no such numbers exist, print "No" else print "Yes". For example, gcd(6, 9)=3, gcd(8, 9)=1, gcd(4, 2)=2. 

def gcd(a, b):
    while b:
        a, b = b, a % b
    return a

def is_possible(l, r):
    for a in range((l + 1) // 2, r // 2 + 1):
        for b in range(a, r // 2 + 1):
            if gcd(a, b) != 1:
                return True
    return False

l, r = map(int, input().split())
if is_possible(l, r):
    print("Yes")
else:
    print("No")
