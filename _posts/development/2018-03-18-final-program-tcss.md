---
layout: article
title:  "Final Program - TCSS142"
date:   2018-03-18
categories: development
image:
    teaser: uwt_teaser_image.jpg
    feature: hguide1_tcss.jpg
comments: true
---

Spring break starts next week an I'm sure we are all glad to be done with finals! I don't believe that a solution for the final will be posted (UWT TCSS 142), so I thought I'd post mine for people to peruse if they so wish. I was fortunate enough to get full marks on it, so hopefully you can trust my answer. Feel free to ask any questions - I'd be glad to answer them!

#### Final Program:

```python
def main():
    length = menu()
    valid_10 = []
    valid_13 = []

    if length != "10" and length != "13":
        print("Incorrect length entered -- Thank you for using my program, goodbye!")

    else:
        if length == "10":
            rules_10()
        else:
            rules_13()

        while length == "10" or length == "13":
            if length == "10":
                code = input("\nEnter your 10 character item code: ")
                if nondigit_10(code) and digits(code):
                    print("Valid")
                    valid_10.append(code)
                else:
                    print("Invalid")
            else:
                code = input("\nEnter your 13 character item code: ")
                if nondigit_13(code) and digits(code):
                    print("Valid")
                    valid_13.append(code)
                else:
                    print("Invalid")

            more = input("\nAre there more item codes to validate [y/n]? ")

            if more != "y":
                print()
                print("These are the valid codes you entered:")
                if length == "10":
                    print(valid_10)
                    validfile(valid_10)
                else:
                    print(valid_13)
                    validfile(valid_13)
                length = "0"

        print("\nThank you for using my program!")


def menu():
    print("This program validates item codes!")
    length = input("Enter your preferred item code length [10 or 13]: ")

    return length

def rules_10():
    print("\nHere are the requirement for 10 character item codes:")
    print("1) Must have 10 characters; \n\
2) Must start with an upper case letter; \n\
3) Must contain at least two lowercase letters; \n\
4) Must contain exactly three digits; \n\
5) The last character cannot be a digit; \n\
6) The sum of digits has to be a multiple of three.")

def rules_13():
    print("\nHere are the requirement for 13 character item codes:")
    print("1) Must have 13 characters; \n\
2) Must start with an upper case letter; \n\
3) Must contain at least two lowercase letters; \n\
4) Must contain at least one character '$', or '&'; \n\
5) Must contain exactly three digits; \n\
6) The last character cannot be a digit; \n\
7) The sum of digits has to be a multiple of three.")

def nondigit_10(code):
    if len(code) == 10:
        if code[0] == code[0].upper():
            if lowercase(code):
                return True
    return False

def nondigit_13(code):
    if len(code) == 13:
        if code[0] == code[0].upper():
            if lowercase(code):
                if '$' in code or '&' in code:
                    return True
    return False

def digits(code):
    count = 0
    summ = 0
    for i in range(len(code)):
        if code[i].isdigit():
            count += 1
            summ += int(code[i])

    if count == 3:
        if not(code[len(code)-1].isdigit()):
            if summ % 3 == 0:
                return True
    return False

def lowercase(code):
    count = 0
    for i in range(len(code)):
        if code[i].isalpha() and code[i] == code[i].lower():
            count += 1
    if count >= 2:
        return True
    return False

def validfile(lis):
    infile = open("valid_codes.txt", "w")
    for i in lis:
        infile.write(i + "\n")
    infile.close()

    print("The file valid_codes.txt was created")

main()

```
