---
layout: post
title: Basic String Compressor
image: "/posts/string_compressor_pic.jpg"
tags: [Python, String Compressor, Run Length Encoder]
---

---

In this project, I created a function that implements basic string compressor. The function is agnostic to case type.


```python
def count_repeated_chars(word):
    """
    this function iterates through a string and 
    returns a count of consecutive repeated characters 
    """
    count_list = []
    count = 1
    for i in range(len(word)-1):
        if word[i] == word [i+1]:
            count = count + 1
        else:
            count_list.append(count)
            count = 1 
    count_list.append(count)
    return (count_list)

def key_chars(word):
    """
    this function uses the itertools module and returns 
    the groupings of strings and the keys
    """
    from itertools import groupby
    groups =[]
    keys = []
    for key, group in groupby(word):
        groups.append(list(group))
        keys.append(key)
    return keys
        

def string_compression (original_string, case_type = 0):
    """
    This function takes a string and compresses it using
    the counts of consecutive letters. The function takes a 2nd
    argument which specifies the case type - upper (1) or lower (0).
    If this is not specified, the function defaults to
    lower case.
    """
    if case_type == 0:
        mod_original_string = original_string.lower()
    elif case_type == 1:
        mod_original_string = original_string.upper()
    else:
        mod_original_string = original_string.lower()

    
    count_rep_chars = count_repeated_chars(mod_original_string)

    
    key_characters = key_chars(mod_original_string)

    import itertools
    zipped = list(zip(key_characters, count_rep_chars))
    combined_flat_list = list(itertools.chain(*zipped))


    all_str = []
    for item in combined_flat_list:
        if type(item) == str:
            all_str.append(item)
        else:
            all_str.append(str(item))

    compressed_string = "".join(all_str)

    if len(compressed_string) >= len(mod_original_string):
        print (mod_original_string)
    else:
        return compressed_string


print(string_compression("aaabbbffggggaaa", 0))
print(string_compression("Aaabbbffggggaaa", 1))

```

### a3b3f2g4a3
### A3B3F2G4A3
