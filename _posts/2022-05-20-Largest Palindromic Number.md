---
layout: post
title: Largest Palindromic Number
image: "/posts/palindrome_post.jpg"
tags: [Palindrome, Python]
---

# Largest Palindromic Number

---

A palindrome is a word/set of numbers that reads the same from both ends. Sounds cool right? I did some googling to find some interesting facts and this excerpt from the Merriam-Webster dictionary is pretty cool:

Palindrome comes from Greek palindromos, meaning "running back again," which itself is from palin ("back," "again") and dramein ("to run"). Nowadays, we appreciate a  clever palindrome—such as "Drab as a fool, aloof as a bard" or "A man, a plan, a canal: Panama"—or even a simple one like "race car," but in the past palindromes were more than just smart wordplay. Some folks thought they were magical, and they carved them on walls or amulets for protection (https://www.merriam-webster.com/dictionary/palindrome)

In this simple project, I am going to create the largest palindrome made from the product of two 3-digit numbers - this is one of the first python challenges I did. Enjoy!

You can try it out using the web app here: <https://github.com/ibiene-ds/palindrome/blob/main/README.md>

```python
def is_palindrome(number):
    """
    this function takes either a number or a string and checks if it is a palindrome. Returns
    True if palindrome or False otherwise
    """
    num_str = str(number)
    num_str_rev = num_str[::-1]
    if num_str == num_str_rev:
        return True
    else:
        return False


def multiply_lists(num_list):
    """
    this function multiplies all the elements of a list by itself. For instance, passing a list of length 4,
    a = [1, 2, 3, 4 ] to the function gives the resulting list of [1, 2, 3, 4, 2, 4, 6, 8, 3, 6, 9, 12, 4, 8, 12, 16 ]
    of length 16
    """
    num_list_dup = num_list.copy()
    index = 0
    list_of_multiples =[]
    for num2 in num_list_dup:
        mult_list = [num2 * num_list[index] for num2 in num_list_dup]
        list_of_multiples.extend(mult_list)
        index = index +1
    return (list_of_multiples)


def check_largest_palindrome(input_list):
    """
    this function checks any list, generates a sublist of palindromes
    and returns the largest palindrome
    """
    palindrome_list =[]
    for x in input_list:
        if is_palindrome(x) == True:
            palindrome_list.append(x)
    return max(palindrome_list)


def largest_palindrome(list_of_nums):
    """
    this function takes one argument and returns the largest palindrome from a product of a list by itself 
    """
    x = multiply_lists(list_of_nums)
    y = check_largest_palindrome(x)
    return y

three_digit_nums = list(range(100, 1000))
output = largest_palindrome(three_digit_nums)

print (f"The largest palindrome within the range indicated is {output}")

```
### The largest palindrome within the range indicated is 906609

