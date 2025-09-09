import random
print("Math Quiz!")
print("Choose an operator to start the quiz:")
print("1. Addition (+)")
print("2. Subtraction (-)")
print("3. Multiplication (*)")

choice = input("Enter 1, 2, or 3: ").strip()

if choice == '1':
    operator = '+'
elif choice == '2':
    operator = '-'
elif choice == '3':
    operator = '*'
else:
    print("Invalid input. Exiting.")
    exit()


score = 0
total = 0

print("\nType the correct option (A/B/C/D) or 'exit' to quit.\n")

while True:
    a = random.randint(1, 20)
    b = random.randint(1, 20)

    # In case if answer is negative in subtraction
    if operator == '-' and b > a:
        a, b = b, a

    # finding correct answer
    if operator == '+':
        correct = a + b
    elif operator == '-':
        correct = a - b
    elif operator == '*':
        correct = a * b

    # Options
    options = [correct,
               correct + random.randint(1, 5),
               correct - random.randint(1, 5),
               correct + random.randint(6, 10)]
    options = list(set(options))


    while len(options) < 4:
        options.append(correct + random.randint(1, 10))
    random.shuffle(options)

    labels = ['A', 'B', 'C', 'D']
    option_dict = dict(zip(labels, options))

    print(f"What is {a} {operator} {b}?")
    for key in labels:
        print(f"{key}. {option_dict[key]}")

    answer = input("Your answer (A/B/C/D): ").strip().upper()

    if answer == 'EXIT':
        break

    if answer in labels:
        total += 1
        if option_dict[answer] == correct:
            score += 1
            print("Correct!\n")
        else:
            print(f"Wrong\nCorrect answer is {correct}\n")
    else:
        print("Invalid option. Try again.\n")


if total > 0:
    percent = (score / total) * 100
    print("\nQuiz Completed!")
    print(f"Your score is {score} out of {total}")
    print(f"Score: {percent:.2f}%")
else:
    print("\nNo questions answered.")
