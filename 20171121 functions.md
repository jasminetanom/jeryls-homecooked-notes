### Functions ###
def pony(a, b=2):
	pass
	#a and b are arguments, 2 is a parameter of b. pass is used as placeholder for function

#Return will assign values to variable, but print function does not

#*args and **kwargs, positional arguments must be before keyword arguments
cheem(*students, **state)

#DataScience SG, Singapore python user group, datakind sg, engineering.sg
total += n is total += n 

###LIST COMPRE
# [n for n in numbers] : read from right to left, output is at the left
lamda n: n*n, numbers #source, always used with MAP() and APPLY()
map() #taking each item and map n*n to it

#double for loops and list compre
#for example
for alphabet in 'xyz':
	for numbers in range(4):
		mylist.append((alphabet, numbers))

# list compre
list compre = [(alphabet, numbers) for alphabet in xyz for numbers in range(4)]

# for loop
something = []
for num in n:
    if num == 1:
        something.append(0)
    elif num == 0:
        something.append(1)
    else:
        something.append(None)
print something

# list comprehension
lc_new = [
    1 if num == 0 
    else 0 if num == 1 
    else None 
    for num in n
]

print lc_new