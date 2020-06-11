# SMT_Flowchart
fh = open(r"מסמך שלב ב.txt", "a")

import datetime
import time

x = datetime.datetime.today()
a_a = 0
b_b = 0
c_c = 0
d_d = 0
e_e = 0
f_f = 0
g_g = 0
h_h = 0
i_i = 0
j_j = 0
k_k = 0
sum_score = 0
number = 0

import sys


def login(username, password):
    # Assuming you just want to test this and keep the data in the source file
    accounts = {'raz': '14130',
                'dan': '12345'}
    if password == accounts[username]:
        return True
    return False


def main():
    login_tries = 0
    if login_tries > 5:
        sys.exit()
        # To prevent infinite login attempts

    user, pw = input('please enter your username:\n '), input("please enter your flex id:\n ")
    fh.write(str(user))
    fh.write(str(pw))

    if login(user, pw):
        time.sleep(2)
        print("\nThanks!\n")
        time.sleep(2)
        print("Login successful!")
        fh.write(str("Login successful!"))
        # Do stuff
    else:
        time.sleep(2)
        print("\nOh no!")
        print("Wrong username or password!\n")
        time.sleep(2)
        fh.write(str("Wrong username or password!"))
        main()


# https://app.site123.com/manager/wizard.php?w=3290273&from=dash#
# https://5e8821f33c6ec.site123.me
def Continue_assembly():
    print("Thanks!!")
    fh.write(str("Thanks!!"))
    time.sleep(2)
    print(f"Your score is {sum_score}")
    time.sleep(2)
    fh.write(str("Your score is:"))
    fh.write(str(sum_score))
    print(f'please go head for this assembly and report to shift manager\n')
    time.sleep(2)
    print(x.strftime("* %c"))
    fh.write(str("\nplease go head for this assembly and report to shift manager\n"))
    fh.write(x.strftime("* %c\n"))
    time.sleep(30)


def Stop_assembly():
    print("Thanks!!")
    fh.write(str("Thanks!!"))
    time.sleep(2)
    print(f'Your score is {sum_score} up the limit\n')
    fh.write(str("Your score is:"))
    fh.write(str(sum_score))
    fh.write(str("\tup the limit"))
    time.sleep(2)
    print(f' please stop this assembly and report to shift manager\n')
    time.sleep(2)
    print(x.strftime("* %c"))
    fh.write(str("\nplease stop this assembly and report to shift manager\n"))
    fh.write(x.strftime("* %c\n"))
    time.sleep(30)


def Hello_user():
    print('\n\n\t\t\t\tHello\n\nThis is a software to calculating the criteria if to continue the SMT process\n\n')
    print("\tDOCUMENT STAGE B")
    text1 = "\t               \n"
    print('\u0332\u0332'.join(text1))
    fh.write(str("\n\nDOCUMENT STAGE B\n"))
    fh.write(x.strftime("\n\t* %c\n"))
    time.sleep(2)
    print("\n\t(Please follow the steps below and answer yes or no for the following questions)\n")
    time.sleep(2)
    fh.write(str("\n\tPlease follow the steps below and answer yes or no for the following questions\n\n"))
    print("\n\tPlease enter, score 1-4, (minimum 1, maximum 4) for each question you will be asked\n\n")
    time.sleep(2)
    fh.write(str("\n\tPlease enter, score 1-4, (minimum 1, maximum 4) for each question you will be asked\n\n"))


if __name__ == "__main__":
    main()
time.sleep(2)
# Hello, criteria + score
Hello_user()
# First qestion: quantity of boards in batch and adding score (1-4)
number = input(print(
    '\t(1) quantity of boards in batch\n\t\t(Please enter score 1-4 points)\n\n\t\t * 3-1 = 1\n\t\t * 8-4 = 2\n\t\t * 15-9 = 3\n\t\t * 15 and up = 4\n'))
sum_score += int(number)
fh.write(
    "\n(1) quantity of boards in batch\n(Please enter score 1-4 points)\n\n * 3-1 = 1\n * 8-4 = 2\n * 15-9 = 3\n * 15 and up = 4\n")
fh.write(str(a_a))
a_a = int(number)
# second question: quantity of components on a boards and adding score (1-4)
number = input(
    '\t(2) quantity of components on a boards\n\t\t(Please enter score 1-4 points)\n\n\t\t * 1 component = 1\n\t\t * 3-2 component = 2\n\t\t * 10-4 component = 3\n\t\t * 10 and up = 4\n')
sum_score += int(number)
b_b = int(number)
fh.write(
    "\n(2) quantity of components on a boards\n (Please enter score 1-4 points)\n\n * 1 component = 1\n * 3-2 component = 2\n * 10-4 component = 3\n * 10 and up = 4\n")
fh.write(str(b_b))
# third question: if it's BGA
number = input(
    '\t(3) if it is BGA/MicroBGA\n\t\t(Please enter score 1-4 points)\n\n\t\t * If not = 0\n * Pitch = > 1.0 = '
    '1\n\t\t * Pitch = > 0.6 = 2\n\t\t * MicroBGA + DIP FLUX = 3\n\t\t * MicroBGA + paste = 4\n')
sum_score += int(number)
c_c = int(number)
fh.write(
    "\n(3) if it is BGA/MicroBGA\n  (Please enter score 1-4 points)\n\n * If not = 0\n * Pitch = > 1.0 = 1\n * Pitch "
    "= > 0.6 = 2\n * MicroBGA + DIP FLUX = 3\n * MicroBGA + paste = 4\n")
fh.write(str(c_c))
# if it's a Component with a thermal pad
number = input(
    '\t(4) if it is a Component with a thermal pad\n\t\t(Please enter score 1-4 points)\n\n\t\t * If not = 0\n\t\t * '
    'up to 30% = 2\n\t\t * up to 50% = 4\n')
sum_score += int(number)
d_d = int(number)
fh.write(
    "\n(4) if it is a Component with a thermal pad\n  (Please enter score 1-4 points)\n\n * If not = 0\n * up to 30% "
    "= 2\n * up to 50% = 4\n")
fh.write(str(d_d))
# if it's a fine pitch component
number = input(
    '\t(5) if it is a fine pitch component\n\t\t(Please enter score 1-4 points)\n\n\t\t * If not = 0\n\t\t * Short = '
    '1\n\t\t * Disconnect = 4\n')
sum_score += int(number)
e_e = int(number)
fh.write(
    "\n(5) if it is a fine pitch component\n  (Please enter score 1-4 points)\n\n * If not = 0\n * Short = 1\n * "
    "Disconnect = 4\n")
fh.write(str(e_e))
# if it's a passive component
number = input(
    '\t(6) if it is passive component\n\t\t(Please enter score 1-4 points)\n\n\t\t * If not = 0\n\t\t * 0603 and up = '
    '1\n\t\t * 0402 = 2\n\t\t * MicroBGA + DIP FLUX0201/01005 = 4\n')
sum_score += int(number)
f_f = int(number)
fh.write(
    "\n(6) if it is passive component\n  (Please enter score 1-4 points)\n\n * If not = 0\n * 0603 and up = 1\n * "
    "0402 = 2\n * MicroBGA + DIP FLUX0201/01005 = 4\n")
fh.write(str(f_f))
# if it's a PIH
number = input(
    '\t(7) if it is a PIH component\n\t\t(Please enter score 1-4 points)\n\n\t\t * If not = 0\n\t\t * Without SMD = '
    '1\n\t\t * Integrated SMD = 4\n')
sum_score += int(number)
g_g = int(number)
fh.write(
    "\n(7) if it is a PIH component\n  (Please enter score 1-4 points)\n\n * If not = 0\n * Without SMD = 1\n * "
    "Integrated SMD = 4\n")
fh.write(str(g_g))
# if there repair capability in SMT
number = input(
    '\t(8) if there repair capability in SMT\n\t\t(Please enter score 1-4 points)\n\n\t\t * Yes = 1\n\t\t * No = 4\n')
sum_score += int(number)
h_h = int(number)
fh.write("\n(8) if there repair capability in SMT\n  (Please enter score 1-4 points)\n\n * Yes = 1\n * No = 4\n")
fh.write(str(h_h))
# if it's sensitive customer
number = input(
    '\t(9) if it is sensitive customer\n\t\t(Please enter score 1-4 points)\n\n\t\t * Apple, Innoviz, AirSpan, '
    'GOJI = 4\n\t\t * All other customer = 1\n')
sum_score += int(number)
i_i = int(number)
fh.write("\n(9) hat is the soldering technology\n  (Please enter score 1-4 points)\n\n * V.P = 4\n * Reflow = 1\n")
fh.write(str(i_i))
# what is the soldering technology
number = input(
    '\t(10) what is the soldering technology\n\t\t(Please enter score 1-4 points)\n\n\t\t * V.P = 4\n\t\t * Reflow = '
    '1\n')
sum_score += int(number)
j_j = int(number)
fh.write("\n(10) what is the soldering technology\n  (Please enter score 1-4 points)\n\n * V.P = 4\n * Reflow = 1\n")
fh.write(str(j_j))
# what the resources required to test 100% of the problem, during production
number = input(
    '\t(11) what the resources required to test 100% of the problem, during production\n\t\t(Please enter score 1-4 '
    'points)\n\n\t\t * SPI/AOI = 1\n\t\t * Q.C = 2\n\t\t * X-RAY = 4\n')
sum_score += int(number)
k_k = int(number)
fh.write(
    "\n(11) what the resources required to test 100% of the problem, during production\n  (Please enter score 1-4 "
    "points)\n\n * SPI/AOI = 1\n * Q.C = 2\n * X-RAY = 4\n")
fh.write(str(k_k))

if sum_score > 12:
    Stop_assembly()
else:
    Continue_assembly()

fh.close()
